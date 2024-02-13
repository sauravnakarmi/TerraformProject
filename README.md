## Overview
The goal of this project was to familiarize myself with Terraform. Terraform is an open-source infrastructure as code software tool created by HashiCorp. It enables users to define and provision infrastructure resources, such as virtual machines, networks, storage, and more, using a declarative configuration language. With Terraform, infrastructure can be managed as code, allowing for versioning, collaboration, and automation of deployment processes. I used this software in tandem with AWS to deploy an EC2 instance (running an Ubuntu AMI) inside of a VPCs subnet which was attached to an internet gateway. The real beauty of Terraform lies in its ability to reuse code for common AWS deployments. The architecture seen in this project is a very common building block for a multitude of AWS powered services since it enables traffic from the internet to reach your EC2 instance. This makes it perfect for Terraform deployment since this architecture can be modularized and reused across projects, promoting code reuse and simplifying management of complex infrastructures.

## Steps

### Step 1: Assign Provider


