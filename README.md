# End-to-End DevSecOps Automation on AWS

This project demonstrates a full "DevSecOps pipeline" on AWS using Terraform, Ansible, and Trivy.  
It provisions secure infrastructure, configures the environment, and automates vulnerability scanning for Docker images.

## Features

- Infrastructure as Code: AWS VPC, Subnet, EC2, and S3 provisioning using Terraform.  
- Configuration Management: EC2 setup and software installation automated via Ansible.  
- Security Automation: Trivy scans Docker images to detect vulnerabilities.  
- DevSecOps Demonstration: End-to-end workflow from provisioning to security scanning.

## Project Structure

devsecops-demo/
├── playbooks/ # Ansible playbooks for setup and scanning
│ ├── setup.yml
│ └── trivy_scan.yml
├── roles/ # Ansible roles (optional, modular)
├── inventory/ # Ansible inventory for hosts
├── modules/ # Terraform modules (EC2, VPC, S3)
├── main.tf # Terraform main configuration
├── variables.tf # Terraform variables
└── outputs.tf # Terraform outputs


## Prerequisites

- **AWS Account** with proper IAM permissions  
- **Terraform** installed (v1.6+)  
- **Ansible** installed (v2.9+)  
- **Trivy** installed for container vulnerability scanning  
- **Docker** installed if scanning images  

## Usage

### 1. Deploy Infrastructure

terraform init
terraform plan
terraform apply

### 2. Connect to EC2
ssh -i <your-key>.pem ec2-user@<EC2_PUBLIC_IP>

### 3. Run Ansible Playbooks
ansible-playbook -i inventory/hosts.ini playbooks/setup.yml
ansible-playbook -i inventory/hosts.ini playbooks/trivy_scan.yml

### 4. Scan Docker Images
trivy image python:3.11

## Outcome
- EC2 instance fully configured with Ansible
- Docker image vulnerabilities identified by Trivy
- Secure and reproducible DevSecOps demonstration


