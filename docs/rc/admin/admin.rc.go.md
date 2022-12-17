---
title: RC
layout: home
nav_order: 5
has_children: true
---
# admin.rc.go

contains handler functions for admin actions on a complete recruitment cycle

## function getAllRCHandler
Returns all the recruitment cycles in response.

## function postRCHandler
Used to post a new recruitment cycle which is then created in DB.

## function getRCHandler
Returns a single RC queried by rid (recruitment-cycle-id) passed in request query.

## function GetMaxCountfromRC
Returns the application count of all students enrolled in the rc.

## function editRCHandler
edits recruitment cycle from a put request
