## In inbox
```dataview
TABLE WITHOUT ID 
	
	file.link AS "", 
	
"[Move]" + "(obsidian://advanced-uri?&filepath=" + replace(file.path, " ", "%20") +
"&commandid=file-explorer%253Amove-file)"
AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
 
 WHERE contains(file.path, "Inbox") 
 where !contains(file.name, "Inbox")
	
LIMIT 99

SORT file.cdate
```

## Untitled & empty
```dataview
TABLE WITHOUT ID
	
		file.link AS "File",
		
		file.size	AS " size", 
	
	"[Move]" + "(obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20") +
	"&commandid=file-explorer%253Amove-file)"
		AS " ", 
	
	"["	
	+ "Delete"
	+ "]("
	+ "obsidian://advanced-uri?&filepath="
	+ replace(file.path, " ", "%20")
	+ "&commandid=app%253Adelete-file)"
	AS "  "
	
		
		
		
	FROM ""
	WHERE file.size = 0 OR file.name = "Untitled"
	SORT file.size ASC
```

