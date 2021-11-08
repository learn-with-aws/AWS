# AWS

### How to switch 2AWS accounts ? 

We want to allow a user whos IAM account there in AWS-Stage account to access the resources there in AWS-Prod account.

1. Create an IAM role ( Another AWS account role ) on AWS-Prod account.
   - Add the AWS-Stage account ID and grant the specific resource permissions.
   - Edit the Trust-Relationship policy and allow specific user/group to access that account.

2. Use Switch Role Option in your account and add the remote AWS account Id and its name ( prod ) in the options and click on Switch role.
