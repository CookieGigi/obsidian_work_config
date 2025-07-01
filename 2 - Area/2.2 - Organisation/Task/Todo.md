---
parent: "[[Task]]"
---


```tasks
not done
filter by function !task.file.folder.includes("liste de course")

group by function \
    const date = task.due.moment; \
    const tomorrow  = moment().add(1,'days'); \
    const now = moment(); \
    const label = (order, name) => `%%${order}%% ==${name}==`; \
    if (!date)                           return label(5, 'Undated'); \
    if (!date.isValid())                 return label(0, 'Invalid date'); \
    if (date.isBefore(now, 'day'))       return label(1, 'Overdue'); \
    if (date.isSame(now, 'day'))         return label(2, 'Today'); \
    if (date.isSame(tomorrow, 'day'))    return label(3, 'Tomorrow'); \
    return label(4, 'Future');
group by function task.file.folder.slice(0, -1).split('/').pop() + '/' + task.file.filenameWithoutExtension + (task.hasHeading ? (' > ' + task.heading) : '')
```















