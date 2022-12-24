---
title : secrets.yml.template
layout : default
nav_order: 8
---

# secret.yml.template

This file just contains the template of the `secret.yml` file which is contains the credentials for the mailer and the database access.

```yml
MAIL:
  USER: "ias"
  PASS: ""
  WEBTEAM: "spowebteam@gmail.com"
JWT:
  PRIVATE_KEY: "pretty-big-secret"
DATABASE:
  PASSWORD: "b2Led2ke"
CALENDAR:
  CID1: ""
  CID2: ""
```
- The file `secret.yml` is stored on the local system with the actual login credentials.
- The `secret.yml` file can be seen in the `Dockerfile`.

```dockerfile
RUN cp $GOPATH/src/github.com/spo-iitk/ras-backend/secret.yml.template $GOPATH/src/github.com/spo-iitk/ras-backend/secret.yml
```
- When the docker image is created, this local file is copied into the template and thus the docker image will have the actual secret credentials that we want it to have.
