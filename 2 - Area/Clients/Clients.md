---
cssclasses: 
type: area-page
category: "[[2 - Area]]"
---

```meta-bind-button
label: New client
icon: plus
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Client.md

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
