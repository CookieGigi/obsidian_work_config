---
cssclasses:
type: directory-page
category: "[[<% tp.file.folder(true).split('/').slice(-2, -1)%>]]"
---

```meta-bind-button
label: New note
icon: plus
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Note.md

    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
## Todo

```dataview
TASK
WHERE startswith(file.folder, this.file.folder)
```

## Notes

> [!multi-column]
> 
>> Last modified
>>```dataview
>>List
>>FROM ""
>>WHERE contains(file.folder, this.file.folder)
>>WHERE type != "directory-page"
>>SORT file.mtime DESC
>>LIMIT 5
>>```
>
>> Last new
>>```dataview
>>List
>>FROM ""
>>WHERE contains(file.folder, this.file.folder)
>>WHERE type != "directory-page"
>>SORT file.ctime DESC
>>LIMIT 5
>>```
>
>> All
>>```dataview
>>LIST
>>WHERE contains(file.folder, this.file.folder)
>>WHERE type != "directory-page"
>>```
<%*
	console.log(tp.file.folder(true).split('/'))
	const folders = tp.file.folder(true).split('/')
	const fileName = folders[folders.length - 1]
  
	const baseFolder = tp.file.folder(true)
	const newFolder = `${baseFolder}/`

	await tp.file.move(newFolder + fileName)
%>
