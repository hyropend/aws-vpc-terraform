# Terraform Remote State Storage

This project demonstrates how to store Terraform state files remotely using Amazon S3 and how to implement state locking with DynamoDB.

The goal of this lab is to understand how Terraform state management works in team environments and why remote state storage is considered a best practice.

---

# Technologies

* AWS S3
* AWS DynamoDB
* Terraform

---

# Features

* Remote Terraform state storage in Amazon S3
* Terraform state locking using DynamoDB
* Shared infrastructure state management
* Team collaboration support

---

# Why Remote State?

By default, Terraform stores its state locally.

In real-world environments this creates several problems:

* State files can be lost
* Team members may have different state versions
* Collaboration becomes difficult
* Infrastructure drift may occur

Using Amazon S3 provides a centralized location for storing Terraform state files.

---

# Why DynamoDB State Locking?

When multiple engineers run Terraform at the same time, state corruption can occur.

Terraform uses a DynamoDB table to create a lock before applying changes.

This prevents:

* Simultaneous infrastructure modifications
* State corruption
* Race conditions during deployments

Only one user can modify the infrastructure state at a time.

---

# Learning Objectives

Through this project I practiced:

* Terraform backend configuration
* AWS S3 integration
* DynamoDB state locking
* Team-oriented Terraform workflows
* Infrastructure state management
