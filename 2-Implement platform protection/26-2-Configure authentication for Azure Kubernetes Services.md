# Configure authentication for Azure Kubernetes Services

* Two ways of authenticate and authorize access to Kubernetes clusters:
   * Kubernetes RBAC: Users and groups can be granted the access to the resources they need by using 
      * Kubernetes RBAC is designed to work on Kubernetes resources within an AKS cluster
   * It is possible to secure an Azure Kubernetes Service (AKS) even further, by using Azure Active Directory and Azure RBAC
      * Azure RBAC is designed to work with resources within your Azure Subscription

## Kubernetes RBAC

* Roles
* ClusterRoles
* RoleBindings
* ClusterRoleBindings
* Kubernetes service account

## Application Gateway Ingress Controller

[What is Application Gateway Ingress Controller?](https://docs.microsoft.com/en-us/azure/application-gateway/ingress-controller-overview)

* The Application Gateway Ingress Controller (AGIC) is a Kubernetes application that makes it possible to for AKS to use the Application Gateway.
* Provides TSL and WAF functionality to the AKS Cluster
* Eliminates the need for an other load balancer/ public IP in front of the cluster.
* Improves performance

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)