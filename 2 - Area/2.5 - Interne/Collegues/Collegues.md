---
cssclasses: 
type: contact-page
category: "[[2.5 - Interne]]"
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
