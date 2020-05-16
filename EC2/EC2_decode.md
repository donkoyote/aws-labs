+++
title = "EC2 decode auth. message"
chapter = false
weight = 30
pre = "<b>3. </b>"
+++


#### Variables
* Instance ID: `ami-01a6e31ac994bbc09`  
* AWS Region: `eu-west-2`


### Lab

1. Configure a cli credentials (**a newly created user**) on your lab computer

1. Go to your CLI and create EC2 instance with _instance-type_ **t2.large**  
```bash
aws ec2 run-instances --image-id ami-01a6e31ac994bbc09 --instance-type t2.large --profile #YOUR_PROFILE_NAME --region eu-west-2
```

1. Decode the failure message using:
```bash
aws sts decode-authorization-message --encoded-message #PASTEHERE# --profile #YOUR_PROFILE_NAME --region #YOURREGION#
```
you can also use `file://path/to/message.file` instead of pasting encoded message.

