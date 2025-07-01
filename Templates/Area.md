---
cssclasses: 
type: area-page
category: "[[2 - Area]]"
---

```meta-bind-button
label: Sub Area
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
  // Rename file with the one choose by user
  const fileName = await tp.system.prompt("Title :")
  await tp.file.rename(fileName)
  
  const baseFolder = tp.file.folder(true)
  const newFolder = `${baseFolder}/${fileName}/`

  await tp.file.move(newFolder + fileName)
%>