---
title: admin.student
layout: dafault
nav_order: 9
parent: admin
grand_parent: rc
---
# admin.student.go

This file contains handler functions for admin requests to get and change student data of a particular RC

## function getAllStudentsHandler
Returns an array of all students registered in a reruitment cycle.

## function getStudentsHandler
Returns information of a single student requested by passing the sid as query parameter.

## function putStudentHandler
Updates student information requested by passing the sid as query parameter. If no or invalid sid is passed corresponding error is returned in response.

## function bulkFreezeStudentsHandler
Freezes all the students whose email id is present in the request. Request object contains freeze status and string of email-ids in csv format. Invalid emails are reported in the error message of response.
After updating frozen status in db, email is sent to the concerned students informing their account is frozen.

## function postStudentHandler
Adds all requested students in the requested recruitment cycle. The request body object contains all requested student's email in a string in CSV format. The information of the students is extracted from the student's master database.
An email is sent to all the concerned students informing their registration in the rc.

## function deleteStudentHandler
Removes student informaiton form database, requested by passing the sid in query parameter.