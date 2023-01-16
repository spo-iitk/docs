---
title: db.question
layout: default
nav_order: 3
parent: Database
grand_parent: Application
---
## db.question.go
---
* Contains DB functions for application questions.

#1
```go
func fetchProformaQuestion(ctx *gin.Context, pid uint, questions *[]ApplicationQuestion) error 
```
* This is used to fetch proforma questions using Proforma ID and Questions in the form of an array of type ApplicationQuestion from the DB.

#2
```go
func fetchAllAnswers(ctx *gin.Context, pid uint, questionID []uint, answers *[]ApplicationQuestionAnswer) error 
```
* This is used to fetch proforma question answers using Proforma ID, question ID and an empty array of type ApplicationQuestionAnswer from the DB.

#3
```go
func updateProformaQuestion(ctx *gin.Context, question *ApplicationQuestion) error
```
* This is used to update a proforma question using the Question in the form of a struct of type ApplicationQuestion in the DB.

#4
```go
func createProformaQuestion(ctx *gin.Context, question *ApplicationQuestion) error 
```
* This is used to create a proforma question using the Question in the form of a struct of type ApplicationQuestion in the DB.

#5
```go
func deleteProformaQuestion(ctx *gin.Context, qid uint) error 
```
* This is used to delete a proforma question using the Question ID from the DB.

#6
```go
func fetchApplicationQuestionsAnswers(ctx *gin.Context, pid, sid uint, questions *[]getApplicationResponse) error 
```
* This is used to fetch proforma question answers using Proforma ID, Student RCID and Questions in the form of an array of type getApplicationResponse from the DB.