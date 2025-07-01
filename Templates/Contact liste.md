---
cssclasses: 
type: contact-page
category: "[[<% tp.file.folder() %>]]"
---

```meta-bind-button
label: New contact
icon: plus
hidden: false
class: ""
tooltip: ""
id: ""
style: default
actions:
  - type: templaterCreateNote
    templateFile: Templates/Contact.md

    fileName: ""
    openNote: true
    openIfAlreadyExists: false

```
## Todo

```dataview
TASK
WHERE startswith(file.folder, this.file.folder)
```

## Contacts
```dataview
Table file.name, email, téléphone, fonction
WHERE contains(file.folder, this.file.folder)
WHERE type != "contact-page"
```
<%*
  // Rename file with the one choose by user
  const fileName = await tp.system.prompt("Title :")
  await tp.file.rename(fileName)
  
  const baseFolder = tp.file.folder(true)
  const newFolder = `${baseFolder}/${fileName}/`

  await tp.file.move(newFolder + fileName)
%>