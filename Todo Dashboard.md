---
cssclasses:
  - width-100
---


## Not done list
```dataview
task
WHERE !completed
AND status != "-"
AND !contains(text, "❌")
AND date(substring(file.name, 0, 10)) < date(today)
AND contains(file.path, "Daily Plan/20")
SORT contains(text, "🔺") DESC, contains(text, "⏫") DESC, file.name
```

## Calendar
```dataviewjs
await dv.view("5. Dev/tasksCalendar", {pages: "", view: "month", firstDayOfWeek: "1", options: "style1"})
```

