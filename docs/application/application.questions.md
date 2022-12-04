---
title: admin.questions
layout: default
nav_order: 6 
parent: admin
---
## admin.questions.go

* This contains function related to application questions

#1
```go
func getQuestionsByProformaHandler
```
{: .info}
Here pid refers to proforma ID

* Used to fetch questions from the pid using the function:
```go
func fetchProformaQuestion(ctx, pid, &questions)
```

         * This takes pid and an empty array of type 
           ApplicationQuestion as parameters. 
Mentioned in [application/db.question]()

#2
```go 
func postQuestionHandler
```
* Used to post proforma questions using the function :
```go 
func createProformaQuestions(ctx, &question) 
``` 
         * This takes struct of type 
           ApplicationQuestion as parameter.
Mentioned in [application/db.question]()

Also, checks are made so that no empty questions in posted.

#3 
```go
func putQuestionHandler
```
* Used to update proforma questions using the function :
```go 
func putProformaQuestions(ctx, &question) 
``` 
         * This takes struct of type 
           ApplicationQuestion as parameter.
Mentioned in [application/db.question]()

Also, a check is done to ensure that ID of the question is not 0.

#4
```go
func deleteQuestionHandler
```
* Used to delete proforma questions using the function :
```go 
func deleteProformaQuestions(ctx, qid) 
``` 
         * This takes qid (question id) as parameter.
Mentioned in [application/db.question]()

#5
```go 
func getAnswersForProforma
```
* Returns a map of answers to the application questions.
The function used to fetch answers is :
```go 
func fetchAllAnswers(ctx, pid, questionID, &answers)
```
         * This takes pid, qid (question id) and an empty 
           array of type ApplicationQuestionAnswer as parameter.
Mentioned in [application/db.question]()



