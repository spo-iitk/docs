---
title : cmd
layout : default
nav_order: 7
has_children: true
---

# main.go

A mail service is initialized and passed on to the following handlers and the errors are returned to the main function and logged by the logger. 

{: .info}
Mail read and write timeouts are defined to 5 seconds and 10 seconds respectively

The service is passed on to the following handlers. The handlers are defined in the [overview]({{ site.baseurl }}{% link docs/overview.md %}) for reference.

- Auth
- RAS
- Student
- Company 
- Admin RC
- Admin Application 
- Admin Student
- Admin Company

---
#### References
- [chan - Go Command](https://www.sohamkamani.com/golang/channels/)
- [errgroup](https://pkg.go.dev/golang.org/x/sync/errgroup)