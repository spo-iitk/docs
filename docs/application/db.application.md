---
title: db.application
layout: default
nav_order: 1
parent: Database
grand_parent: Application
---
## db.application.go
---
* Contains DB functions for application.

#1

```go
func fetchApplicationEventID(ctx *gin.Context, pid uint) (uint, error) 
```
{: .info}

Here pid refers to Proforma ID

* This is used to fetch application event ID using pid from the db.

#2

```go
func deleteApplication(ctx *gin.Context, pid uint, sid uint) error 
```
{: .info}

Here pid refers to Proforma ID and sid refers to student RCID

* This is used to delete applications using pid and sid from the db.

In order to delete an application, we need to delete the EventStudent, ApplicationQuestionAnswer, and ApplicationResume.

Hence first,response to application questions is fetched using the function:
```go
func fetchApplicationQuestionsAnswers(ctx, pid, sid, &questions)
```
* This takes Proforma Id, Student RCID and an empty array of type getApplicationResponse as parameters.

Mentioned in application/db.question

From this, the Question ID is fetched which is required to delete ApplicationQuestionAnswer.

Then, event Id is extracted from the event fetched using the function:

```go
func fetchEventsByProforma(ctx, pid, &events)
```
* This takes pid and an empty array of type ProformaEvent as parameters.

#3

```go
func createApplication(ctx *gin.Context, application *EventStudent, answers *[]ApplicationQuestionAnswer, resume *ApplicationResume) error
```
* This is used to create an application using EventStudent, ApplicationQuestionAnswer, and ApplicationResume in the db.

#4
```go
func createApplicationResume(ctx *gin.Context, resume *ApplicationResume) error 
```
* This is used to create an application resume using ApplicationResume in the db.

#5
```go
func fetchApplicantDetails(ctx *gin.Context, pid uint, students *[]ApplicantsByRole) error
```
* This is used to fetch applicant details using Proforma ID, an array of type ApplicantsByRole from the db.

#6
```go
func fetchApplications(ctx *gin.Context, sid uint, response *[]ViewApplicationsResponse) error 
```
* This is used to fetch applications using Student RCID and Application Response in the form of array of type ViewApplicationsResponse from the db.



