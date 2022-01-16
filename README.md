# AWS

### How to switch 2AWS accounts ? 

We want to allow a user whos IAM account there in AWS-Stage account to access the resources there in AWS-Prod account.

1. Create an IAM role ( Another AWS account role ) on AWS-Prod account.
   - Add the AWS-Stage account ID and grant the specific resource permissions.
   - Edit the Trust-Relationship policy and allow specific user/group to access that account.

2. Use Switch Role Option in your account and add the remote AWS account Id and its name ( prod ) in the options and click on Switch role.


### VPC flow Logs ?

VPC Flow Logs is a feature that enables you to capture information about the IP traffic going to and from network interfaces in your VPC. Flow log data can be published to Amazon CloudWatch Logs or Amazon S3. After you've created a flow log, you can retrieve and view its data in the chosen destination.


### Multiple Ip addresses ?

It can be useful to assign multiple IP addresses to an instance in your VPC to do the following:

    - Host multiple websites on a single server by using multiple SSL certificates on a single server and associating each certificate with a specific IP address.
    - Operate network appliances, such as firewalls or load balancers, that have multiple IP addresses for each network interface. 
    - Redirect internal traffic to a standby instance in case your instance fails, by reassigning the secondary IP address to the standby instance.

### Launch Template Vs Launch Configuration ? 

## Topics to learn
- Load Balancing and It types ??
- Auto Scaling ??
- EC2 types ??
- Code Build & Code Pipeline & Code Deploy ??
- ECR & ECS ??
- VPC ??
- EBS ??
- Lambda ??
- RDS ??
- Cloud Front ??
- Terraform ??

### Security Group Vs NACL
Screenshot 2022-01-15 at 5.09.44 PM<img width="1133" alt="image" src="https://user-images.githubusercontent.com/51190838/149620846-8e6a7ef2-8167-47a9-9008-fcea8f17bf15.png">


### VPC peering
Screenshot 2022-01-15 at 7.48.35 PM<img width="1641" alt="image" src="https://user-images.githubusercontent.com/51190838/149624934-87a2ecc3-f419-45b0-81dc-58ec01303074.png">

### ALB 
Screenshot 2022-01-16 at 8.47.20 AM<img width="1547" alt="image" src="https://user-images.githubusercontent.com/51190838/149646091-4f831cad-91fc-4a3f-8b4e-c3325fefb696.png">

### Launch Configuration Vs Launch Template


     -  Launch template is similar to launch configuration which usually Auto Scaling group uses to launch EC2 instances. 
      However, defining a launch template instead of a launch configuration allows you to have multiple versions of a template.

     - AWS recommend that we should use launch templates instead of launch configurations to ensure that we can leverage 
      the latest features of Amazon EC2, such as T2 Unlimited instances.

     - launch configurations are used with Auto Scaling Groups. While launch templates are used when you launch an instance 
       using the aws EC2 console, an AWS SDK, or a command line tool.

     - Launch templates enable you to store the parameters (AMI, instance type, security groups, and key pairs etc.) 
       so that you do not need to define these parameters every time you launch a new instance.
      
![image](https://user-images.githubusercontent.com/51190838/149654503-a24893db-7836-4837-a7c2-861f344d88f3.png)

