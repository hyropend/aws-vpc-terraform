# EKS IRSA (IAM Roles for Service Accounts)

This project demonstrates how to configure IRSA (IAM Roles for Service Accounts) in Amazon EKS using Terraform.

The goal of this lab is to provide Kubernetes workloads with secure access to AWS services without storing AWS credentials inside containers.

---

# Technologies

* AWS EKS
* Terraform
* IAM
* OIDC Provider
* Kubernetes Service Accounts

---

# Features

* OIDC Connect Provider configuration
* IAM Policy creation
* IAM Role for Kubernetes workloads
* Service Account integration
* IRSA validation job

---

# Why IRSA?

Traditionally, applications running inside Kubernetes often access AWS services using credentials attached to worker nodes.

This approach grants permissions to every pod running on the node, which violates the principle of least privilege.

IRSA solves this problem by allowing individual Kubernetes Service Accounts to assume specific IAM Roles.

As a result:

* Pods receive only the permissions they need
* No AWS access keys are stored inside containers
* Security is improved
* AWS permissions are managed centrally through IAM

---

# How It Works

1. An OIDC Provider is connected to the EKS cluster.
2. An IAM Role and Policy are created.
3. The IAM Role is linked to a Kubernetes Service Account.
4. Pods using that Service Account automatically receive temporary AWS credentials.
5. The validation job confirms successful access through IRSA.

---

# Learning Objectives

Through this project I practiced:

* EKS identity management
* OIDC federation concepts
* IAM trust policies
* Kubernetes Service Accounts
* Secure AWS access from pods
* Least-privilege security design
