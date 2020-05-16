+++
title = "Simple Notification Service"
chapter = false
weight = 10
pre = "<b>1. </b>"
+++

{{% notice warning %}}
Please be sure, that you are in US-EAST-1 Region.
{{% /notice %}}

#### First - Create S3 bucket

1. Log in to _Main_ account through *Training Accounts* url.
1. Go to AWS Management Console
1. Select S3
1. *Create bucket* -  
_xyzSAA-WS_ - as bucket prefix
{{% notice tip %}}
Bucket names are unique across whole AWS.
{{% /notice %}}
* Copy Bucket nam
{{% notice note %}}
Save your bucket name to a text file.
{{% /notice %}}
e 

#### Next - Create SNS Topic
1. Go to *Simple Notification Service*
1. Select *Topics* from left menu side.
1. Select *Create SNS Topic*
1. Put a *Name* (_remember about naming convetion_) and select *Create topic*
* Copy your SNS Topic ARN 

{{% notice note %}}
SNS Topic name to a text file.
{{% /notice %}}

1. Select *Edit* and go to *Access Policy* (_Select Advanced view if needed_)
Change SNS topic policy to allow S3 to publish to SNS

* Add a policy statement right after opening [
```json
{
  "Version": "2008-10-17",
  "Id": "__default_policy_ID",
  "Statement": [
```
```
{
    "Sid" : "s3events",
    "Effect" : "Allow",
    "Principal" : {
        "Service" : "s3.amazonaws.com"
    },
    "Action" : [
        "SNS:Publish"
    ],
    "Resource" : "arn:aws:sns:us-east-1:ACCOUNTID:SNSTOPICNAME",
    "Condition": {
        "ArnLike": {"aws:SourceArn": "arn:aws:s3:*:*:BUCKETNAME" } 
    }
},
```
Fill policy with your *Account ID*, *SNS Topic Name*, *Bucket Name*   
Select *Save Changes*  
  
* Select *Create subscription*
* Select *Email* in *Protocol* filed
* Type your REAL email address.
* Hit *Create Subscription

{{% notice note %}}
Go to your email box, to confirm subscription.
{{% /notice %}}

#### Go back to your S3 bucket

 1. Select S3
 1. Select your bucket 
 1. Select *Properties* -> *Events*
 1. Select *Add notification*
 1. Give it a name
 1. Select *All object create events* and *All object delete events*
 1. Select SNS Topic in *Send to* field
 1. Select your SNS Topic name
 1. Click *Save*
 
 Put an object to your S3 bucket, check your email box.
  
