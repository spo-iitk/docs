---
title : admin
layout : default
nav_order: 1
parent : cmd
---

# admin.go
This file defines mail service handler for the admin service.


The Go viper package is used to read the [config.yaml secrets file]() and get the port of the various administrator services. A new Go engine is initialized and the required middlewares are attached to it.


## function adminRCServer
It returns an http server instance of the adminRC server for reading and writing to the mail service.

{: .info} 
The adminRC service is hosted on port 3490.

### Middlewares Attached to the process
- [CORS]() : Custom middleware
- [Authenticator]() : Custom middleware
- [EnsurePsuedoAdmin]() : Custom middleware
- Recovery
- Logger

Initialized service is passed to [adminRC router]().

## function adminApplicationServer
Same as [adminRCServer]() except the fact the service is passed to [Application admin router]().

{: .info} 
The adminApplication service is hosted on port 3492.

## function adminCompanyServer
Same as [adminRCServer]() except the fact the service is passed to [Company admin router]().

{: .info} 
The adminCompany service is hosted on port 3495.

## function adminStudentServer
Same as [adminRCServer]() except the fact the service is passed to [Student admin router]().

{: .info} 
The adminStudent service is hosted on port 3500.

---
#### References
- [Go Engines]()
- [Go Logger middleware]()
- [Go recovery middleware]()
- [Go Viper module]()