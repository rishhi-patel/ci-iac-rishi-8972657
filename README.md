# Assignment 3 – Deploying AWS EC2 and RDS using CloudFormation

**Name:** Rishikumar Patel
**Student ID:** 8972657
**Course:** PROG8870 – Cloud Architectures and Infrastructure as Code

---

## 📚 Assignment Overview

This assignment involves deploying the following infrastructure using AWS CloudFormation:

- VPC, Subnets, Route Table, and Internet Gateway
- EC2 instance with SSH access
- MySQL RDS instance with public access

---

## 🧾 Files Included

- `networking.yml` – CloudFormation template for networking resources
- `ec2.yml` – Template to deploy EC2 with security group
- `rds.yml` – Template for public RDS MySQL deployment

---

## 🖼️ Screenshots

1. **VPC, Subnets, Internet Gateway** – AWS VPC Dashboard

![1753221290717](image/README/1753221290717.png)

![1753221336947](image/README/1753221336947.png)

![1753221363434](image/README/1753221363434.png)

![1753221403302](image/README/1753221403302.png) 2. **EC2 Instance Running** – Show public IP

![1753221446832](image/README/1753221446832.png)

3. **RDS Instance Created** – From AWS RDS dashboard

![1753221475314](image/README/1753221475314.png) 4. **CloudFormation Stack Outputs & Events** – For all 3 stacks 5. **CLI Stack Creation Output** – Terminal screenshots

![1753221314714](image/README/1753221314714.png)
![1753221428865](image/README/1753221428865.png)
![1753221513376](image/README/1753221513376.png)

---

## 🧪 CLI Deployment Commands

### Deploy Networking Stack

```bash
aws cloudformation create-stack   --stack-name assignment3-networking   --template-body file://networking.yml   --capabilities CAPABILITY_NAMED_IAM
```

![1753221179479](image/README/1753221179479.png)

### Deploy EC2 Stack

```bash
aws cloudformation create-stack   --stack-name assignment3-ec2   --template-body file://ec2.yml   --capabilities CAPABILITY_NAMED_IAM   --parameters ParameterKey=AMI,ParameterValue=ami-0cbbe2c6a1bb2ad63                ParameterKey=InstanceType,ParameterValue=t2.micro
```

![1753221207579](image/README/1753221207579.png)

### Deploy RDS Stack

```bash
aws cloudformation create-stack   --stack-name assignment3-rds   --template-body file://rds.yml   --capabilities CAPABILITY_NAMED_IAM   --parameters ParameterKey=DBUsername,ParameterValue=admin                ParameterKey=DBPassword,ParameterValue=Password123!
```

![1753221232314](image/README/1753221232314.png)

---
