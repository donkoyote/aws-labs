+++
title = "CLI"
chapter = false
weight = 20
pre = "<b>2. </b>"
+++

### AWS CLI
A command line interface, a way to interact with Amazon AWS APIs.  

1. Go to your training computer.
Open Terminal 
```
$ aws configure
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
Default region name [None]: us-west-2
Default output format [None]: json
```
Your **profile** and **credentials** files are in _~/.aws/_ directory

2. Go to ~/.aws/ directory and    
`cat config`   
then look at the credentials file entries   
`cat credentials`

### Check IAM
Run below commands and look at familiarize yourself with the output.

Check IAM users with access keys
```
aws iam list-access-keys
```

Check your username key **LastUsedDate**
```
aws iam get-access-key-last-used --access-key-id #PASTEYOURACCESSKEYID
```

Other commands to familiarize with  
  
A very usefull tool is **jq**
```
 aws iam list-access-keys  | jq -r '.[][].AccessKeyId'
```

Same example, but with natively supported **--query** option 
```
aws iam list-access-keys --query 'AccessKeyMetadata[*].AccessKeyId' --output text
```

Lets list more information about user
```
aws iam list-users --output text --query 'Users[*].[UserName,Arn,CreateDate,PasswordLastUsed,UserId]' --profile #USEPROFILENAME
```

### Extras
[AWS Env variables](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)  
[CLI usage outputs](https://docs.aws.amazon.com/cli/latest/userguide/cli-usage-output.html)  


