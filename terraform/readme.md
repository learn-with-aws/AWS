## terraform

- terraform init  --> to install required plugin's 
    
    Ex : I am using AWS as provider then you need to install AWS plugin located at "registry.terraform.com/hasicorp/aws"

- terraform plan  --> for running as dry run mode

    terraform plan -out output.tf   --> you can store the plan in one file and use that file for launching the servers|VPC etc
    
    terraform apply output.tf 
    
- terraform apply  --> for creating the resources
  
