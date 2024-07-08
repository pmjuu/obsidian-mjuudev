---
cssclasses:
  - width-100
---

Start of the Week: <%+ tp.user.currentWeek().startOfWeek %>
End of the Week: <%+ tp.user.currentWeek().endOfWeek %>

# work list
```dataview
TABLE WITHOUT ID 
(["-", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"][file.day.day]) as "DAY"
, DONE, NOT_DONE
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "work to do" & contains(x.text, "✅")).text) as DONE
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "work to do" & !contains(x.text, "✅")).text) as NOT_DONE
WHERE 1=1
AND contains(file.path, "Daily")
AND file.day.weekyear = this.file.day.weekyear
AND file.day.year = this.file.day.year
SORT file.day
```

# Daily retros
```dataview
TABLE KEEP, PROBLEM, TRY
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "KEEP").text) as KEEP
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "PROBLEM").text) as PROBLEM
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "TRY").text) as TRY
WHERE 1=1
AND contains(file.path, "Daily")
AND file.day.weekyear = this.file.day.weekyear
AND file.day.year = this.file.day.year
SORT file.day
```

---
## Keep
- 
## Problem
- 
## Try
- [ ] 