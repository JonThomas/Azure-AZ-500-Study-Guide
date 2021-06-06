# Configure security for different types of containers

## Deploy a container to Azure

1. [Create an ASP.NET Core Web API in a container](https://code.visualstudio.com/docs/containers/quickstart-aspnet-core)
1. [Create an Azure container registry using the Azure portal](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-get-started-portal)
   1. Create resource group
   1. Create Azure Container Registry
1. [Deploy application to Azure App Service](https://code.visualstudio.com/docs/containers/app-service#_push-the-image-to-a-container-registry)
   1. Tag the container
   1. Push the container to the Azure Container Registry
   * Either: Deploy the container to Azure App Service
      1. Create an App Service
      1. Deploy the container
   * Or: Deploy the container to Azure Container Instance
      1. Create the Container Instance (Se below)
      1. Deploy the container

## Azure Container Instance

[What is Azure Container Instance](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-overview)

> "Azure Container Instances offers the fastest and simplest way to run a container in Azure [...] that can operate in isolated containers"
> "For scenarios where you need full container orcestration, including service discovery across multiple containers, automatic scaling, [...] we recommend Azure Kubernetes Service (AKS)"
* No virtual servers involved
   * Enables faster startup times (seconds)
* An alternative to deploying containers to App Service
* The containerized application is made available at *customlabel.azureregion*.azurecontainer.io

## Creating Container Instance

* Choose networking:
   * Public ip, port and DNS name label
   * Private (choose [Virtual Network (VNet)](10-Secure%20the%20connectivity%20of%20virtual%20networks%20(VPN%20authentication,%20Express%20Route%20encryption).md) and subnet within the VNet)
   * None
* Restart policy
   * On failure
   * Always (it will always restart, whatever the reason is for stopping)
   * Never
* Environment variables
   * The value of Secure variables are only available within the container
   * The value of other variables can also be read within the portal

## Securing a Container Instance

* Azure Container Instance guarantees that the container is as isolated as a VM: Hypervisor-level security
* Portal deployment of a container from Azure Container Registry requires the ACR Admin-user to be enabled
* [Secure Environment variables](https://docs.microsoft.com/en-us/azure/container-instances/container-instances-environment-variables#secure-values)
   * Passwords and keys environment variables can be specified when setting up the container
   * These values are not visible in the container properties - only from within the container.

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)