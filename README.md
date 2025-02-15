# Cloud Application Deployment Using AWS

## Introduction

In today’s digital era, cloud computing has become the backbone of many organizations' infrastructure, enabling flexibility, scalability, and cost-efficiency. This project focuses on deploying a web application in the cloud using **Amazon Web Services (AWS)**. The primary steps involve creating a **Virtual Private Cloud (VPC)**, launching a **web application on an EC2 instance**, and ensuring security and accessibility.

## Objectives

- **Setting up a secure and scalable network architecture** using a **Virtual Private Cloud (VPC)**.
- **Configuring and launching an EC2 instance** that hosts the web application.
- **Ensuring accessibility** of the deployed application from the internet while maintaining security.

## Steps Involved in Cloud Deployment

### 1. Creating the Underlying Infrastructure: **Amazon VPC**
Amazon Virtual Private Cloud (VPC) allows users to create a private network within AWS, providing control over IP ranges, subnets, gateways, and route tables.

#### VPC Creation
- A new VPC is created with a CIDR block (e.g., `10.0.0.0/16`) to define the range of IP addresses.

#### Subnet Configuration
- Two **public subnets** are created in different availability zones (AZs) to ensure high availability.

#### Internet Gateway
- An **internet gateway** is attached to the VPC, enabling instances to connect to the internet.

#### Route Table
- A **route table** is configured to route traffic from the subnets to the internet via the internet gateway.

### 2. Security Setup: **Creating a Security Group**
Security is a critical concern in cloud computing. In this step:

#### Security Group Configuration
- A **security group** named **"Web Security Group"** is created to control traffic to the EC2 instances.
- **Inbound Rules**: HTTP traffic (port 80) is allowed from anywhere, making the web application publicly accessible.
- **Outbound Rules**: Outbound traffic is enabled to allow communication with the internet.

### 3. Deploying the Application: **Launching an EC2 Instance**
The next step is to launch an **Amazon EC2 instance** that hosts the web application.

#### Instance Configuration
- A `t3.micro` instance type is chosen for its balance between performance and cost.
- The **Amazon Linux 2023** operating system is used, commonly used for server applications.

#### User Data Script
- A **user data script** automates the installation of **Node.js** and sets up the web application.
  - Installs required packages.
  - Downloads the application from **Amazon S3**.
  - Installs dependencies using `npm`.
  - Starts the web application.

### 4. Accessing the Web Application
Once the EC2 instance is configured, the **public IP address** is used to access the application through a browser. This verifies that the web application is deployed successfully.

## Key Learnings

1. **Automation with User Data Scripts**: Automating the instance configuration using user data scripts saves time and reduces human error.
2. **Security and Networking**: Proper configuration of the VPC with subnets, security groups, and routing ensures a secure and scalable cloud environment.
3. **Scalability**: By deploying the application in two public subnets across different availability zones, the architecture is designed for high availability and scalability.

## Conclusion
This project demonstrates how to deploy a scalable and secure web application in the cloud using AWS. By creating a VPC, configuring security, and automating the deployment process with user data scripts, we can ensure that the application is easily accessible, highly available, and secure.

---

### Getting Started

1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/aws-cloud-application.git
    cd aws-cloud-application
    ```

2. Follow the steps outlined in the **Steps Involved in Cloud Deployment** section to replicate the infrastructure and deploy the application.

---

### Prerequisites

- **AWS Account**: You need an AWS account to create a VPC, EC2 instances, and other resources.
- **AWS CLI**: If you plan to interact with AWS from the terminal, install and configure the AWS CLI.

---
