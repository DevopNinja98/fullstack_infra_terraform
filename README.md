🚀 Full-Stack Infrastructure on AWS using Terraform & GitHub Actions

A fully automated, production-ready AWS infrastructure built with Terraform, orchestrated via GitHub Actions, and designed to deploy a complete 3-tier application on Amazon EKS.

This project demonstrates real-world DevOps skills including IaC, CI/CD, Kubernetes, security, networking, and automation — making it a strong portfolio piece for DevOps, SRE, and Platform Engineer roles.

🎯 What This Project Does

This repository builds a complete AWS infrastructure using Terraform:

🔹 Core AWS Infrastructure

Custom VPC (private + public subnets across AZs)

Internet Gateway & NAT Gateways

Routing, subnet associations, and VPC endpoints

🔹 EKS Kubernetes Cluster

EKS cluster with public & private node groups

IAM roles, security groups, OIDC provider

Automatic installation of AWS EBS CSI Driver

Ready for workload deployment

🔹 Container Registry

Secure Amazon ECR repository for application container images

🔹 SonarQube EC2 Server

EC2 instance with automated installation script

Helps with continuous code quality and DevSecOps workflows

🔹 GitHub Actions CI/CD Pipeline

Terraform Init → Validate → Plan → Apply

Deploys EKS manifests automatically after infrastructure creation

Uses OpenID Connect (OIDC) for secure AWS authentication

Integrates with a 3-tier application repo

<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/efea08c9-2b6a-482d-a0cc-97b57f9d5c20" />


🛠️ Technologies Used
Category	Tools
IaC	Terraform
Cloud	AWS (EKS, VPC, EC2, IAM, ECR, VPC Endpoints)
CI/CD	GitHub Actions
Kubernetes	EKS, EBS CSI Driver
Security	IAM, OIDC, least-privilege policies
Scripting	Bash (user-data for SonarQube)
📦 How to Use This Project
1️⃣ Prerequisites

AWS Account

Terraform installed (≥ 1.3)

kubectl installed

AWS CLI installed

GitHub repository + secrets configured

2️⃣ Clone the Repo
git clone https://github.com/DevopNinja98/fullstack_infra_terraform.git
cd fullstack_infra_terraform

3️⃣ Configure Backend (Optional)

Update backend.tf with your S3 bucket and DynamoDB table.

4️⃣ Initialize Terraform
terraform init

5️⃣ Validate the configuration
terraform validate

6️⃣ Preview changes
terraform plan

7️⃣ Deploy the infrastructure
terraform apply -auto-approve

8️⃣ Configure Kubeconfig
aws eks update-kubeconfig --name <cluster-name> --region <region>

9️⃣ Deploy Application

A GitHub Actions workflow will do this automatically, but you can run manually:

kubectl apply -f k8s/

🔐 Setting Up GitHub Secrets

Add these secrets in GitHub → Settings → Secrets → Actions:

Secret	Description
AWS_ACCESS_KEY_ID	IAM access key
AWS_SECRET_ACCESS_KEY	IAM secret key
AWS_REGION	AWS region
ECR_REPO	Your ECR repo name
CLUSTER_NAME	EKS cluster name 

🌟 Future Enhancements(Planned)

Integrate ArgoCD for GitOps

Add monitoring (Prometheus + Grafana)

Add logging using EFK stack

Add autoscaling using Karpenter

Add WAF + CloudFront

🤝 Contributing

Pull requests are welcome! Feel free to improve the infrastructure or optimize modules.

📧 Contact

Author: Niranjan Pawar (DevOps Engineer)
LinkedIn/GitHub: https://www.linkedin.com/in/niranjan-pawar-3051a9160/
