# Automated DevOps Project

This project demonstrates an automated CI/CD pipeline that deploys a web application to the Azure cloud.

## Overview

The main goal is to show how a developer can make a code change and have it go live on the internet automatically, with no manual steps.

It uses Git, GitHub Actions, Docker, and Azure Kubernetes Service (AKS).

## Pipeline Workflow

1. Make a code change to the Python application in VS Code.
2. Git push the change to the GitHub repository.
3. GitHub Actions pipeline automatically triggers.
4. CI job: Build the application into a Docker image and push it to Azure Container Registry.
5. CD job: Deploy the new image to the Kubernetes cluster (AKS).
6. Kubernetes automatically updates the running application.

## Demo

Change the text in `app.py`, git push, and watch the pipeline run in the GitHub Actions tab. Once green, refresh the website to see the live change.

## Infrastructure Setup

For this demo, the Kubernetes cluster and container registry were set up manually in the Azure portal. The next step is to automate this with Terraform.

## Prerequisites

- Azure account with AKS and ACR set up
- GitHub repository with secrets configured:
  - ACR_LOGIN_SERVER
  - ACR_USERNAME
  - ACR_PASSWORD
  - AZURE_CREDENTIALS
  - AKS_RESOURCE_GROUP
  - AKS_CLUSTER_NAME

## Local Development

To run locally:

```bash
pip install -r requirements.txt
python app.py
```

Visit http://localhost:80

## Deployment

The deployment is handled automatically via GitHub Actions on push to main branch.
