+++
title = "EC2 create instance"
chapter = false
weight = 20
pre = "<b>2. </b>"
+++

### Create EC2 instance.

*Amazon EC2 - Linux Server (Hands on Lab)*

1. Open AWS Management Console
1. Select your region
1. Go to *EC2* section
1. Select *Launch Instance*
1. From available instance chose the first one *Amazon Linux 2 AMI (HVM)*, and chose *Select*
1. From available *Instance Type's* list, select „t2.micro” and click *Next: Configure…* 
* Make sure, that *Network* is set to „Default VPC”  
* Check if „Auto-assign Public IP” is set to „enable”  
* „Next: Add Storage”,  
7. On the bottom of this page, open *Advanced Details*
* in *User data* field, paste
```bash
#!/bin/bash
yum -y update
yum -y install httpd 
systemctl start httpd
systemctl enable httpd
INSTANCE_ID=$(curl -s http://169.254.169.254/latest/meta-data/instance-id)
echo "Instance: $INSTANCE_ID" > /var/www/html/index.html
```

8. leave all EBS settings  as they are and click „Next: Add Tags”
1. Create tags using privided values:  
* Key: „Owner”, Value: „YOURUSERNAME”    
* Key: „Name”, Value: „JD-DEV-EC2-1” - _FirstLettersNameSurname_-_Environment_-_Instance_-_Instance ID_  
* Key: "Environment", Value: "Development"  
„Next: Configure…”  
10. On *Security Group* page, 
* select security group, created in previous task
* then, chose „Review and Launch”
11. Quick review, if there are any mistakes, and click „Launch”
1. Chose „Create a new key pair”
* Use JD-EC2-Linux, where WS need to be replaced with your initials
* „Download key pair” - store and do not delete :)
13. Go with „Launch”

In AWS Management Console, please monitor how your instance status is changing while the creation process continues.
Check, by using instance domain name or public IP, if your HTTPD server is up and running.

#### When our instance is up and running, lets gain some information.   

First, decribe instance with different outputs types: table, json, text   
```bash
aws ec2 describe-instances --region=#WHATISYOURREGION --output=table
```

Next, lets describe its volumes   
```bash
aws ec2 describe-volumes --region #WHATISYOURREGION
```

Create another volume for your instance   
```bash
aws ec2 create-volume --size 80 --region us-east-1 --availability-zone us-east-1a --volume-type gp2
```

If you want to check if your key is the one used by instance, check its fingerprint.   
```bash
openssl rsa -in jdow.pem -pubout -outform DER | openssl md5 -c
```




### Extras

Find your public key from instance metadata:
`https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html`
