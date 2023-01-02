---
title: student.proforma
layout: default
nav_order: 3
parent: Student
grand_parent: Application
---
student.proforma.go
---
* Contains student related functions for proforma.

#1
```go
func getProformasForStudentHandler
```
* Used to get proformas using recruitment cycle id.

Student RCID is fetched using the function:
```go
func getStudentRCID(ctx)
```
* Mentioned in [application/util.student.middleware]().

{: .info}

Here SID refers to Student RCID.

A student recruitment cycle is fetched using the funciton:
```go
func FetchStudent(ctx, sid, &student)
```

* This takes SID and an empty array of type StudentRecruitmentCycle as parameters.

{: .info}

Here, SID refers to student RCID.

* Mentioned in [rc/db.student]().

Finally, the proformas are fetched using the function:
```go
func fetchProformaForEligibleStudent(ctx, rid, &student, &jps)
```

* This takes RID , an empty array of type StudentRecruitmentCycle and an empty array of type Proforma as parameters.

{: .info}

Here, RID refers to recruitment cycle ID.

* Mentioned in [application/db.proforma]().

#2
```go
func getProformaForStudentHandler
```
* Used to get a proforma using proforma id.

Proforma is fetched using the function:
```go
func fetchProformaForStudent(ctx, pid, &jp)
```

* This takes PID and an empty array of type Proforma as parameters.

{: .info}

Here, PID refers to proforma ID.

* Mentioned in [application/db.proforma]().


