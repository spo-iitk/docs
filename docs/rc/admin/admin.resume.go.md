---
title: admin.resume
layout: dafault
nav_order: 8
parent: admin
grand_parent: rc
---
# admin.resume.go

## function getAllResumesHandler
Returns an array of all resumes present in the requested rc.

## function getResumesHandler
Returns an array of all resumes submitted by a particular student.

## function putResumeVerifyHandler
Handles resume verification requests for a particular resume. Verification status is updated in database and then mail is sent to the student to inform about the verification action.