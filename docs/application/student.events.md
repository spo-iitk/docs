---
title: student.events
layout: default
nav_order: 2
parent: Student
grand_parent: Application
---
student.events.go
---
* Contains student related functions for events.

#1
```go
func getEventsByStudentHandler
```
* Used to get events using recruitment cycle id.

Events are fetched using the function:
```go
func fetchEventsByStudent(ctx, rid, &events)
```

* This takes RID and an empty array of type proformaEventStudentResponse as parameters.

{: .info}

Here, RID refers to recruitment cycle ID.

* Mentioned in [application/db.events]().

#2
```go
func getEventsByProformaForStudentHandler
```
* Used to get events using proforma ID.

Events are fetched using the function:
```go
func fetchEventsByProforma(ctx, pid, &events)
```

* This takes PID and an empty array of type ProformaEvent as parameters.

{: .info}

Here, PID refers to proforma ID.

* Mentioned in [application/db.events]().

