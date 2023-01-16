---
title: admin.pio_ppo
layout: default
nav_order: 4
parent: Admin
grand_parent: Application
---
## admin.pio_ppo.go

* It is used to update the students with pio and ppo.

```go
func getEmptyProformaByCID
```
* This fetch an empty proforma of the company Id provided.

```go 
func postPPOPIOHandler
```
* This is used to do the task assigned, i.e to update the students with pio and ppo.

First, an empty proforma is fetched using the above function. Then,  the RCID of students is fetched using the emails from the request using the function:
```go
func FetchStudentRCIDs(ctx, rid, req.Emails)
```
{: .info}

Here rid refers to Recruitment Cycle ID

* This takes rid and emails as parameters.

Mentioned in [rc/db.student]()

Then, the student type is updated to "PIOPPOACCEPTED" using the function: 
```go
func UpdateStudentType(ctx, req.Cid, req.Emails, string(PIOPPOACCEPTED))
```
Mentioned in [rc/db.student]()

Then, an event is created for the same using the function
```go
func createEvent(ctx, &event)
```
* This takes a struct of type ProformaEvent as a parameter

Mentioned in [application/db.events]()

And, students are added to the event using the function:
```go
func createEventStudents(ctx, &ses)
```
* This takes the an array of type EventStudent as a parameter


