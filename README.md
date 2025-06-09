# 🚀 Dynamic Web Application on AWS

This project demonstrates a secure, scalable, and highly available architecture for deploying a dynamic web application using AWS services. The architecture supports fault tolerance, autoscaling, and follows AWS best practices for production workloads.
---

## 📊 Architecture Diagram

![Alt Text](/My_Dynamic_Web_App_on_AWS.jpg)
---

## 🏗️ Architecture Overview

The website is hosted on EC2 instances within a Virtual Private Cloud (VPC) configured with public and private subnets spanning two Availability Zones. The infrastructure leverages the following AWS resources:

- **Virtual Private Cloud (VPC)**: A logically isolated section of the AWS cloud where AWS resources are launched.
- **Internet Gateway**: Enables communication between the VPC instances and the internet.
- **Security Groups**: Act as virtual firewalls to control inbound and outbound traffic.
- **Availability Zones**: Multiple Availability Zones are used to increase reliability and fault tolerance.
- **Public Subnets**: Host infrastructure components like the NAT Gateway and Application Load Balancer.
- **Private Subnets**: Host the web servers (EC2 instances) for enhanced security.
- **NAT Gateway**: Allows instances in private subnets to access the internet.
- **EC2 Instance Connect Endpoint**: Enables secure connections to EC2 instances within both public and private subnets.
- **Application Load Balancer**: Distributes incoming web traffic across multiple EC2 instances in an Auto Scaling group.
- **Auto Scaling Group**: Automatically manages the EC2 instances hosting the website, ensuring availability, scalability, fault tolerance, and elasticity.
- **AWS Certificate Manager**: Secures application communications with SSL/TLS certificates.
- **Simple Notification Service (SNS)**: Sends notifications about activities within the Auto Scaling Group.
- **Route 53**: Provides DNS services for registering and managing the website's domain name.
- **S3 Bucket**: Stores the application code and assets.
---

## 🛠️ Deployment Overview

The deployment of this infrastructure is automated using scripts and configuration files stored in a GitHub repository. The repository includes the following:

- **Reference Diagram**: A visual representation of the AWS infrastructure and its components.
- **Deployment Scripts**: Scripts to provision and configure the necessary AWS resources.

---

1. **Provision AWS Infrastructure**
   -Provision the necessary AWS infrastructures:
     - VPC, Subnets, Route Tables, Internet Gateway, NAT Gateways
     - Security Groups
     - EC2 Launch Template and Auto Scaling Group
     - RDS instance and DB subnet group
     - ALB with target groups and listeners

2. **Set Up the Required AWS Resources**
   - Deploy your application code to EC2 instances
   - Ensure security groups and IAM roles are correctly applied

3. **Deploy the Website Code and Assets**
   - Upload your website's static assets and application code to the designated S3 bucket:
   - From the AWS CLI run the command to sync your S3 bucket to your working directory "aws s3 sync ./website s3://your-s3-bucket-name"
   - Ensure your EC2 launch configuration or AMI includes any necessary application stack setup (e.g., Node.js, Nginx, Apache).

4. **Access the Application**
   - Confirm that the domain is properly configured in Route 53.
   - Open your web browser and navigate to your registered domain or Application Load Balancere DNS name.
---

## ✅ Key Features

- High availability via Multi-AZ deployment
- Scalable web tier with EC2 Auto Scaling
- Secure architecture with private subnets and IAM controls
- End-to-end HTTPS with managed TLS certificates
---

## 🔐 Security Best Practices

- Use private subnets for application and database layers
- Principle of least privilege for IAM
- Restrict EC2 access via EC2 Connect Endpoint or AWS Systems Manager Session Manager
- Encrypted RDS with backup enabled
---

## 👥 Contributing
Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request in the GitHub repository.
