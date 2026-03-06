# Terraform Docker Microservices Deployment 🚀

This project demonstrates how to deploy a Dockerized microservice on AWS using Terraform and automate deployments using a CI/CD pipeline.

The project provisions AWS infrastructure using Terraform, builds a Docker container for a Node.js microservice, and deploys it to an EC2 instance.

---

# Architecture

Developer
↓
GitHub Repository
↓
GitHub Actions CI/CD
↓
DockerHub Image Registry
↓
AWS EC2 Instance
↓
Docker Container
↓
Node.js Microservice
↓
Browser Access

---

# Tech Stack

Infrastructure as Code
- Terraform

Cloud Provider
- AWS EC2
- VPC
- Security Groups
- Internet Gateway
- Route Tables

Containerization
- Docker
- DockerHub

Application
- Node.js

CI/CD
- GitHub Actions

---

# Project Structure


terraform-docker-microservices
│
├── docker
│ ├── backend
│ │ ├── Dockerfile
│ │ └── server.js
│ │
│ ├── nginx
│ │ └── nginx.conf
│ │
│ └── docker-compose.yml
│
├── terraform
│ ├── provider.tf
│ ├── vpc.tf
│ ├── subnet.tf
│ ├── igw.tf
│ ├── route-table.tf
│ ├── security.tf
│ ├── ec2.tf
│ ├── variables.tf
│ └── outputs.tf
│
└── README.md


---

# Application

The backend service is a simple Node.js HTTP server running inside a Docker container.

Example response:


Hello from Docker + Terraform Microservices Project By Ashish


---

# Infrastructure Deployment

Terraform provisions the following resources:

- VPC
- Public Subnets
- Internet Gateway
- Route Tables
- Security Groups
- EC2 Instance

Deploy infrastructure:


cd terraform

terraform init
terraform plan
terraform apply


After deployment, Terraform outputs the public IP of the EC2 instance.

---

# Docker Deployment

Build Docker image locally:


docker build -t ashishjo10/terraform-microservice-app ./docker/backend


Push image to DockerHub:


docker push ashishjo10/terraform-microservice-app


Run container on EC2:


docker run -d -p 3000:3000 --name backend ashishjo10/terraform-microservice-app


---

# Access the Application

Open the application in a browser:


http://<EC2_PUBLIC_IP>:3000


Example:


http://13.234.116.131:3000


---

# CI/CD Pipeline

The project includes a GitHub Actions pipeline that automatically:

1. Builds the Docker image
2. Pushes the image to DockerHub
3. Connects to EC2 via SSH
4. Pulls the latest image
5. Restarts the Docker container

Pipeline Trigger:


git push


---

# Features

- Infrastructure provisioning with Terraform
- Docker containerized microservice
- AWS EC2 deployment
- Automated CI/CD with GitHub Actions
- DockerHub image registry

---

# Author

Ashish Joseph

DevOps | Cloud | Terraform | Docker | AWS
