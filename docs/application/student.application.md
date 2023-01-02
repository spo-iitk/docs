---
title: student.application
layout: default
nav_order: 1
parent: Student
grand_parent: Application
---
student.application.go
---
* Contains student related functions for application.

#1
```go
func getApplicationHandler
```
* Used to get application questions' answers  using proforma id.

First, Student RCID is fetched using the function:
```go
func getStudentRCID(ctx)
```
* Mentioned in application/util.student.middleware.

{: .info}

Here SID refers to Student RCID.

Then, a check is done to ensure that SID isn't zero.

Finally, the response to application questions is fetched using the function:

```go
func fetchApplicationQuestionsAnswers(ctx, pid, sid, &questions)
```
* This takes pid, sid, and an empty array of type getApplicationResponse as parameters.

#2
```go
func postApplicationHandler
```
* Used to post application using proforma id.

First, the application event ID is fetched using the function:
```go
func fetchApplicationEventID(ctx, pid)
```

* This takes PID as a parameter.

Then, Student RCID is fetched using the function:
```go
func getStudentRCID(ctx)
```
* Mentioned in application/util.student.middleware.

{: .info}

Here SID refers to Student RCID.

Also, a check is done to ensure that SID isn't zero.

Proforma eligibility, CPI eligibility, Company ID and deadline are fetched from PID using the function:

```go
func getEligibility(ctx, pid)
```

* This takes PID as a parameter.

Then, final student eligibilty is checked using the function:
```go
func GetStudentEligible(ctx, sid, proformaEligibility, cpiEligibility)
```
* This takes Student RCID , Proforma eligibility, CPI eligibilityas parameters.

Then, total number of applications are obtained using the function:
```go
func getCurrentApplicationCount(ctx, sid)
```
* Mentioned in [application/db.student]().

A check is done so that the total application count is less than maximum which is obtained using the function:
```go
func GetMaxCountfromRC(ctx)
```

* Mentioned in [rc/admin.rc]().

Also, the time is checked to confirm that the deadline hasn't passed.

Application Question answers are filled in an array of type ApplicationQuestionAnswer.

Resume link is fetched using the function:
```go
func FetchResume(ctx, request.ResumeID, sid)
```
{: .info}

 Here, request is a struct of type postApplicationRequest and sid refers to Student RCID.

* Mentioned in [rc/db.resume]().

Finally, application is created using the function:'
```go
func createApplication(ctx, &application, &answers, &resume)
```

* This takes a struct of type EventStudent, an array of type ApplicationQuestionAnswer and a struct of type ApplicationResume as parameters.

#3
```go
func postApplicationHandler
```
* Used to delete application using proforma id.


Deadline is fetched from PID using the function:

```go
func getEligibility(ctx, pid)
```

* This takes PID as a parameter.

A check is made to ensure that the deadline hasn't passed.

Then, Student RCID is fetched using the function:
```go
func getStudentRCID(ctx)
```
* Mentioned in [application/util.student.middleware]().

{: .info}

Here SID refers to Student RCID.

Then, the application is deleted using the function:
```go
func deleteApplication(ctx, pid, sid)
```

* This takes PID and SID as parameters.
* Mentioned in [application/db.application]().

#4
```go
func getEventHandler
```
* Used to get event using event id.

Event is fetched using the function:
```go
func fetchEvent(ctx, eid, &event)
```

* This takes EID and an empty array of type ProformaEvent as parameters.

{: .info}

Here, EID refers to event ID.

* Mentioned in [application/db.events]().

#5
```go
func viewApplicationsHandler
```
* Used to view application using student RCID.

Student RCID is fetched using the function:
```go
func getStudentRCID(ctx)
```
* Mentioned in [application/util.student.middleware]().

{: .info}

Here SID refers to Student RCID.

Then, applications are fetched using the function:
```go
func fetchApplications(ctx, sid, &response)
```

* This takes SID and an empty array of type ViewApplicationsResponse as parameters.

{: .info}

Here, SID refers to student RCID.

* Mentioned in [application/db.application]().






