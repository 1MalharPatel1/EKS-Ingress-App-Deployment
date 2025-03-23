# EKS-Ingress

## Overview

This repository contains resources and configurations for deploying an application on Amazon EKS (Elastic Kubernetes Service) with an NGINX Ingress Controller. The deployment includes Kubernetes manifests, Helm charts, and scripts to streamline the setup process.

## Prerequisites

Before using this repository, ensure you have the following:
- AWS CLI configured with appropriate permissions.
- kubectl installed and configured for your EKS cluster.
- Helm installed for managing Kubernetes packages.
- Terraform (if infrastructure provisioning is required).

## Folder Structure

```
EKS-Ingress-app-deployment/
├── manifests/          # Kubernetes manifests for deployment
├── helm-charts/        # Helm charts for application and ingress
├── scripts/            # Helper scripts for automation
├── terraform/          # Terraform configurations for EKS cluster setup
└── README.md           # Project documentation
```

## Deployment Steps

1. **Provision EKS Cluster** (if not already created):
    - Navigate to the `terraform/` directory.
    - Run `terraform init`, `terraform plan`, and `terraform apply` to create the EKS cluster.

2. **Install NGINX Ingress Controller**:
    - Use the Helm chart in the `helm-charts/` directory to deploy the NGINX Ingress Controller.

3. **Deploy the Application**:
    - Apply the Kubernetes manifests in the `manifests/` directory using `kubectl apply -f`.

4. **Verify Deployment**:
    - Check the status of pods and services using `kubectl get pods` and `kubectl get svc`.
    - Access the application via the Ingress endpoint.

## Cleanup

To delete the resources:
- Use `kubectl delete -f manifests/` to remove application resources.
- Use `terraform destroy` in the `terraform/` directory to delete the EKS cluster.

## Notes

- Ensure proper IAM roles and policies are configured for the EKS cluster.
- Update the Helm values and Kubernetes manifests as per your application requirements.
- Monitor the Ingress logs for troubleshooting.