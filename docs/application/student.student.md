---
title: student.student
layout: default
nav_order: 4
parent: Student
grand_parent: Application
---
student.student.go
---
* Contains student related functions for student.

#1
```go
func getStudentsByEventForStudentHandler
```
* Used to fetch students using event id.

First, the event is fetched using the function:
```go
func fetchEvent(ctx, eid, &event)
```

* This takes EID and an empty array of type ProformaEvent as parameters.

{: .info}

Here, EID refers to event ID.

* Mentioned in [application/db.events]().

Then, a check is made to ensure that the event has started.

Students are fetched using the function:
```go
func fetchStudentsByEvent(ctx, eid, &students)
```

* This takes EID and an empty array of type ProformaEvent as parameters.

{: .info}

Here, EID refers to event ID.

* Mentioned in [application/db.student]().

Finally, the student recruitment cycle is fetched using the function:
```go
func FetchStudents(ctx, studentRCIDs, &studentRCs)
```

* This takes student RCIDs and an array of type StudentRecruitmentCycle as parameters.

* Mentioned in [application/db.student]().



