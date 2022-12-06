---
title : mail
layout : default
nav_order: 11
---
# config.go 
This file initializes the mailer with the required constants. Viper is used to get the constants from [_config.yml]() and the [secrets file](). Logrus is used to log the status.

Following constants are initialized
- user
- sender : user + "@iitk.ac.in"
- pass : password
- host
- port
- webteam : email address of the web-team

{: .info}
user, password, webteam are defined in the secrets file.

---
# service.go
This file defines methods to build messages. 

Mail struct is defined with the standard mailing properties.
- To
- Subject
- Body

## Function BuildMessage
This method builds the message by setting the From, Subject, To and Signature properties of the body of the mail and returns the final body.

[Read the code here]()

{: .info}
All the recipients are put into BCC when the message is mass mailed.

## Function Service
This is the function started in [cmd]() as a Go routine for sending mails. The function receives the mail queue channel, builds the message of the mail using [BuildMessage function]() and sends the mail using the SMTP protocol.

Errors are logged by logrus.

{: .info}
The mail is forwarded to the webteam mail as well

--- 
# generate.go
This file takes all the properties of the mail and generates the final object of type Mail to be sent using the SMTP protocol.

- **Function GenerateMail** - to generate a single mail
- **Function GenerateMails** - to generate multiple mails

---
#### References
- [logrus middleware](https://pkg.go.dev/github.com/sirupsen/logrus#section-readme)
- [A Tour of Go](https://go.dev/tour/concurrency/1) - Do check this out
- [SMTP Documentation](https://pkg.go.dev/net/smtp)