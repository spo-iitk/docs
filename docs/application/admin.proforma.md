---
title: admin.proforma
layout: default
nav_order: 7
parent: Admin
grand_parent: Application
---
## admin.proforma.go
* This contains function related to proforma in applications.

#1
```go
func getProformaHandler
```
{: .info}

Here pid refers to Proforma ID

* Used to get Proforma from pid.

Proforma is fetched in a struct of type Proforma using the function:
```go
func fetchProforma(ctx, pid, &jp)
```
* This takes pid and a struct of type Proforma as parameters.

Mentioned in [application/db.proforma]()

#2
```go
func getProformaByCompanyHandler
```
{: .info}

Here cid refers to Company ID

* Used to get Proforma from cid.

All the proformas are fetched using the function:
```go
func fetchProformasByCompanyForAdmin(ctx, cid, &jps)
```
* This takes cid and an empty array of type Proforma as parameters.

Mentioned in [application/db.proforma]()

#3
```go
func getAllProformasHandler
```
{: .info}

Here rid refers to Recruitment Cycle ID

* Used to get proformas from rid.
All the proformas are fetched using the function:
```go
func fetchProformasByRCForAdmin(ctx, rid, &jps)
```
* This takes rid and an empty array of type Proforma as parameters.

Mentioned in [application/db.proforma]()

#4
```go
func putProformaHandler
```

* Used to update proformas.
First the old proforma is fetched using the pid of the same using the function:
```go
func fetchProforma(ctx, jp.ID, &oldJp)
```
{: .note}

This is done only for publishing a notice about the change, where we require RCID of the old proforma.

Mentioned in [application/db.proforma]()

Then, the proforma is updated using the function:
```go
func updateProforma(ctx, &jp)
```
* This takes a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

And finally, a notice is published regarding the change.

#5
```go
func hideProformaHandler
```

* Used to hide proformas.

The proforma is hidden using the function: 
```go
func updateHideProforma(ctx, &jp)
```
* This takes a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

#6
```go
func postProformaHandler
```

* Used to create proformas.

The proforma is created using the function: 
```go
func createProforma(ctx, &jp)
```
* This takes a struct of type Proforma as parameter.

Mentioned in [application/db.proforma]()

#7
```go
func deleteProformaHandler
```

* Used to delete proformas.

The proforma is deleted using the function: 
```go
func deleteProforma(ctx, pid)
```
* This takes pid as parameter.

Mentioned in [application/db.proforma]()

