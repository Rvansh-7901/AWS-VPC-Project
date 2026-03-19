# AWS-VPC-Project
⸻
🌐 AWS VPC Architecture (Multi-AZ, Public-Private Subnet Setup)
⸻

📌 Overview

This project demonstrates the design and implementation of a secure and highly available AWS VPC architecture using best practices.

The architecture includes:
	•	Public and Private subnets
	•	Multi-AZ deployment
	•	Internet Gateway for public access
	•	NAT Gateways for secure outbound access
	•	Proper routing and network isolation

⸻

🚀 Key Features
	•	🌍 Custom VPC with CIDR 10.10.72.0/22
	•	🏢 Multi Availability Zone (High Availability)
	•	🌐 Public Subnets (Internet-facing)
	•	🔒 Private Subnets (Secure, no direct access)
	•	🔁 NAT Gateways per AZ (Best Practice)
	•	📡 Internet Gateway for external connectivity
	•	🧭 Route Tables for traffic control

⸻

🧱 Architecture Components

🔹 VPC
	•	CIDR Block: 10.10.72.0/22
	•	Fully isolated network environment

⸻

🔹 Subnets

Type	Availability Zone	Name	Purpose
Public	ap-south-1b	my-subpub	Internet-facing resources
Public	ap-south-1c	my-subpub2	High availability
Private	ap-south-1b	my-subpriv	Backend services
Private	ap-south-1c	my-subpriv2	Secure workloads


⸻

🔹 Internet Gateway (IGW)
	•	Attached to VPC
	•	Enables inbound and outbound internet access for public subnets

⸻

🔹 NAT Gateways
	•	NAT Gateway 1 → AZ-1
	•	NAT Gateway 2 → AZ-2

👉 Allows private subnet instances to access internet securely

⸻

🔹 Route Tables

Public Route Table

0.0.0.0/0 → Internet Gateway

Private Route Table

0.0.0.0/0 → NAT Gateway


⸻

🔄 Traffic Flow

🌐 Public Subnet

EC2 → Internet Gateway → Internet
Internet → Internet Gateway → EC2

🔒 Private Subnet

EC2 → NAT Gateway → Internet Gateway → Internet
(No direct inbound internet access)


⸻

🛡️ Security Best Practices
	•	Private subnets are not directly accessible from the internet
	•	NAT Gateway ensures outbound-only traffic
	•	Can integrate:
	•	Security Groups
	•	Network ACLs
	•	Bastion Host (for SSH access)

⸻

📈 High Availability Design
	•	Multi-AZ architecture ensures fault tolerance
	•	NAT Gateway deployed in each AZ (avoids single point of failure)
	•	Scalable and production-ready foundation

⸻

🧠 Use Cases
	•	Web applications (Frontend + Backend separation)
	•	Microservices architecture
	•	Secure database deployment
	•	Enterprise-grade cloud infrastructure

⸻

🛠️ Future Enhancements
	•	🔹 Add Application Load Balancer (ALB)
	•	🔹 Configure Auto Scaling Groups
	•	🔹 Deploy RDS in private subnets
	•	🔹 Add Bastion Host for secure access
	•	🔹 Convert to Terraform / CloudFormation

⸻
📚 Learnings
	•	VPC networking fundamentals
	•	Subnet design strategies
	•	Routing and internet access control
	•	High availability architecture in AWS

⸻
👨‍💻 Author
    Vansh
⸻

⭐ Support

If you found this project helpful:
	•	Give it a ⭐ on GitHub
	•	Share with others
