---
parent: "[[<%tp.file.folder()%>]]"
---


## New task


## Task 

## Task complete today
```tasks
filter by function task.done.format("YYYY-MM-DD") === "{{query.file.filenameWithoutExtension}}"
filter by function !task.file.folder.includes("liste de course")

group by function task.file.folder.slice(0, -1).split('/').pop() + '/' + task.file.filenameWithoutExtension + (task.hasHeading ? (' > ' + task.heading) : '')
```

## New Notes
```dataview
List file.path
WHERE file.cday = this.file.day
```

## Pomodoro
