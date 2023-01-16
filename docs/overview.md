---
title : Overview
layout: default
nav_order: 2
---
# Overview
The application is divided into multiple sections and follows a sort of neomonolith architecture. The different sections of the application use separate ports for increased stability. A crash at one of the ports/handler leaves the others remain unaffected.

## RAS: 3470
This is the testing handler. It is used to get ping responses from the server. It is also used to test the connection to the mail controller.

## AUTH: 3475
This handler is responsible for authentication of the user. It is responsible for checking the credentials of the user and returning the appropriate response. It also handles the registration of new users.


## STUDENT: 3480
This handler has all the routes related to the student. It is responsible for handling the requests related to the student's application, profile, etc.

## COMPANY: 3485
This handler has all the routes related to the company. It is responsible for handling the requests related to the company's new job openings, notices, application status etc.

# ADMIN:
Overview of the admin handlers
## RC: 3490
This handler is responsible for handling the requests related to the RC. It is used by the admin to post notices, reminders, verify resumes and answers to rc questions.

## APP: 3492
This handler contains all the APIs related to the admin RC events, proformas, etc. It is used by the admin to verify the proforma, add new proforma, etc.
## COMPANY: 3495
This handler contains all the APIs related to the company. It is used by the admin to verify the company, add new company, etc.
## STUDENT: 3500
This handler contains all the APIs related to the student. It is used by the admin to verify the student, add new student, etc.

