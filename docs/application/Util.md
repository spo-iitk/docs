---
title: Util
layout: default
nav_order: 6
parent: Application
has_children: true
---
* It contains all the utility functions required for an applicaiton

# util.calendar.go

#### 1.
```go
func deleteCalenderEvent(cID string, cevent *ProformaEvent) 
```
* Used to delete calendar event.
* Takes calendar ID string and a pointer of struct of type ProformaEvent as parameters.

#### 2.
```go
func insertCalenderEvent(event *ProformaEvent, proforma *Proforma, loc *time.Location, time_zone string, cID string) 
```
* Used to insert calendar event.
* Google Calendar event is also created using the function:

```go
func updateEvent(nil, event) 
```
Mentioned in [application/db.event]()

#### 3.
```go
func insertCalenderApplicationDeadline(proforma *Proforma, event *ProformaEvent)     
```
* Used to insert calendar application deadline.
* Takes pointer to a struct of type Proforma and another of type ProformaEvent.

#### 4.
```go
func getCalenderID(rid uint) (cID string)    
```
* Used to fetch calendar ID required for google calendar integration.
* Takes recruitment cycle ID and calendar ID as parameters.

# util.company_id.go 

#### 1.
```go
func extractCompanyID(ctx *gin.Context) (uint, error) 
```
* Used to extract company ID from user email.
* Uses the function:
```go
func FetchCompanyIDByEmail(ctx, user_email)  
```
- Mentioned in [company/db.hr]()

# util.student_rcid.go  

#### 1.
```go
func extractStudentRCID(ctx *gin.Context) (uint, error) 
```
* Used to extract student RCID from recruitment cycle id.
* User ID is fetched using the funciton:
```go
func GetUserID(ctx) 
```
 Mentioned in [middleware/authenticator.hr]()
* Then RCID is fetched using the function:
 ```go
func FetchStudentRCID(ctx, rid, user_email)
```
* This takes recruitment cycle ID and User ID as parameters.
 Mentioned in [middleware/authenticator.hr]()
 