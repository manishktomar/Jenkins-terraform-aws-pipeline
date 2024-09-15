# Jenkins Terraform AWS Pipeline
Jenkins, AWS, terraform and Github pipeline

## Explanation:
- **provider.tf**: Specifies the AWS provider and uses the AWS region defined in variables.tf.
- **variables.tf**: Stores variable definitions, such as instance type, key name, AMI ID, and region.
- **main.tf**: Contains the resource block to create an EC2 instance. It uses variables for flexibility and defines tags for better management.
- **output.tf**: Outputs useful information like the EC2 instance's public IP and instance ID after it is created.

## AWS IAM Policy for Terraform
- User Name = CICD-User
- AWS Credential Type = Access Key 
- Attach Policy = Administration Access       // You can change any other policy.
- Access Key and Secret Key                   // Required for Terraform.

## Jenkins Credential Setup

Add Access Key and Secret Key on Jenkins Credential
- Manage Jenkins >  Credential > System > Global
- Kind = Secret Text || Name = AWS_ACCESS_KEY_ID
- Kind = Secret Text || Name = AWS_SECRET_ACCESS_KEY

    ```
    environment {
            // Define environment variables for AWS Keys
            AWS_ACCESS_KEY_ID = credentials{'AWS_ACCESS_KEY_ID'}
            AWS_SECRET_ACCESS_KEY = credentials{'AWS_SECRET_ACCESS_KEY'}
        }
    ```
