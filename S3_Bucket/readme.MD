## Encryption types and differences

    - SSE-S3 is the simplest method – the keys are managed and handled by AWS to encrypt the data you have selected. You cannot see the key directly or use this key manually to encrypt or decrypt the data. AES-256 is used as the encryption algorithm. AES (Advanced Encryption Standard) is a symmetric block cypher, with 256 bit being the cryptographic key length. If you fully trust AWS, use this S3 encryption method.

    - SSE-KMS is a slightly different method from SSE-S3. AWS Key Management Service (KMS) is used to encrypt S3 data on the Amazon server side. The data key is managed by AWS, but a user manages the customer master key (CMK) in AWS KMS. The advantages of using the SSE-KMS encryption type are user control and audit trail.

## AWS Storage Types

    Amazon Simple Storage Service (Amazon S3)
    Amazon Glacier
    Amazon Elastic File System (Amazon EFS)
    Amazon Elastic Block Store (Amazon EBS)
    Amazon EC2 Instance Storage
    AWS Storage Gateway
    AWS Snowball
    Amazon CloudFront
    Amazon RDS




## S3 Bucket

### List Operations

- list out the S3 bucket
    aws s3 ls 
   
- List out the content of bucket 

    aws s3 ls s3://gaurav-test-today
    
- List all the files inside folder

    aws s3 ls s3://use-s3-gateway-prd --recursive
    
- Get the total objects count and total bucket size

     aws s3 ls s3://use-s3-gateway-prd --recursive --human-readable --summarize
     
     
### COPY / Move Operations

 - Copy a file from one bucket to another bucket

    aws s3 cp s3://use-s3-gateway-prd/index.html s3://anand-terraform-logs/index.html
    
 - Copy from Local to s3 bucket

    aws s3 cp test.txt s3://use-s3-gateway-prd
    
 - Recursively copying S3 objects (all contents of bucket) to a local directory
 
    aws s3 cp s3://gaurav-test-today . -- recursive

 - Move a file from one bucket to another

    aws s3 mv s3://gaurav-test-today/MyFile.txt s3://exmaple-today-bucket
    
    
### Create / Remove a Bucket

 - create a bucket in a region
    
    aws s3 mb s3://euw-s3-gateway-dev --region eu-west-1
    
 - Remove an empty bucket

    aws s3 rb s3://euw-s3-gateway-dev
    
 -  Remove a Non-empty bucket
 
    aws s3 rb s3://euw-s3-gateway-dev --force
    
### Remove file

 - Delete a file
    
    aws s3 rm s3://gaurav-test-today/HCI.txt
    
 - Recursively deletes all objects

    aws s3 rm s3://xyxyxyxyxyxyxyxyxxy --recursive
    
 - Delete everything except but with excluded files

    aws s3 rm s3://gaurav-test-today --recursive --exclude “*.jpg”

    
### SYNC the files

 - Sync from local to a bucket

     aws s3 sync /c/Users/Anand_Reddy/Desktop/website s3://use-s3-gateway-prd
     

### Configures a bucket named “my-bucket” as a static website

    aws s3 website s3://my-bucket/ --index-document index.html --error-document error.html
    
    
    
----------------------------------------------------------------------------------------------------------------------------------

## S3 Life Cycle Management

Cycle :

    S3 Standard storage class ( 30 days min to store here ) -> S3 Standard-IA -> S3 Intelligent-Tiering or S3 One Zone-IA -> S3 Glacier storage class (after 90 days files we can move to glacier ) -> S3 Glacier Deep Archive storage class ( 180 days ) -> Permanent Delete

Supported lifecycle transitions

    S3 Standard storage class –> other storage class.
    Any storage class –> S3 Glacier or S3 Glacier Deep Archive storage classes.
    S3 Standard-IA –> S3 Intelligent-Tiering or S3 One Zone-IA
    S3 Intelligent-Tiering storage class –> S3 One Zone-IA storage class.
    S3 Glacier storage class –> S3 Glacier Deep Archive storage class
    
Expiration Days ( Standards ): 

    

