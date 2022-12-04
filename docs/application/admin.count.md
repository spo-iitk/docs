---
title: admin.count
layout: default
nav_order: 3
parent: admin
---
## admin.count.go

```go 
func getApplicationCountHandler
```
{: .info} Here rid refers to Recruitment Cycle ID
* It returns the total role count and recruitment count in a rid.

Role count is fetched using the function:
```go
func fetchRolesCount(ctx, rid)
```
* This takes rid as a parameter

Mentioned in [application/db.proforma]()

Similarly, Recruitment Count is fetched using the function:
```go
func fetchRecruitedCount(ctx, rid)
```
* This also takes rid as a parameter

Mentioned in [application/db.proforma]()
