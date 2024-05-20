---
cssclasses:
  - width-100
---

Start of the Week: <%+ tp.user.currentWeek().startOfWeek %>
End of the Week: <%+ tp.user.currentWeek().endOfWeek %>


# Daily retros
```dataview
TABLE KEEP, PROBLEM
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "KEEP").text) as KEEP
FLATTEN list(filter(file.lists, (x) => meta(x.section).subpath = "PROBLEM").text) as PROBLEM
WHERE 1=1
AND contains(file.path, "Daily Plan")
AND file.day.weekyear = this.file.day.weekyear
AND file.day.year = this.file.day.year
SORT file.day
```

---
# Keep
- 
# Problem
- 
# Try
- [ ] 