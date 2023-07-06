---
title: admin.question
layout: dafault
nav_order: 6
parent: admin
grand_parent: rc
---
# admin.question.go

This file contains handler functions for admin requests to get and change student questions data of a particular RC.

## function getStudentQuestionsHandler
Returns all questions in a particular rc.

## function postStudentQuestionHandler
Creates a new question in the database.

## function putStudentQuestionHandler
handles request to update a question. If question id is not passed or invalid then corresponding error message is returned in response.

## function deleteStudentQuestionHandler
deletes requested question.
