---
title: company.student
layout: default
nav_order: 3
parent: Company
grand_parent: Application
---
## company.student.go
---

```go
func getStudentsByEventForCompanyHandler
```
{: .info}

Here eid refers to Event ID and cid refers to Company ID.

* It is used to fetch students in an event of a company using eid and cid.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, an event is fetched using the function:
```go
func fetchEvent(ctx, eid, &event)
```
{: .info}

Here eid refers to event ID

* This takes eid and a stuct of type ProformaEvent as parameter.

Mentioned in [application/db.events]()

Then, the proforma is fetched from the proforma ID (fetched above) using the function:
```go
func fetchProforma(ctx, event.ProformaID, &proforma)
```
* This takes proforma ID and a stuct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

Then, an authorization check is made by confirming that CompanyRecruitmentCycleID fetched from the proforma matches with the cid.

Students in the event are fetched (to obtain RCID) using the function:
```go
func fetchStudentsByEvent(ctx, eid, &students)
```
* This takes event ID and an array of type EventStudent as parameter.

Mentioned in [application/db.student]()

Finally, the RCs of students are fetched using the function:
```go
func FetchStudents(ctx, studentRCIDs, &studentRCs)
```
* This takes student RCID and an array of type StudentRecruitmentCycle as parameter.

Mentioned in [rc/db.student]()
