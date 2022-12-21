---
title : auth
layout : default
nav_order: 2
parent : cmd
---

# auth.go

This file configures the mail service handler for the authentication service.

## function authServer
It returns an http server instance of the started server for broadcasting content on the mail channel.

The Go viper package is used to read the [config.yaml configuration constants file]() and get the port of the authentication service. A new Go engine is initialized and the required middlewares are attached to it.

{: .info} 
The authentication service is hosted on port 3475. 

### Middlewares Attached to the process
- CORS - Cross-Origin Resource Sharing : Custom middleware defined in the middleware documentation
- Recovery (Standard Go middleware) : to recover from any panic
- Logger (Standard Go Middleware) : To log the status
- Gin middleware

Initialized service is passed to [auth router].

---
#### References
- [Go Engines]()
- [Go Logger middleware]()
- [Go recovery middleware]()
- [Go Viper module]()