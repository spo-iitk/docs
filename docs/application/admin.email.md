---
title: admin.email
layout: default
nav_order: 4
parent: admin
---
## admin.email.go
```go
func proformaEmailHandler
```
* This is used to handle the mailing to students enrolled in an event.

In order to fetch the email ID of students enrolled in an event, first the RCID of students is fetched using the function:

```go
func fetchStudentRCIDByEvents(ctx, request.EventID)
```
* This takes the eventID from the request (i.e. a struct of type proformaEmailRequest) as a parameter

Mentioned in [application/db.student]()

Then, the email ID of students is fetched using the function: 
```go
func FetchStudentEmailBySRCID(ctx, studentRCID)
```
* This takes studentRCID as a parameter which was fetched in the previous step.

Mentioned in [rc/db.student]()

Finally, the mail is sent to  students using the mail channel.