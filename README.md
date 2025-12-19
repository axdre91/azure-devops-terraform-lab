Tech Stack: Azure DevOps · Terraform · Azure CLI · Azure Blob Storage · YAML

Azure DevOps + Terraform CI/CD Lab
Walkthrough of an Azure DevOps pipeline deploying Azure infrastructure with Terraform, including remote state, plan artifacts, and a manual approval gate before apply.

## 🎥 Demo Videos
- [Loom Video 1: Azure Devops + Terraform](https://www.loom.com/share/8ab4c3c7147b455aa3ad1365a2fa4b6b)
🔍 What This Lab Demonstrates

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


# Azure DevOps + Terraform Remote State Lab

This lab demonstrates deploying Azure infrastructure using **Terraform** with a **remote backend** and a **production-style Azure DevOps pipeline**.  
The pipeline validates, plans, and applies infrastructure changes with a manual approval gate before apply.

## Architecture (High Level)
- Azure Resource Group
- Virtual Network (VNet)
- Subnets
- Terraform remote state stored in Azure Storage Account
- CI/CD pipeline in Azure DevOps

## Pipeline Flow
1. **Format & Validate**
   - Runs `terraform fmt` and `terraform validate`
2. **Plan**
   - Initializes Terraform with an AzureRM remote backend
   - Generates a `tfplan` file
   - Publishes the plan as a pipeline artifact
3. **Manual Approval**
   - Requires approval before changes are applied
4. **Apply**
   - Downloads the saved plan artifact
   - Applies infrastructure changes using `terraform apply`

## Key Features
- AzureRM remote backend for state management
- Secure authentication using Azure DevOps Service Connection
- Manual approval gate (production-style control)
- Artifact-based plan/apply separation
- Clean, repeatable Infrastructure-as-Code workflow

## Tools & Technologies
- Terraform
- Azure DevOps Pipelines (YAML)
- Azure CLI
- Azure Resource Manager (AzureRM provider)

## Notes
- This lab is intentionally simple to focus on **pipeline structure**, **state management**, and **Terraform workflow best practices**.
- Re-running the pipeline is safe and idempotent when resource names remain consistent.

