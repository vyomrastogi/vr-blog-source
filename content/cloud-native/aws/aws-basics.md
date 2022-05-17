---
title: "AWS Basics"
date: 2022-05-16T23:02:15-04:00
draft: false
weight: 1
---

## AWS IAM 

- An AWS account is created with a `root` account which has `admin` privileges. 
- IAM Group : is a collection of users who perform similar jobs on aws . IAM Policies can be attached to group
- IAM Policy: Provides permission to user to carry out allowed actions 
    - can be `Job Function` or `Aws Managed` or `Customer Managed`
- IAM Role : Allows aws services to securely access different services.

### AWS CLI Setup 
- Windows Chocolatey install `choco install awscli -y`
- To configure aws : `aws configure` . This requires user to configure following fields 
```
AWS Access Key ID [None]: _access key_
AWS Secret Access Key [None]: _secret_
Default region name [None]: us-west-2 //or any default region
Default output format [None]: json
```

### Commands 
- Format : `aws <command> <subcommand> [options & parameters]` 
- 

