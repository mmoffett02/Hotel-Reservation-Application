# D387 - Advanced Java
**Student ID:** 012029134
**Mikaela Moffett**

## Part C3: Deployment to the Cloud

This document describes how to deploy the current multithreaded Spring application to the cloud using Microsoft Azure as the service provider.

### Steps to Deploy the Application to Azure

1. **Create an Azure Account**
    - If you don't have an Azure account, sign up at [Azure](https://azure.microsoft.com/) and create a free account.

2. **Install Azure CLI**
    - Download and install the Azure CLI from [here](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli). Follow the instructions for your operating system.

3. **Login to Azure**
    - Open your terminal and login to Azure using the command:
      ```sh
      az login
      ```
    - This will open a browser window for you to log in with your Azure account.

4. **Create a Resource Group**
    - Create a resource group in Azure where all resources will be stored:
      ```sh
      az group create --name D387ResourceGroup --location eastus
      ```

5. **Create an Azure Container Registry (ACR)**
    - Create a container registry to store your Docker images:
      ```sh
      az acr create --resource-group D387ResourceGroup --name D387Registry --sku Basic
      ```

6. **Login to ACR**
    - Login to the newly created container registry:
      ```sh
      az acr login --name D387Registry
      ```

7. **Tag and Push Docker Image**
    - Tag your Docker image with the ACR login server name:
      ```sh
      docker tag d387_sample_code D387Registry.azurecr.io/d387_sample_code:v1
      ```
    - Push the image to ACR:
      ```sh
      docker push D387Registry.azurecr.io/d387_sample_code:v1
      ```

8. **Create an Azure App Service Plan**
    - Create an App Service plan in Azure:
      ```sh
      az appservice plan create --name D387AppServicePlan --resource-group D387ResourceGroup --sku B1 --is-linux
      ```

9. **Create a Web App**
    - Create a Web App for Containers in Azure:
      ```sh
      az webapp create --resource-group D387ResourceGroup --plan D387AppServicePlan --name D387App --deployment-container-image-name D387Registry.azurecr.io/d387_sample_code:v1
      ```

10. **Configure Web App**
    - Configure the Web App to use the container registry:
      ```sh
      az webapp config container set --name D387App --resource-group D387ResourceGroup --docker-custom-image-name D387Registry.azurecr.io/d387_sample_code:v1 --docker-registry-server-url https://D387Registry.azurecr.io
      ```

11. **Browse to the Web App**
    - Open the application in your web browser:
      ```sh
      az webapp browse --name D387App --resource-group D387ResourceGroup
      ```

By following these steps, you will have successfully deployed your multithreaded Spring application to the cloud using Microsoft Azure.

