---
title : scripts
layout : default
nav_order: 15
---

# production.sh

This is a bash script that is made to run from the file [Dockerfile]() when the docker image is created for deployment.

```sh
git pull origin main --force
```
- pulls the latest commits/changes made on the RAS Website code.

```sh
go get -d -v ./...
go install -v ./...
```
- for installing all the dependencies.

```sh
service nginx start
```
- starts the nginx server.

```sh
go build -o server ./cmd
./server
```
- creates an executable go file named `server` by building the code in [main.go]() which is basically the program for the initialization of our server. then runs it.

# createDB.sh

```sh
#!/usr/bin/env bash

CreateDB() {
   echo "Creating DB $1"
   sudo -u postgres psql -c "CREATE ROLE $1admin WITH LOGIN PASSWORD 'b2Led2ke';"
   sudo -u postgres psql -c "CREATE DATABASE $1;"
   sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE $1 TO $1admin;"
   # echo "CREATE ROLE $1admin WITH LOGIN PASSWORD 'b2Led2ke';" >> container/init.sql
   # echo "CREATE DATABASE $1;" >> container/init.sql
   # echo "GRANT ALL PRIVILEGES ON DATABASE $1 TO $1admin;" >> container/init.sql
   # echo "" >> container/init.sql
}

sudo systemctl start postgresql
CreateDB application
CreateDB auth
CreateDB company
CreateDB rc
CreateDB student
```

- This file was created to run manually and hence isn't called from any other file.
- This file is run when manually provisioning the databases.

#### References
- [Postgres Documentation](https://www.postgresql.org/docs/)
- [Bash Reference](gnu.org/savannah-checkouts/gnu/bash/manual/bash.html)
