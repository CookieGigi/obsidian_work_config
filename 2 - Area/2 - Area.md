---
cssclasses: 
type: directory-page
category: "[[2 - Area]]"
---

```meta-bind-button
label: Area
icon: plus
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Area.md

    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
# Area
```dataview
List
where contains(file.folder, this.file.folder)
where !contains(file.folder, "4 - Archive")
where contains(type, "area")
where !contains(type, "sub-area")
sort priority
```
