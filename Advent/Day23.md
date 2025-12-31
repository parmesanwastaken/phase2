# AWS Security - S3cret Santa
> Learn the basics of AWS enumeration.

## Task 1: Introduction
- I am asked to start the target machine
- Then STS token and credentials are talked about
- Then I am asked to run `aws sts get-caller-identity`

### Answers:
- Output shows `123456789012` as account

## Task 2: IAM: Users, Roles, Groups and Policies
- Overview on `IAM` and subtopics are talked about

### Answers:
- After reading we can conclude answer is `policy`

## Task 3: Practical: Enumerating a User's Permissions
- I am taught how to enumerate user and user policies using various commands provided in guide

### Answers:
- First I used command `aws iam list-user-policies --user-name sir.carrotbane`
- This gave me one result with policy name `SirCarrotbanePolicy`
- THis was the answer
- I also verified it works using command `aws iam get-user-policy --policy-name SirCarrotbanePolicy --user-name sir.carrotbane`

## Task 4: 
- I am taught how to enumerate roles
- Then I am shown various example commands to get further info
- Also assuming role is talked about

### Answers:
- By running `aws iam list-roles`, we get to know about `bucketmaster` role
- Then we can check perms using command `aws iam get-role-policy --role-name bucketmaster --policy-name BucketMasterPolicy`
- This shows other than the 2 mentioned in question we can also use action `ListAllMyBuckets`
- Also changed all tokens using `export` command

## Task 5:
- AWS's simple storage service or s3 is talked about
- We can use various commands to list content from buckets
- We already have access from previous task
- Thus by using commands provided in guide, we get the flag
