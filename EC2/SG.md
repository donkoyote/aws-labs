+++
title = "Security Groups"
chapter = false
weight = 10
pre = "<b>1. </b>"
+++



1. Open AWS Management Console
1. Select your region
1. Go to *EC2*, *Security Groups* section under *Network & Security*
1. „Create a security group”
- In „Security group name” - be consistent with names, so „JD-DEV-EC2-SG”,   
{{% notice tip %}}
_Security Group name cannot be edited when it's created_.  
{{% /notice %}}
* In description filed, type what is the purpuse of this SG.  
* Select correct VPC (_The one you are going to place your EC2 instance in_).  
* Set new rules for HTTP traffic, and allow it from anywhere,  
* Add another ingress rule for SSH, strict to your IP, use "Use my IP" feature.  
5. Check if your SG was created correctly

