# Deploying-AWS-EC2-terraform
Deploying an EC2 instance with Terraform

In this lab, we are going to set up two simple EC2 instances with Terraform. Terraform is an open-source infrastructure as a code software tool that provides a consistent CLI workflow to manage hundreds of cloud services.

# Prerequisites
To follow this tutorial you will need:
1) The Terraform CLI (3.0 +)  Installed.
2) The AWS CLI Installed.
3) An AWS account. 
### 1) create non-root AWS user     2) Add the necessary IAM roles (e.g. AmazonEC2FullAccess)
### 3) Save Access key + secret key (or use AWS CLI `aws configure` -- https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)

#### Write configuration

The set of files used to describe infrastructure in Terraform is known as a Terraform configuration. You will write your first configuration to define a single AWS EC2 instance. Each Terraform configuration must be in its own working directory. Create a directory for your configuration.

#### Create a directory
# mkdir terraform-aws-instance

#### Change into the directory

# cd terraform-aws-instance

#### Create a file to define your infrastructure

# touch main.tf
Open main.tf in your text editor, paste in the configuration that is on main.tf file in this reposito

#terraform {
# required_providers {
#    aws = {
#      source  = "hashicorp/aws"
#      version = "~> 3.0"
#    }
# }
#}

#provider "aws" {
#  region = "us-east-1"
#}

#resource "aws_instance" "EC1" {
#  ami           = "ami-011899242bb902164" # Ubuntu 20.04 LTS // us-east-1
#  instance_type = "t2.micro"

#   tags = {
#    Name = "Ubuntu1"
#  }
#}

#resource "aws_instance" "EC2" {
#  ami           = "ami-011899242bb902164" # Ubuntu 20.04 LTS // us-east-1
#  instance_type = "t2.micro"

#   tags = {
#    Name = "Ubuntu2"
#  }
# }

## In the working directory run terraform init  ( When you create a new configuration — or check out an existing configuration from version control — you need to initialize the directory with terraform init. Initializing a configuration directory downloads and installs the providers defined in the configuration, which in this case is the aws provider.)

# Create Infrastructure

Apply the configuration  by running terraform apply command. Terraform will print out list of resources that will be created.  Once you review the list scroll all the way down and select "yes" to approve the creation of the resources.

If you don't get any errors go into your AWS console and you should see your two new EC2 instances.




