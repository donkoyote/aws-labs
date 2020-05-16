+++
title = "Create VPC"
chapter = false
weight = 10
pre = "<b>1. </b>"
+++


### Create a VPC using AWS Management Console
  
  

Let's log in to AWS Management Console and create EC2 Instance... 
 
### Create a VPC

From given list (will be delivered by Trainer):   
1. Select your region (if you don't know your region, please ask your Trainer),
1. Go to VPC section,
1. Select `Yours VPCs`
1. Hit button `Create VPC`
1. Give it a name: *Name tag* `JD-VPC`
1. in *IPv4 CIDR block* type your CIDR range ex. `10.1.0.0/16`
1. click `Create`

### Create Subnets

1. On the top of the screen, in *Filter by VPC:* field, select your VPC
1. Select `Subnets`
1. Select `Create subnet`
1. Give it a name: *Name tag* `JD-Private`
1. In *Select VPC* select yours newly created VPC.
1. In the field *IPv4 CIDR block*, type `10.x.1.0/24` - where x is yours seccond filed in the CIDR range you have provided to your VPC. ex. `10.1.1.0/24`
1. Repeate above steps and create `JD-Public` subnet with `10.x.2.0/24` block.

