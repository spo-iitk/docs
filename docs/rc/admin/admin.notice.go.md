---
title: admin.notice
layout: dafault
nav_order: 5
parent: admin
grand_parent: rc
---
# admin.notice.go

Contains handler function for admin action on notices

## function getAllNoticesHandler
returns an array of all notices present in a rc.

## function postNoticeHandler
crreates a new notice.

## function putNoticeHandler
updates an existing notice.

## function deleteNoticeHandler
deletes a notice present in db

## function postReminderHandler
handles request to send a particular reminder through email to all unfrozen students only if last reminder was sent atleast 6 hours brfore.
