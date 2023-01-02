---
title: db.proforma
layout: default
nav_order: 2
parent: Database
grand_parent: Application
---
## db.proforma.go
---
* Contains DB functions for proforma.

#1
```go
func fetchProformasByCompanyForAdmin(ctx *gin.Context, cid uint, jps *[]Proforma) error 
```
* This is used to fetch proforma for Admin using Company ID and Proformas in the form of an  array of type Proforma from the DB.

#2
```go
func fetchProformaForCompany(ctx *gin.Context, pid uint, cid uint, jp *Proforma) error
```
* This is used to fetch proforma for Company using Company ID, Proforma ID and Proformas in the form of an  array of type Proforma from the DB.

#3
```go
func fetchProformasForStudent(ctx *gin.Context, rid uint, jps *[]Proforma) error 
```
* This is used to fetch proforma for student using RCID and Proformas in the form of an  array of type Proforma from the DB.

#4
```go
func fetchProformasByCompanyForCompany(ctx *gin.Context, cid uint, jps *[]Proforma) error 
```
* This is used to fetch proforma for company using Company ID and Proformas in the form of an  array of type Proforma from the DB.

#5
```go
func fetchProformaByRCForAdmin(ctx *gin.Context, rid uint, jps *[]Proforma) error 
```
* This is used to fetch proforma for admin using RCID and Proformas in the form of an  array of type Proforma from the DB.

#6
```go
func fetchProforma(ctx *gin.Context, pid uint, jp *Proforma) error
```
* This is used to fetch "a" proforma using Proforma ID and a Proforma in the form of a struct of type Proforma from the DB.

#7
```go
func fetchProformaForStudent(ctx *gin.Context, pid uint, jp *Proforma) error 
```
* This is used to fetch "a" proforma for student using Proforma ID and a Proforma in the form of a struct of type Proforma from the DB.

#8
```go
func fetchProformaForEligibleStudent(ctx *gin.Context, rid uint, student *rc.StudentRecruitmentCycle, jps *[]Proforma) error
```
* This is used to fetch proformas for student along with checking their eligibility using RCID, StudentRecruitmentCycle and Proforma in the form of an array of type Proforma from the DB.

#9
```go
func createProforma(ctx *gin.Context, jp *Proforma) error
```
* This is used to create a proforma using a Proforma in the form of a struct of type Proforma in the DB.

#10
```go
func updateProforma(ctx *gin.Context, jp *Proforma) error
```
* This is used to update a proforma using a Proforma in the form of a struct of type Proforma in the DB.

#11
```go
func updateHideProforma(ctx *gin.Context, jp *hideProformaRequest) error 
```
* This is used to update a proforma using a Proforma in the form of a struct of type hideProformaRequest in the DB.

#12
```go
func updateProformaForCompany(ctx *gin.Context, jp *Proforma) (bool, error)
```
* This is used to update a proforma for company using a Proforma in the form of a struct of type Proforma in the DB.

#13
```go
func deleteProforma(ctx *gin.Context, pid uint) error 
```
* This is used to delete a proforma for company using Proforma ID from the DB.

#14
```go
func deleteProformaByCompany(ctx *gin.Context, pid uint, cid uint) (bool, error)
```

* This is used to delete a proforma by company using Proforma ID and Company RCID from the DB.

#15
```go
func firstOrCreatePPOProforma(ctx *gin.Context, jp *Proforma) error
```
* This is used to create a proforma for PPO using a Proforma in the form of a struct of type Proforma in the DB.

#16
```go
func getEligibility(ctx *gin.Context, pid uint) (string, float64, uint, uint, error) 
```

* This is used to get eligibility and other information usind Proforma ID from the DB.

* It returns the eligibility (as a string), CPI cutoff (as a float), Company RCID (as uint) and the deadline (as uint).

#17
```go
func fetchRolesCount(ctx *gin.Context, rid uint) (int, error)
```

* This is used to fetch the number of approved roles count using RCID from the DB.

#18
```go
func fetchRecruitedCount(ctx *gin.Context, rid uint) (int, error)
```

* This is used to fetch recruited count (including both Recruited and PPOAccepted) using RCID from the DB.









