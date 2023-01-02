---
title: db.student
layout: default
nav_order: 4
parent: Database
grand_parent: Application
---
## db.student.go
---
* Contains DB functions for students in application.

#1
```go
func createEventStudents(ctx *gin.Context, eventStudents *[]EventStudent) error 
```
* This is used to create event students using students in the form of an array of type EventStudent in the DB.

#2
```go
func getRecruitmentStats(ctx *gin.Context, rid uint, stats *[]statsResponse) error 
```
* This is used to get recruitment stats using RCID and stats in the form of an array of type statsResponse from the DB.

#3
```go
func fetchStudentRCIDByEvents(ctx *gin.Context, eventID uint) ([]uint, error) 
```
* This is used to fetch Student RCID using event ID from the DB.

#4
```go
func fetchStudentsByEvent(ctx *gin.Context, eventID uint, students *[]EventStudent) error
```
* This is used to fetch Student in event using event ID and student as an array of type EventStudent from the DB.

#5
```go
func getCurrentApplicationCount(ctx *gin.Context, sid uint) (int, error)
```
* This is used to get the current application count using the RCID.
