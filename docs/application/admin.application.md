---
title: admin.application
layout: default
nav_order: 2
parent: admin
grandparent: Application
---
admin.application.go
---
#1 
```go
func getStudentsByProforma 
```
* It returns all the valid applicants under a proforma ID.

First, it fetch all the students from the pid using the function :
```go
func fetchApplicantDetails(ctx, pid, &applied) 
```
{: .info}
Here pid refers to Proforma ID

- This takes pid and an empty array of type ApplicantsByRole (applied) as parameters.


Mentioned in [db.application]()

Then it fetch all the students in the rc by srid taken from above function using the function:


```go
func FetchStudentBySRID(ctx, srids, &allStudentsRC)
```
Mentioned in [rc/db.student]()

#Check 1:
Are some students missing from the rc :

* Done by comparing the output of both the ways.

#Check 2:
Are some students missing from master:

* Done by comparing the output from the SRID path and from SID path.

{: .info}
Here SRID refers to Student RCID and SID refers to Student ID

For getting the students from SID path, we used the function:
```go
func FetchStudentByID(ctx, sid, &allStudents) 
```
* This takes sid and an empty array of type Student

Mentioned in [student/db]()

Finally it returns the valid applicants by verifying the questions using the function:
```go
func getAnswersForProforma(ctx, pid)
```
Mentioned in [application/admin.questions]()

#2
```go
func viewApplicationsAdminHandler
```
* It returns the applications of a student using its SID with the function:
```go
func fetchApplications(ctx, srid, &response)
```
* This takes SRID and an empty array of type ViewApplicationsResponse

Mentioned in [application/db.application]()


