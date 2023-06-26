# AWS Storage 

## AWS Storage Types
1. AWS S3 -> Cloud Object storage
2. AWS S3 Glacier -> Archive storage 
3. EFS -> Managed file storage for EC2
4. EBS -> Block storage
5. AWS Backup -> AWS backup centrally Manages and automates backup across AWS services. 
6. Storage Gateway -> Hybrid storage integration
7. AWS RDS -> DataBase Storage 
8. AWS Snowball, Sonwball Edge, Snow Mobile
9. AWS CloudFront
10. AWS Elastic Disaster Recovery -> Scalable, cost-effective application recovery to AWS 
11. FSx -> Fully managed third-party file systems optimised for a varity of workloads


## AWS S3
Amazon Simple Storage Service (Amazon S3) is an object storage service offering industry-leading scalability, data availability, security, and performance.

  - Durability:  S3 provides 99.999999999 percent durability.
  - Low cost: S3 lets you store data in a range of “storage classes.” These classes are based on the frequency and immediacy you require in accessing files. 
  - Scalability: S3 charges you only for what resources you actually use, and there are no hidden fees or overage charges. You can scale your storage resources to easily meet your organization’s ever-changing demands.
  - Availability: S3 offers 99.99 percent availability of objects
  - Security: S3 offers an impressive range of access management tools and encryption features that provide top-notch security.
  - Flexibility: S3 is ideal for a wide range of uses like data storage, data backup, software delivery, data archiving, disaster recovery, website hosting, mobile applications, IoT devices, and much more.
  - Simple data transfer: You don’t have to be an IT genius to execute data transfers on S3. The service revolves around simplicity and ease of use.

### S3 Limitations

  1. <b>Cannot change Bucket ownership</b> : An Amazon S3 bucket is owned by the AWS account that created it. Bucket ownership is not transferable to another account.
  2. <b>Not able to change Name and Region</b> : When you create a bucket, you choose its name and the AWS Region to create it in. After you create a bucket, you can't change its name or Region.
  3. <b>We can create Max 100 buckets</b> :  By default, you can create up to 100 buckets in each of your AWS accounts. If you need additional buckets, you can increase your account bucket limit to a maximum of 1,000 buckets by submitting a service limit increase
  4. <b>Max 5TB object storage and 5GB as a single part upload</b> : Individual Amazon S3 objects can range in size from a minimum of 0 bytes to a maximum of 5 terabytes. The largest object that can be uploaded in a single PUT is 5 gigabytes. For objects larger than 100 megabytes, customers should consider using the Multipart Upload capability.

### Scenarios : 
<b>1. Create a S3 policy to give access to specific CIDR range and restrict one IP out of it.</b>


<b>2. Make S3 bucket Public with S3 Policy</b>

- First, Disable "Block public access" in permissions.
- Gernerate a Bucket policy from policy generator 
```
              {
                "Id": "Policy1687754937482",
                "Version": "2012-10-17",
                "Statement": [
                  {
                    "Sid": "Stmt1687754934648",
                    "Action": [
                      "s3:GetObject"
                    ],
                    "Effect": "Allow",
                    "Resource": "arn:aws:s3:::hpc-dev-1/*",
                    "Principal": "*"
                  }
                ]
              }
```