---
title : init.sql
layout : default
nav_order: 8
---

# init.sql

This file when run initializes all the databases with their respective admins.

```sql
CREATE ROLE applicationadmin WITH LOGIN PASSWORD 'b2Led2ke';
CREATE DATABASE application;
GRANT ALL PRIVILEGES ON DATABASE application TO applicationadmin;

CREATE ROLE authadmin WITH LOGIN PASSWORD 'b2Led2ke';
CREATE DATABASE auth;
GRANT ALL PRIVILEGES ON DATABASE auth TO authadmin;

CREATE ROLE companyadmin WITH LOGIN PASSWORD 'b2Led2ke';
CREATE DATABASE company;
GRANT ALL PRIVILEGES ON DATABASE company TO companyadmin;

CREATE ROLE rcadmin WITH LOGIN PASSWORD 'b2Led2ke';
CREATE DATABASE rc;
GRANT ALL PRIVILEGES ON DATABASE rc TO rcadmin;

CREATE ROLE studentadmin WITH LOGIN PASSWORD 'b2Led2ke';
CREATE DATABASE student;
GRANT ALL PRIVILEGES ON DATABASE student TO studentadmin;
```