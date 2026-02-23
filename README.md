# 🚀 Getting started with Strapi

Strapi comes with a full featured [Command Line Interface](https://docs.strapi.io/dev-docs/cli) (CLI) which lets you scaffold and manage your project in seconds.

### `develop`

Start your Strapi application with autoReload enabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-develop)

```
npm run develop
# or
yarn develop
```

### `start`

Start your Strapi application with autoReload disabled. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-start)

```
npm run start
# or
yarn start
```

### `build`

Build your admin panel. [Learn more](https://docs.strapi.io/dev-docs/cli#strapi-build)

```
npm run build
# or
yarn build
```

## ⚙️ Deployment

Strapi gives you many possible deployment options for your project including [Strapi Cloud](https://cloud.strapi.io). Browse the [deployment section of the documentation](https://docs.strapi.io/dev-docs/deployment) to find the best solution for your use case.

```
yarn strapi deploy
```

## 📚 Learn more

- [Resource center](https://strapi.io/resource-center) - Strapi resource center.
- [Strapi documentation](https://docs.strapi.io) - Official Strapi documentation.
- [Strapi tutorials](https://strapi.io/tutorials) - List of tutorials made by the core team and the community.
- [Strapi blog](https://strapi.io/blog) - Official Strapi blog containing articles made by the Strapi team and the community.
- [Changelog](https://strapi.io/changelog) - Find out about the Strapi product updates, new features and general improvements.

Feel free to check out the [Strapi GitHub repository](https://github.com/strapi/strapi). Your feedback and contributions are welcome!

## ✨ Community

- [Discord](https://discord.strapi.io) - Come chat with the Strapi community including the core team.
- [Forum](https://forum.strapi.io/) - Place to discuss, ask questions and find answers, show your Strapi project and get feedback or just talk with other Community members.
- [Awesome Strapi](https://github.com/strapi/awesome-strapi) - A curated list of awesome things related to Strapi.
# 🚀 Strapi Deployment on AWS ECS Fargate with Terraform & CI/CD

## 📌 Overview

This project demonstrates how to deploy a Strapi application on AWS using ECS Fargate, fully managed with Terraform and automated through GitHub Actions. CloudWatch is used for logging, monitoring, and alarms to ensure visibility into application performance.

---

# Strapi Deployment on AWS ECS using Fargate Spot (Terraform + CI/CD)

## Project Overview

This project demonstrates how to deploy a containerized Strapi application on AWS using ECS with Fargate Spot. The infrastructure is provisioned using Terraform, and deployment is automated using GitHub Actions. The service runs on Fargate Spot to optimize cost, and CloudWatch logging is intentionally not used as per task requirements.

---

## Architecture

- Strapi application containerized using Docker
- Docker image stored in Amazon ECR
- Infrastructure created using Terraform
- ECS Cluster and Service run on Fargate Spot
- Public access enabled on port 1337
- CI/CD pipeline builds and deploys automatically

---

## Technologies Used

- AWS ECS
- AWS Fargate Spot
- Amazon ECR
- Terraform
- Docker
- GitHub Actions
- Strapi (Node.js)

---

## Deployment Flow

1. Dockerfile builds the Strapi container image
2. GitHub Actions builds and pushes image to ECR
3. Terraform provisions AWS infrastructure
4. ECS service runs the container on Fargate Spot
5. Application becomes accessible via public IP

---

## Terraform Resources

- ECS Cluster
- ECS Task Definition
- ECS Service (Fargate Spot)
- Security Group
- IAM Role
- ECR Repository

---

## Key Configuration

- Port 1337 exposed for Strapi
- Public IP assigned to ECS task
- Capacity provider set to FARGATE_SPOT
- CloudWatch logging removed

---

## How to Deploy

### 1. Initialize Terraform

```bash
terraform init
2. Plan Infrastructure
terraform plan
3. Apply Changes
terraform apply
Verify Deployment

Go to AWS Console → ECS → Cluster

Open running task

Confirm Capacity Provider shows Fargate Spot

Cost Optimization

Fargate Spot uses spare AWS capacity, reducing compute cost compared to standard Fargate.

What Was Changed for Task

Switched ECS service from Fargate to Fargate Spot

Removed CloudWatch logging configuration

Verified deployment in ECS console

Repository Structure
app/                → Strapi application
terraform/          → Infrastructure code
.github/workflows/  → CI/CD pipeline
Dockerfile          → Container definition
Author

Namit Agrawal



