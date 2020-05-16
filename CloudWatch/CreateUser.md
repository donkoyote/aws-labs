+++
title = "IAM Create user alarm"
chapter = false
weight = 20
pre = "<b>2. </b>"
+++

{{% notice warning %}}
Please be sure, that you are in US-EAST-1 Region.
{{% /notice %}}

#### Go to CloudWatch console

* Make sure, that you are in us-east-1 region.
* Select *Events* -> *Rules* -> *Create Rule*
* Select *Event Patern*
* As *Service Name* select *IAM*
* As *Event Type* select *AWS API Call using CloudTrail*
* Select *Specific operation(s)* and paste `CreateUser` into empty field.
* Add *Target*
* Select *SNS topic* and chose your _Topic_
* Again, select *Add* add, and select *SNS topic*, but this time expand *Configure input* 
* Select *Input Transformer*  and fill fields with data

First field
```json
{"User":"$.detail.requestParameters.userName","Creator":"$.detail.userIdentity.userName"}
```
Second field
```json
"ALERT! User: <User> was created by: <Creator>."
```
