---
title: company.proforma
layout: default
nav_order: 2
parent: Company
grand_parent: Application
---
## company.proforma.go
---
* It contains functions related to proforma for company.

#1
```go
func getProformaForCompanyHandler
```
* It is used to fetch proformas using a Company ID.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, the proformas are fetched from the CID using the function:
```go
func fetchProformasByCompanyForCompany(ctx, cid, &jps)
```
{: .info}

Here CID refers to Company ID

* This takes cid and an empty array of type Proforma as parameters.

Mentioned in [application/db.proforma]()

#2
```go
func postProformaByCompanyHandler
```
* It is used to create proformas using a Company ID.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, Company Recruitment Cycle is fetched using the function:
```go
func FetchCompany(ctx, cid, &companyRC)
```
Mentioned in [rc/db.company]()

Then, a proforma is created (also containing the company data filled using the above function) using the function:
```go
func createProforma(ctx, &jp)
```
* This takes a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

#3 
```go
func putProformaByCompanyHandler
```
* It is used to update proformas using a Company ID.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, the proforma is updated using the function:
```go 
func updateProformaForCompany(ctx, &jp)
```
* This takes a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

#4
```go
func deleteProformaByCompanyHandler
```
* It is used to delete proformas using a Company ID.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, the proforma is deleted using the function:
```go 
func deleteProformaByCompany(ctx, pid, cid)
```
* This takes Proforma ID and Company ID as parameter.

Mentioned in [application/db.proforma]()

#5
```go
func getProformaHandlerForCompany
```
* It is used to fetch a proforma using Proforma ID and Company ID.

First the company ID is fetched using the function:
```go
func getCompanyRCID
```
Mentioned in [application/util.company.middleware]()

A check is made to ensure that CID isn't 0.

Then, the proforma is fetched using the function:
```go
func fetchProformaForCompany(ctx, pid, cid, &jp)
```
* This takes Proforma ID, Company ID and a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()


