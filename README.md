# Azure Container Instance with Docker

## Project Overview
This project demonstrates how to containerize a Python Flask application using Docker and deploy it to Azure Container Instance (ACI) using Azure Container Registry (ACR).

---

## Technologies Used
- Python
- Flask
- Docker
- Azure Container Registry (ACR)
- Azure Container Instance (ACI)
- GitHub
- VS Code

---

## Project Structure

Project3-ContainerApp/
│
├── app.py
├── requirements.txt
├── Dockerfile
└── README.md

---

## Flask Application

The Flask application displays a simple message:

Hello Jyoti, Azure Container is working!

---

## Docker Commands Used

### Build Docker Image

docker build -t project3app .

### Run Docker Container Locally

docker run -p 80:80 project3app

### Tag Docker Image

docker tag project3app jyotiacr30.azurecr.io/project3app:v1

### Push Docker Image to Azure Container Registry

docker push jyotiacr30.azurecr.io/project3app:v1

---

## Azure Commands Used

### Login to Azure Container Registry

az acr login --name jyotiacr30

### Create Azure Container Instance

az container create \
--resource-group AZ204-Project3-RG \
--name project3container \
--image jyotiacr30.azurecr.io/project3app:v1 \
--registry-login-server jyotiacr30.azurecr.io \
--registry-username jyotiacr30 \
--os-type Linux \
--dns-name-label jyotiproject3demo \
--ports 80 \
--cpu 1 \
--memory 1

---

## Azure Container Registry Details

- Registry Name: jyotiacr30
- Resource Group: AZ204-Project3-RG

---

## Azure Container Instance Details

- Container Name: project3container
- OS Type: Linux
- Region: East US

---

## Application URL

http://jyotiproject3demo.eastus.azurecontainer.io

---

## GitHub Repository

Add your GitHub repository link here:

https://github.com/YOUR_GITHUB_USERNAME/YOUR_REPOSITORY_NAME

---

## Screenshots

Add screenshots of:
1. Docker build success
2. Docker push success
3. Azure container deployment
4. Browser output
5. GitHub repository

---

## Outcome

Successfully deployed a Dockerized Python Flask application on Azure Container Instance using Azure Container Registry.
