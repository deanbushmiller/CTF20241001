# CTF20241017

## 20241011 HASH for ALL SUBMISSIONS
	All hash value submissions must be in specific format stated at the beginning of the competition.
 	Use the built in tool gtkhash and changing the settings to match the CTF requirements for speed.
  	You will only login to the CTF posting site from within the guac/kali instance.
   	For CTF scoreboard if you see the button "submit query" you are not in kali. 
	User/pass will be supplied at the start in private chat.

## For in competition updates, twist & hints please keep the wiki open.
https://github.com/deanbushmiller/CTF20241001/wiki


# AWS Lab Environment Deployment Guide
	You will not need to install any software locally to run this lab.
	You will need an AWS account and a creditcard on file with Amazon.
	This will cost less than two dollars per hour while it is running
	VERSION: 20241011.01
## 9 minute video walk-thru of lab setup & tear down https://vimeo.com/941430484

### AWS account
	To build your AWS account consider using a non-work / disposable email adddress.
	You cannot use a one-time use email address.
	https://portal.aws.amazon.com/billing/signup#/start/email
### Choose a region
*	In order track costs easily deploy in an empty region (where no other machines are deployed).
#### Run this test to determine your closest region:
*	https://cloudpingtest.com/aws
*	Less than 200 ms is optimal.
### Create SSH keypair in EC2
1. Login to the AWS Console
2. In left sevices search type key pairs
3. On right click "create key pair"
 - This is used to create an SSH key pair for connecting to the attacker machine in emergencies.
4. Name your key 'lab' and append today's date, Example 'lab20240430'
 - Windows = .ppk / Everyone else .pem
5. Click create key pairs.
 - The key will automatically download
## Resource Deployment
1. Search for CloudFormation in service
2. On right Click Create Stack > With New Resources (standard)
4. Template source: https://20240311-drb-ctf.s3.amazonaws.com/CAP-flag-20241016v1.yml
5. Click Next
6. Fill in the parameters
 - Name stack:
   - Same as key pairs from above
   - Must start with letters and have no spaces
 - PublicIpAddress:
   - Your public IPv4 address. ( https://whatismyipaddress.com/ )
 - SSHKeyPair:
   - key pair you created before will be listed in the drop down
6. Click Next
7. Scroll to bottom: you must CHECK I acknowledge that AWS CloudFormation might create IAM resources.
8. Click (Create stack)
### Wait 5 min
It will take up to 5 minutes for the resources to be created
### Connecting to Guacamole
1. Search for EC2 console at top of AWS interface / click Instances and sub menu Instances / right side will show your running machines
2. Identify the guacamole public IP address
- Name of instance will say "This-Pub-IP-ADDRESS-GUAC"
3. Copy & Paste IP into your browser
4. Login kali with password kali
- the first time this console loads it might take 5 minutes for the interface to display
### Smile your lab is ready

## Cleaning Up
When you are done using the solution, you will want to tear down the resources you built in order to prevent unwanted costs in your AWS account.

### You will CONTINUALLY incur charges from AWS if you DO NOT clean up
Stopping instance will REDUCE charges and allow you to do the lab on your own.

### CloudFormation clean up
1. Go to AWS CloudFormation
2. Select the stack name you built and click Delete. 
- This will delete all resources for the solution
- At this point, your account is clear of all resources created by this solution.

# FILES
## They are not perfect, if you have constructive ideas on improvement email me.
## You do not need these files to attend class.
## I do make changes and trim down these files at class time due to the compressed schedule 

