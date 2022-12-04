---
title: admin.student
layout: default
nav_order: 7 
parent: admin
grandparent: Application
---
## admin.student.go

* This contains function related to application students.

#1
```go 
func getStudentsByEventHandler
```
* Used to get an array of student RCs enrolled in an event.

First, students are fetched from Event Id using the function: 
```go 
func fetchStudentsByEvent(ctx, eid, &students)
```
Mentioned in [application/db.student]()

Then, student RCs are fetched from the studentRCIDs using the function:

```go 
func FetchStudents(ctx, studentRCIDs, &studentRCs)
```
Mentioned in [rc/db.student]()
