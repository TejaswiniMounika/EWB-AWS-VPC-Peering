# AWS VPC Peering Project

## 📌 Project Overview
This project demonstrates how to establish private communication between two Amazon Virtual Private Clouds (VPCs) using **AWS VPC Peering**. It enables resources in different VPCs to communicate securely using their private IP addresses without requiring public internet access between them.

## 🎯 Objectives
- Create two separate VPCs with different CIDR blocks.
- Configure public and private subnets.
- Establish a VPC peering connection.
- Configure route tables and security groups.
- Enable private communication between EC2 instances.
- Verify connectivity using the ping command.

## 🏗️ Architecture Diagram

![AWS VPC Peering Architecture](architecture/vpc-peering-architecture.png)

## ☁️ AWS Services Used
- **Amazon VPC:** Creates isolated virtual networks.
- **Amazon EC2:** Hosts instances for connectivity testing.
- **VPC Peering:** Connects two VPCs privately.
- **Route Tables:** Direct network traffic between VPCs.
- **Security Groups:** Control inbound and outbound traffic.
- **Internet Gateway:** Provides internet access to the public subnet.

## 🌐 Network Configuration

| Component | Configuration |
|---|---|
| AWS Region | Mumbai (`ap-south-1`) |
| VPC A | `ewb-vpc-a` |
| VPC A CIDR | `10.10.0.0/16` |
| VPC A Public Subnet | `10.10.1.0/24` |
| VPC A Private Subnet | `10.10.2.0/24` |
| VPC B | `ewb-vpc-b` |
| VPC B CIDR | `10.20.0.0/16` |
| VPC B Private Subnet | `10.20.1.0/24` |
| Peering Connection | `ewb-a-b-peer` |

## ⚙️ Implementation Steps
1. Created two VPCs with separate CIDR blocks.
2. Created public and private subnets.
3. Configured an Internet Gateway for VPC A.
4. Launched a bastion host and private EC2 instances.
5. Created and activated the VPC peering connection.
6. Updated route tables to enable communication between VPCs.
7. Configured security groups to allow the required traffic.
8. Connected to private EC2 instances through the bastion host.
9. Tested connectivity using the ping command.

## 🧪 Testing and Results

The connectivity test was performed from the EC2 instance in VPC B to the private EC2 instance in VPC A.

**Command:**
```bash
ping -c 4 10.10.2.157
```

**Result:**
```text
4 packets transmitted, 4 received, 0% packet loss
```

The successful test confirmed private network connectivity between the two VPCs.

## 📸 Project Screenshots
The `screenshots/` folder contains screenshots of the AWS configuration and project implementation, including VPC details, peering status, route tables, security groups, EC2 instances, and connectivity testing.
<img width="971" height="801" alt="image" src="https://github.com/user-attachments/assets/cc8fde53-fda0-4a0f-8838-75ba2eea5ac3" />
<img width="1312" height="1199" alt="image" src="https://github.com/user-attachments/assets/b2d42559-20b3-44fd-bbcd-98bcf30c0235" />


## 🔐 Security
- Used private IP addresses for inter-VPC communication.
- Configured security groups to allow required network traffic.
- Used a bastion host to access private EC2 instances.
- Private SSH keys and credentials should never be uploaded to GitHub.

## 📚 Learning Outcomes
Through this project, I learned how to create VPCs, configure subnets, establish VPC peering, manage route tables and security groups, access private EC2 instances, and troubleshoot network connectivity.

## 📁 Project Structure
```text
ewb-aws-vpc-peering/
├── README.md
├── architecture/
│   └── vpc-peering-architecture.png
├── screenshots/
├── documentation/
└── configs/
```

## 👩‍💻 Project Information
- **Project Name:** AWS VPC Peering
- **Internship:** AWS Cloud Computing Internship
- **Cloud Provider:** Amazon Web Services (AWS)
- **Region:** Asia Pacific (Mumbai)

---
*This project was developed as part of hands-on learning in AWS Cloud Computing and Networking.*
