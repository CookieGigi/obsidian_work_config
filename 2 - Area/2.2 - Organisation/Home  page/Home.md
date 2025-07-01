---
parent: "[[Home  page]]"
---
# Today 
```tasks
(due on or before today) 
not done
filter by function !task.file.folder.includes("liste de course")
filter by function !task.file.folder.includes("Archive")

group by status.name
group by function task.recurrenceRule.replace('when done', '==when done==')


sort by priority

```

# Réunion
```dataview
table file.path, date, location, link
WHERE file.cday = date(today)
WHERE contains(type, "réunion")
Where !contains(file.path, "Template")
```





# Quick link
- [[2 - Area/2.2 - Organisation/Task/Todo|Todo]]
- [[Planifier]]

```meta-bind-button
label: Quick Note
icon: ""
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: createNote

    fileName: Untitled
    openNote: true
    openIfAlreadyExists: false

```

