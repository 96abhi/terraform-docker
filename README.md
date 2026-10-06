# Terraform Docker Setup

This project demonstrates how to use **Terraform** to manage Docker resources, including Docker images and containers.

## Architecture

```text
Terraform
    |
    v
Docker Provider
    |
    v
Docker Engine
    |
    v
Nginx Container
```

## Prerequisites

Make sure the following are installed:

* Ubuntu/Linux
* Terraform
* Docker
* Git

Check the installations:

```bash
terraform --version
docker --version
git --version
```

## Project Structure

```text
terraform-docker/
├── .gitignore
├── .terraform.lock.hcl
├── main.tf
└── README.md
```

## Terraform Configuration

The project uses the Docker Terraform provider:

```hcl
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "3.6.2"
    }
  }
}

provider "docker" {}
```

Terraform creates an Nginx Docker image and container.

## Initialize Terraform

Clone the repository and enter the project directory:

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd terraform-docker
```

Initialize Terraform:

```bash
terraform init
```

## Validate Configuration

Check the Terraform configuration:

```bash
terraform validate
```

Expected output:

```text
Success! The configuration is valid.
```

## Create Terraform Plan

Review the resources Terraform will create:

```bash
terraform plan
```

## Create Docker Resources

Apply the Terraform configuration:

```bash
terraform apply
```

Enter:

```text
yes
```

Terraform will create the Docker Nginx container.

## Verify Docker Container

Check running containers:

```bash
docker ps
```

You should see the container:

```text
terraform-nginx
```

You can also check all containers:

```bash
docker ps -a
```

## Access Nginx

The container exposes port `80` and maps it to port `8080` on the host.

Open:

```text
http://localhost:8081
```
<img width="670" height="266" alt="image" src="https://github.com/user-attachments/assets/db4fa67f-087b-4969-8600-68180b184bef" />

You should see the Nginx welcome page.

## Useful Terraform Commands

Initialize Terraform:

```bash
terraform init
```

Format Terraform files:

```bash
terraform fmt
```

Validate configuration:

```bash
terraform validate
```

Create execution plan:

```bash
terraform plan
```

Apply configuration:

```bash
terraform apply
```

Show Terraform-managed resources:

```bash
terraform show
```

Display Terraform state:

```bash
terraform state list
```

Destroy resources:

```bash
terraform destroy
```

## Useful Docker Commands

Show running containers:

```bash
docker ps
```

Show all containers:

```bash
docker ps -a
```

Show Docker images:

```bash
docker images
```

View container logs:

```bash
docker logs terraform-nginx
```

Stop the container:

```bash
docker stop terraform-nginx
```

Remove the container:

```bash
docker rm terraform-nginx
```

## Cleanup

To remove the infrastructure created by Terraform:

```bash
terraform destroy
```

Enter:

```text
yes
```

Terraform will remove the Docker resources it manages.

## Git

Check the repository status:

```bash
git status
```

Add the project files:

```bash
git add .
```

Commit:

```bash
git commit -m "Add Terraform Docker setup"
```

Push to GitHub:

```bash
git push origin main
```

## .gitignore

The project ignores Terraform-generated files and sensitive state files.

```gitignore
.terraform/
*.tfstate
*.tfstate.*
crash.log
crash.*.log
```

> **Note:** `.terraform.lock.hcl` should normally be committed to Git because it locks provider versions and checksums.

## Technologies Used

* Terraform
* Docker
* Nginx
* Git
* GitHub
* Ubuntu/Linux

## Author

**Abhishek Singh**

---

## Learning Objectives

This project helps demonstrate:

* Terraform provider configuration
* Terraform Docker integration
* Infrastructure as Code (IaC)
* Docker image management using Terraform
* Docker container management using Terraform
* Terraform lifecycle commands
* Git/GitHub project management
* Infrastructure cleanup using `terraform destroy`
