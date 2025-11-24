<h1 align="center">🚀 Full-Stack Infrastructure on AWS using Terraform & GitHub Actions</h1>

A fully automated, production-ready AWS infrastructure built with Terraform, orchestrated through GitHub Actions, and designed to deploy a complete 3-tier application on Amazon EKS.

This project showcases strong DevOps, SRE, and Platform Engineering capabilities including IaC, CI/CD, Kubernetes, cloud networking, and security automation.
                                              
<h2>🎯 What This Project Does</h2>  

This repository provisions an end-to-end AWS infr astructure using Terraform.

##🔹 Core AWS Infrastructure
 - Custom VPC (public & private subnets across multiple AZs)

 - Internet Gateway & NAT Gateways

 - Routing tables + subnet associations

 - VPC Endpoints for secure AWS service access

##🔹 EKS Kubernetes Cluster

- Amazon EKS Cluster with public & private node groups

- IAM roles, security groups, and OIDC provider

- Automatic installation of EBS CSI Driver

- Production-ready for deploying workloads

##🔹 Container Registry

- Amazon ECR repository for storing application container images

##🔹 SonarQube EC2 Server

- EC2 instance with automated setup script

- Useful for code quality, DevSecOps, and CI integration

##🔹 GitHub Actions CI/CD Pipeline

- Terraform: Init → Validate → Plan → Apply

- Deploys Kubernetes manifests to EKS automatically

- Uses OIDC for secure GitHub → AWS authentication

- Integrates with external 3-tier application repository

<p align="center"> <img width="1280" height="720" src="https://github.com/user-attachments/assets/efea08c9-2b6a-482d-a0cc-97b57f9d5c20" /> </p>

<h2>🛠️ Technologies Used</h2>

| **Category**   | **Tools**                                    |
| -------------- | -------------------------------------------- |
| **IaC**        | Terraform                                    |
| **Cloud**      | AWS (EKS, VPC, EC2, IAM, ECR, VPC Endpoints) |
| **CI/CD**      | GitHub Actions                               |
| **Kubernetes** | EKS, EBS CSI Driver                          |
| **Security**   | IAM, OIDC, least-privilege policies          |
| **Scripting**  | Bash (SonarQube user-data)                   |


<h2>📦 How to Use This Project</h2>

##1️⃣ Prerequisites

- AWS Account

- Terraform ≥ 1.3

- kubectl installed

- AWS CLI installed

- GitHub secrets configured

##2️⃣ Clone the Repository
'''
git clone https://github.com/DevopNinja98/fullstack_infra_terraform.git
cd fullstack_infra_terraform
'''

##3️⃣ Configure Backend (Optional)

Modify backend.tf with your S3 bucket + DynamoDB table.
'''
terraform init

'''

##4️⃣ Initialize Terraform
'''
terraform init
'''

##5️⃣ Validate Configuration
'''
terraform validate
'''

##6️⃣ Preview Changes
'''
terraform plan
'''

##7️⃣ Deploy Infrastructure
'''
terraform apply -auto-approve
'''

##8️⃣ Configure Kubeconfig
'''
aws eks update-kubeconfig --name <cluster-name> --region <region>
'''

##9️⃣ Deploy the Application
GitHub Actions will deploy automatically.
To deploy manually:
'''
kubectl apply -f k8s/
'''

<h2>🔐 Setting Up GitHub Secrets</h2>
| **Secret Name**         | **Description**     |
| ----------------------- | ------------------- |
| `AWS_ACCESS_KEY_ID`     | IAM access key      |
| `AWS_SECRET_ACCESS_KEY` | IAM secret key      |
| `AWS_REGION`            | AWS region          |
| `ECR_REPO`              | ECR repository name |
| `CLUSTER_NAME`          | EKS cluster name    |


<h2>🌟 Future Enhancements (Planned)</h2>
- Integrate ArgoCD for GitOps

- Add monitoring (Prometheus + Grafana)

- Add EFK logging stack

- Introduce Karpenter for autoscaling

- Add AWS WAF + CloudFront for security & caching

<h2>🤝 Contributing</h2>

Pull requests are welcome!
Feel free to improve modules, optimize networking, or extend CI/CD workflows.

<h2>📧 Contact</h2>

Author: Niranjan Pawar (DevOps Engineer)
LinkedIn: https://www.linkedin.com/in/niranjan-pawar-3051a9160/

