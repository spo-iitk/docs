---
title : config
layout : default
nav_order: 8
---

# config.yaml

This file is basically just a collection of all the environment variables that we are using in the ras-backend application.

```yaml
MAIL:
  HOST: "smtp.cc.iitk.ac.in"
  PORT: "25"
  # BATCH: 200
JWT:
  EXPIRATION:
    LONG: 5000
    SHORT: 200
OTP:
  EXPIRATION: 20
  SIZE: 6
DATABASE:
  HOST: "database"
  PORT: "5432"
  USER: "admin"
DBNAME:
  APPLICATION: "application"
  COMPANY: "company"
  RC: "rc"
  STUDENT: "student"
  AUTH: "auth"
PORT:
  RAS: 3470
  AUTH: 3475
  STUDENT: 3480
  COMPANY: 3485
  ADMIN:
    RC: 3490
    APP: 3492
    COMPANY: 3495
    STUDENT: 3500
```
- `MAIL` stores the host name and the port of the mailer.
- `JWT` stores the durations for the expiry for the Web Token.
- `OTP` stores the expiration time and the length of the OTP.
- `DATABASE` stores the host, port and username of the database.
- `DBNAME` stores the database names of various databases used.
- `PORT` stores all the ports used by their respective microservices.
