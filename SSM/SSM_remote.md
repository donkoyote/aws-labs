+++
title = "Instance login with SSM"
chapter = false
weight = 10
pre = "<b>1. </b>"
+++

#### Go to IAM and create Instance Role (Instructor led)

* Create a new *Role*
* Select *EC2* and *Next...*
* Search for   
`AmazonSSMFullAccess`  
`AmazonEC2RoleforSSM`   
* Select those policies and hit *Next ...*
* Fill up *Tags* and select *Next*
* Give the Role a *Name* and hit *Next*
* Check if everything is OK, then move to:

#### Go to EC2 Console

* *EC2* console
* Select your _instance_
* From menu *Actions* select *Instance Settings* and *Attach/Replace Instance Role*
* Select instance *IAM role* created in above step, and *Apply*

#### Go to Systems Manager Console
* On the left side of the screen under *Instances & Nodes*
* Select *Session Manager*
* Select *Start session*
* Find your instance, then hit *Start session*

#### Let's try another way to gain access to your's instance console

* Please check if you have already a proper setup of your aws profile 
* First execute `aws s3 ls --profile default` 
* If you can't see buckets created in previous labs, run `aws configure` command and configure it. 
* Take a note, of your running instance, the oone, you have attached roles to in earlier part of this lab. 
* Next, run `aws ssm start-session --target INSTANCEID --profile default --region REGION`


