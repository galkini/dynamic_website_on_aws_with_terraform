![Alt text](/Terraform-AWS-GitHub.png)

![Alt text](/Dynamic_Web_Site_on_AWS_with_terraform.png)

# Hosting a Dynamic Website on AWS Using Terraform

This project demonstrates how to host a dynamic website on AWS using Terraform for infrastructure as code (IaC). It leverages multiple AWS services to ensure high availability, scalability, fault tolerance, and security. The reference diagram and configuration files for the project are available in a private GitHub repository.

## Prerequisites and Initial Setup

Before starting the deployment, the following prerequisites and initial setup were completed:

1. **Terraform Installation**:
   - Installed Terraform on my PC.
   - Updated the system environment variable (path) to access Terraform from any location.

2. **Git Installation and Configuration**:
   - Installed and configured Git on my PC.
   - Created a private GitHub repository to store all configuration files for this project.

3. **SSH Key Pair**:
   - Generated an SSH key pair on my PC.
   - Added the public key to the GitHub account for secure access.

4. **Repository Cloning**:
   - Cloned the previously created private GitHub repository to my PC.

5. **Visual Studio Code**:
   - Installed Visual Studio Code and integrated it with Terraform.

6. **AWS CLI Installation**:
   - Installed AWS CLI on my PC.

7. **S3 Bucket for Terraform State**:
   - Created an S3 bucket in my AWS account to store the Terraform state files.

8. **Terraform IAM User**:
   - Created an IAM user specifically for Terraform.
   - Configured authentication for Terraform with my AWS account using the IAM user's credentials.

## Infrastructure Setup Using Terraform

### Network Architecture

1. **VPC Configuration**:
   - Configured a Virtual Private Cloud (VPC) with both public and private subnets spanning two availability zones.

2. **Internet Gateway**:
   - Deployed an Internet Gateway to enable connectivity between VPC instances and the Internet.

3. **Security Groups**:
   - Established Security Groups to serve as a network firewall mechanism.

4. **Availability Zones**:
   - Leveraged two Availability Zones to increase system reliability and fault tolerance.

5. **Subnets**:
   - Used public subnets for infrastructure components like the NAT Gateway and Application Load Balancer.
   - Placed web servers (EC2 instances) within private subnets for enhanced security.

6. **NAT Gateway**:
   - Allowed instances in both the private Application and Data subnets to access the Internet via the NAT Gateway.

### Compute and Load Balancing

1. **EC2 Instances**:
   - Hosted the dynamic website on EC2 instances.

2. **Application Load Balancer**:
   - Used an Application Load Balancer and a target group for evenly distributing web traffic to an Auto Scaling Group of EC2 instances across multiple availability zones.

3. **Auto Scaling Group**:
   - Utilized an Auto Scaling Group to automatically manage EC2 instances, ensuring website availability, scalability, fault tolerance, and elasticity.

### Additional Services

1. **Certificate Manager**:
   - Secured application communications using AWS Certificate Manager.

2. **Simple Notification Service (SNS)**:
   - Configured SNS to alert about activities within the Auto Scaling Group.

3. **Route 53**:
   - Registered the domain name and set up a DNS record using Route 53.

### Deployment and Cleanup

1. **Infrastructure Deployment**:
   - Deployed the infrastructure using `terraform apply`.

2. **Project Cleanup**:
   - After completing the project and testing various configurations, the infrastructure was destroyed using `terraform destroy`.

## Repository

Find all configuration files, diagrams, and scripts in the private GitHub repository [https://github.com/galkini/dynamic_website_on_aws_with_terraform]
