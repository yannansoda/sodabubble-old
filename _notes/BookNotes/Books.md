
```dataview
table
author as Author,
publisher as Publisher,
EndDate as FinishDate,
format as Format

from "BookNotes" 
where !contains(file.name, "BookList") 
sort EndDate desc
```

