# Terraform-deploy-minecraft
Deploy Minecraft server using terraform to AWS

Create S3 bucket for terraform
Create S3 bucket for mc-backup
Create Elastic IP
Create EC2 key
Enter values in config/account.tfvars

Adjust download URL in 

Uses lambda functions to create and destroy a minecraft server instance with terraform. S3 is used for server backups and for storing terraform resources. lambda functions can send notifications to a discord chat.

Push button minecraft server uses 2 s3 buckets 

-world backup
-terraform plan

auto_shutoff.py - Runs on the minecraft server 

mine-build.py - This is used in a lambda function. It pulls terraform files and startup bash script from s3 and starts an ec2 instance.

mine-destroy.py - Used in a lambda function to run terraform destroy and update the terraform state file in the s3 bucket

minecraft.sh - start up script use for ec2 instance

new-minecraft-server.sh - start up script to use the first time you create a server, the initial server will be used to create the world backup s3 bucket.

server.tf - terraform configuration file.
