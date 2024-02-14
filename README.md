## Overview
The goal of this project was to familiarize myself with Terraform. Terraform is an open-source infrastructure as code software tool created by HashiCorp. It enables users to define and provision infrastructure resources, such as virtual machines, networks, storage, and more, using a declarative configuration language. With Terraform, infrastructure can be managed as code, allowing for versioning, collaboration, and automation of deployment processes. I used this software in tandem with AWS to deploy an EC2 instance (running an Ubuntu AMI) inside of a VPCs subnet. This was attached to an internet gateway using routing tables. The real beauty of Terraform lies in its ability to reuse code for common AWS deployments. The architecture seen in this project is a very common building block for a multitude of AWS powered services since it enables traffic from the internet to reach your EC2 instance. This makes it perfect for Terraform deployment since this architecture can be modularized and reused across projects, promoting code reuse and simplifying management of complex infrastructures.

## Steps

### Step 1: Assign Provider
![assign provider](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/eac785d2-6770-4f6e-ae0b-421b89ed55cf)

Terraform works with various other cloud services such as AWS, Azure, and Google Cloud Platform. For our use case we will be using AWS.

### Step 2: Create A VPC
![associate subnet with route table](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/2dfda096-b6d6-4356-8448-fdb3dd1a591a)

VPC gives us a place to store our infrastructure in a private manner on the cloud. 

### Step 3: Create an Internet Gateway
![create internet gateway](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/c500bc7c-bfa7-46ee-95f3-2a173b2b9b1b)

Internet Gateway provides internet access to our VPC. 

### Step 4: Create Custom Route Table
![create custom route table](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/d182e7c2-86aa-46a9-803f-2b972a0f329c)

Route table is used to route traffic from the internet into the internet gate way and will also eventually send out traffic from the subnet to the internet through the internet gateway. 

### Step 5: Subnet
![create subnet](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/9bec3f59-3944-45be-903e-3b10f6dab42e)

A subnet acts as a range of ip addresses from the VPC and helps to manage traffic within the VPC. We will use the subnet to launch our EC2 instance and also to route traffic from our internet gateway. 

### Step 6: Associate Subnet with Route Table
![associate subnet with route table](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/2dfda096-b6d6-4356-8448-fdb3dd1a591a)

We need to add an association into our route table for the subnet we just created. 

### Step 7: Security Group
![create security group](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/30b6c3c2-58e2-410a-9bea-a0f50f5c5120)

Security groups are used to allow traffic from different sources into and out of the system. In this case we are allowing traffic into port 443, 80, and 22. These being SSH, HTTP, and HTTPS respectively. We are also allowing all ports in the egress direction. 

### Step 8: Network Interface
![create network interface](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/b10d759e-afb5-4412-a987-44c32f520f2c)

Network interfaces are fundamental for connecting instances to the network, enabling them to send and receive traffic. 

### Step 9: Elastic Ip 
![elasticip](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/77375599-1311-4b77-a870-6180d2dedac2)

Elastic IP addresses are static IP addresses designed for dynamic cloud computing. They are primarily used for the purpose of persistent IP address for resources like EC2 instances. 

### Step 10: EC2 instance
![create ec2 server](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/980502a8-1e2a-48ce-aca8-0b04a3715e29)

Amazon EC2 instances are virtual servers provided by AWS.

### Step 11: Outputs
![outputs](https://github.com/sauravnakarmi/TerraformProject/assets/70821330/11c087e1-8d90-458a-a0a9-fdd678b0a8b9)

Outputs server id, public and private ip

