
```dataview
table
author as Author,
publisher as Publisher,
EndDate as FinishDate,
format as Format

from "BookNotes" 
where !contains(file.name, "Books") 
sort EndDate desc
```

