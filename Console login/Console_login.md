+++
title = "AWS Management Console"
chapter = false
weight = 10
pre = "<b>1. </b>"
+++

### AWS Management Console
The very first screen you will see, when you want to Access and manage Amazon Web Services. AWS Management Console is a simple and intuitive web-based user interface.  

Where the journey begins:  

* AWS Management Console URL: `https://console.aws.amazon.com/console` 
* Training Accounts access site link: `https://uolpl-training.awsapps.com/start`  

`123456789000` - SameName  
`123456789001` - SameNameAnother aka Another   
`123456789002` - SameNameMain aka Main - `https://namemain.signin.aws.amazon.com/console`

### Create a new user

Let's start with the **Main** account.
1. Log in to _Main_ account through *Training Accounts* url.
1. Go to _IAM_ console, users tab: [direct url](https://console.aws.amazon.com/iam/home?region=eu-central-1#/users)
1. Click *Add user*  
1. Fill User name field using the first letter of your name and whole surname.  
e.g. for John Doe username will be *jdoe*
1. For access type, select both **Programmatic access** and **AWS Management Console access**  
Unselect **Require password reset**, click **Next**
1. Go to **Attach existing policies directly** and select **AdministratorAccess**, click **Next**
1. Fill tags with "Name:YOURUSERNAME"
1. On the next page, review provided data, if all is OK, go to the **Next** page
1. **Important** - save provided CSV file and/or write down provided keys and password
1. Click **CloseNext**
1. LogOut from the AWS Management Console 
1. Log in using [**Main**](https://namemain.signin.aws.amazon.com/console) account url and new user credentials.
1. Confirm, that all is working fine and smoothly.


### Extras
* [Supported MFA devices](https://aws.amazon.com/iam/features/mfa/?audit=2019q1)  

