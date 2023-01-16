---
title: RC Admin-Resume handler functions
layout: home
nav_order: 5
has_children: true
---
# admin.resume.go

## function getAllResumesHandler
Returns an array of all resumes present in the requested rc.

## function getResumesHandler
Returns an array of all resumes submitted by a particular student.

## function putResumeVerifyHandler
Handles resume verification requests for a particular resume. Verification status is updated in database and then mail is sent to the student to inform about the verification action.