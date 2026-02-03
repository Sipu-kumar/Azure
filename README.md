# How to Deploy a Docker Container to Azure 🚀

This guide explains how to containerize an application using Docker and deploy it to **Microsoft Azure** using **Azure Container Registry (ACR)** and **Azure Container Instances (ACI)**.

---
## How to install Azure CLI to Windows 
Visit <a href="https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?view=azure-cli-latest&pivots=msi"> this site </a>and install Azure CLI

<img src="./Images/Images1.png"> 
## Prerequisites

Make sure you have the following installed and ready:

- Docker
- Azure CLI
- An Azure account
- A working application (Node.js / Java / Python / etc.)

---

## Step 1: Create a Docker Image

Create a `Dockerfile` in your project root.

### Example Dockerfile
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
