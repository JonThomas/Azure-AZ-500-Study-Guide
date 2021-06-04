# Configure authentication for Azure Container Registry

## Azure Container Registry (ACR)

[Introduction to private Docker Container Registries](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-intro)

* Private Docker images and related artifacts can be stored in the Container Registry
* Use Container Registry in the deployment pipeline to pull images to various deployment targets
   * Azure Kubernets Service (AKS), Docker Swarm, App Service, Batch, Service Fabric etc.
* Use Container Registry Tasks to build container images
   * Automatically rebuild application images when base images are updated
   * Automate image build on commit
* Work with ACR with plugins to VSCode

## Configuration options when creating ACR

* Private key for encrypting data at rest
* Public/ Private IP address

## Configure authentication

* End users can access the registry using Azure CLI (*az acr login*) or the *docker login* command
* Access to the registry:
   * End users log in using an Azure identity
      * Docker CLI and Docker daemon must be installed
      * Authentication using *az acr login* is only valid for 3 hours.
      * If Docker deamon hasn't been installed, switch *-expose-token* can be used to get the access token. Then log in using the token and user name *00000000-0000-0000-0000-000000000000* (!)
   * Applications can authenticate using a [Service Principal](../1-Manage%20identity%20and%20access/11-Configure%20security%20for%20service%20principals.md) for headless scenarios
      * Multiple service principals can be assigned to the registry
      * Roles include: *AcrPull*, *AcrPush* (pull and push), *Owner* (pull, push, assign roles to others)
   * An Admin account.
      * Has full permissions to the registry
      * User name is the name of the container registry. 
      * Disabled by default
      * Admin account is required in some scenarios
      * Two passwords are provided (useful to remain connected to the registry while regenerating the other)

## Other security features of ACR

* Images are transferred over HTTPS. TLS 2.0 is required to connect.
* Images can be signed, using [Content Trust](https://docs.microsoft.com/en-us/azure/container-registry/container-registry-content-trust)
* Images can optionally be scanned by [Azure Defender for container registries](https://docs.microsoft.com/en-us/azure/security-center/defender-for-container-registries-introduction) whenever an image is pushed to the registry


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)