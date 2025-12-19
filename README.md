Tech Stack: Azure DevOps · Terraform · Azure CLI · Azure Blob Storage · YAML

Azure DevOps + Terraform CI/CD Lab
Built a production-style Azure DevOps pipeline that runs Terraform fmt/validate/plan, stores the plan as an artifact, enforces a manual approval gate, and applies infrastructure using remote state in Azure Blob Storage.

## 🎥 Demo Videos
- [Loom Video 1: Azure Devops + Terraform](https://www.loom.com/share/8ab4c3c7147b455aa3ad1365a2fa4b6b)
🔍 What This Lab Demonstrates (Recruiter-Scan Friendly)

-Infrastructure as Code using Terraform

-Azure DevOps YAML pipelines for CI/CD

-Secure authentication using Azure Service Connections

-Remote Terraform state stored in Azure Blob Storage

-Artifact-based plan → apply workflow

-Manual approval gate before production changes

-Clean, repeatable deployments with idempotent Terraform runs

🚀 Azure DevOps + Terraform: Automated VNet Deployment

<p align="center">
  <img src="assets/ChatGPT Image Nov 30, 2025, 09_10_33 PM.png" alt="Azure DevOps Terraform Architecture Diagram" width="750">
</p>


This project demonstrates how I built a fully automated Azure infrastructure deployment using Terraform and Azure DevOps Pipelines. The pipeline formats, validates, plans, and deploys a Virtual Network (VNet) with multiple subnets — all automatically, using a clean CI/CD workflow.

This repo is intentionally simple, easy to follow, and focused on real-world DevOps practices.

🔥 What This Project Shows (for recruiters & reviewers)

Infrastructure-as-Code using Terraform

Azure resource creation using AzureRM provider

Automated CI/CD using Azure DevOps Pipelines

Manual approval gate before apply (production-style control)

Use of a secure Azure Service Connection

Clean and modular Terraform structure

Proper documentation 
🧱 Architecture Overview

Below is the high-level architecture for what this pipeline deploys:

```
Resource Group: rg-ado-tf-demo
└── Virtual Network: vnet-ado-demo
    ├── Address Space: 10.10.0.0/16
    ├── Subnets
    │   ├── subnet-app   (10.10.1.0/24)
    │   ├── subnet-db    (10.10.2.0/24)
    │   └── subnet-mgmt  (10.10.10.0/24)
```

🔧 Tools Used
| Tool                       | Purpose                        |
| -------------------------- | ------------------------------ |
| **Terraform**              | Provision Azure resources      |
| **Azure DevOps Pipelines** | CI/CD workflow                 |
| **Azure CLI Task**         | Authentication inside pipeline |
| **AzureRM Provider**       | Azure resource creation        |

📁 Repository Structure
```
.
├── terraform/
│   ├── main.tf
│   ├── providers.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── terraform.tfvars
│
├── azure-pipelines.yml
└── README.md
```
▶️ How to Run This Yourself

You can follow these steps to recreate the deployment, or simply review them to understand how the project is structured.

1. Prerequisites

Azure subscription

Azure DevOps project

Azure Service Connection (I used: adolab2)

Terraform installed (optional – pipeline runs it automatically)

2. Update Your Service Connection Name

In azure-pipelines.yml, update:
azureSubscription: 'adolab2'

Replace adolab2 with your Azure DevOps service connection name.

3. Push Your Code to Azure DevOps Repo
   Run:
git add .
git commit -m "Initial commit for Terraform DevOps pipeline"
git push

4. Run the Pipeline

The pipeline will:

Validate Terraform

Plan the deployment

Pause for your approval

Apply and create all Azure resources

The approval step is intentional — mirrors real production workflows.

5. Clean Up Resources (Avoid Charges)

Terraform can destroy EVERYTHING deployed:
terraform destroy

Or delete the Resource Group directly:

1. Go to Azure Portal
2. Open Resource groups
3.Delete: rg-ado-tf-demo

This ensures you avoid unnecessary Azure costs.

