---
title: company.application
layout: default
nav_order: 1
parent: Company
grand_parent: Application
---
## company.application.go
---

```go 
func getStudentsForCompanyByRole
```
*  It returns all the valid applicants under a proforma ID for company.

First, the applicants for the company are fetched using the function:
```go
func fetchApplicantDetails(ctx, pid, &applied)
```
{: .info}

Here pid refer to Proforma ID

* This takes pid and an empty array of type ApplicantsByRole.

Mentioned in [application/db.application]()

Then, all the students are fetched based on their SRID using the function :
```go
func FetchStudentBySRID(ctx, srids, &allStudentsRC)
```
* This takes Student RCID and an empty array of type StudentRecruitmentCycle.

Mentioned in [rc/db.student]()

Then, for checking the validity of applicants, the response from company side is matched with the data from RC.

Also, a check of IsFrozen is made at the start.

{: .note}

IsFrozen checks whether the student can continue in the process or not.

And, finally, the valid applicants are returned.
