---
title : router
layout : default
nav_order: 2
parent : admin
---
# router.go

This file declares the API routes and attaches middlewares related to rc to the adminRCServer, studentRCServer, companyRCServer.

Backend API documentation: [https://ras-docs.netlify.app/]

The middlewares attached to these servers are:
[rc util util.active_rc.middleware]()
[rc util util.student.middleware]()