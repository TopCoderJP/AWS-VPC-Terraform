AWS VPC - Terraform - Infrastructure as Code 
=========================================

 

Infrastructure Components | インフラコンポーネント
------------------------------------------------

This Terraform configuration deploys:

-   A basic AWS VPC with CIDR block 192.168.0.0/16
-   Multiple subnets across availability zones (ap-northeast-1a and ap-northeast-1c)
-   Internet Gateway for public internet access
-   Route table and associations for subnet connectivity


Remote State Management
-----------------------

This project uses remote state management with:

-   S3 bucket: "topcoder-state-bucket"
-   State file key: "global/s3/terraform.tfstate"
-   DynamoDB table: "terraform-lock-table" for state locking

  

Configuration Files 
-------------------

-   main.tf - Primary Terraform configuration that defines AWS resources including VPC, subnets, Internet Gateway, and route tables.
-   state.tf - Configuration for Terraform state management using S3 bucket for remote state storage and DynamoDB for state locking.




Usage | 使い方
--------------

To deploy this infrastructure:

```source-shell
# Initialize Terraform
terraform init

# Plan the deployment
terraform plan

# Apply the configuration
terraform apply

# To destroy the infrastructure
terraform destroy
```

Ensure that your AWS credentials are correctly configured before running these commands.
