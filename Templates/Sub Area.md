---
cssclasses: 
type: sub-area-page
area: "[[<% tp.file.folder() %>]]"
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
```meta-bind-button
label: New project
icon: "plus"
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Projet.md
    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
## Todo

```tasks
filter by function task.file.folder.includes(query.file.folder)

group by filename
group by status.name


sort by priority

```

## Projets
```tasks
filter by function task.file.folder.includes(query.file.folder.replace("2 - Area", "1 - Project"))

group by function task.file.folder.slice(0, -1).split('/').pop()
group by status.name


sort by priority

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
  // Rename file with the one choose by user
  const fileName = await tp.system.prompt("Title :")
  await tp.file.rename(fileName)
  
  const baseFolder = tp.file.folder(true)
  const newFolder = `${baseFolder}/${fileName}/`

  await tp.file.move(newFolder + fileName)
%>