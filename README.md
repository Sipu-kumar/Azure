# How to Deploy a Docker Container to Azure 🚀

This guide explains how to containerize an application using Docker and deploy it to **Microsoft Azure** using **Azure Container Registry (ACR)** and **Azure Container Instances (ACI)**.

---
## How to install Azure CLI to Windows 
Visit <a href="https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?view=azure-cli-latest&pivots=msi"> this site </a>and install Azure CLI

<img src="./Images/Images1.png"> 


After installation, close and reopen any active terminal window. Run the Azure CLI with the az command from either PowerShell or the Windows Command Prompt.

<img src="./Images/Azure done.png">

1. Now login to your Azure with Azure CLI <b>with command</b> 

    AZ login

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
