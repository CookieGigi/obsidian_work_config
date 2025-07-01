---
cssclasses: 
type: area-page
category: "[[2 - Area]]"
---

```meta-bind-button
label: New sub area
icon: plus
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Sub Area.md

    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
# Sub Area
```dataview
List
where contains(file.folder, this.file.folder)
where !contains(file.folder, "4 - Archive")
where contains(type, "sub-area")
sort priority
```
<%*
	console.log(tp.file.folder(true).split('/'))
	const folders = tp.file.folder(true).split('/')
	const fileName = folders[folders.length - 1]
  
	const baseFolder = tp.file.folder(true)
	const newFolder = `${baseFolder}/`

	await tp.file.move(newFolder + fileName)
%>