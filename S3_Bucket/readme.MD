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

    
