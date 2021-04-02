## S3 Bucket

- list out the S3 bucket
    aws s3 ls 
   
- List out the content of bucket 

    aws s3 ls s3://gaurav-test-today
    
- List all the files inside folder

    aws s3 ls s3://use-s3-gateway-prd --recursive
    
- Get the total objects count and total bucket size

     aws s3 ls s3://use-s3-gateway-prd --recursive --human-readable --summarize
     
 - Copy a file from one bucket to another bucket

    aws s3 cp s3://use-s3-gateway-prd/index.html s3://anand-terraform-logs/index.html
    
 - Copy from Local to s3 bucket

    aws s3 cp test.txt s3://use-s3-gateway-prd
