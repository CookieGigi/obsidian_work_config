---
cssclasses: 
type: directory-page
category: "[[1 - Project]]"
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
# Projets
```dataview
Table category, priority, deadline
where contains(file.folder, this.file.folder)
where !contains(file.folder, "4 - Archive")
where contains(type, "project")
sort priority
```
