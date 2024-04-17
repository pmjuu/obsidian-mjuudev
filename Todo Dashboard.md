---
cssclasses:
  - width-100
---


## Not done list
```dataview
task
WHERE !completed
AND status != "-"
AND file.cday < date(today) - dur(1 day)
AND contains(file.path, "Daily Plan")
SORT file.cday
```

## Calendar
```dataviewjs
await dv.view("5. Dev/tasksCalendar", {pages: "", view: "month", firstDayOfWeek: "1", options: "style1"})
```

