# Configure security for service principals

[Configure security for service principals](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/service-accounts-principal)

## General
* A service principal functions as the identity for an application instance, including who can access it and which resources the application can access. 
> Service principals is an AD concept, so the application has to be registered with AD. See [Manage application access](README.md)
* A service principal is created in each tenant where the application is used (so one application can have multiple service principals) In other words: The service principal references the Object Id of the application, not the globally unique Application Id.

## Service principal vs Security principal vs User principal
To aviod confusion, I've listed several types of principals:
* A service princpal is the identity of the application.
* A user principal is the identity of the user
* A security principal is an umbrella term for all principals
   * Definition: Security principal is an Azure object (identity) that can be assigned to a role (ex. users, groups, or applications)
   * Answers the question: "**Who** can do it"

## Service Principal security
* Prefer certificate based authentication over username/ password (client secrets)
* If using client secrets: Store them in Azure Key Vault
* Prefer Service Principals and Managed Identities over Azure user accounts. (Managed Identities is now prefered over Service Principals)
* Apply least privileges principle when assigning roles to Service Principals
   * The default Azure RBAC role is Contributor, which can create and manage any resource, but cannot grant access to others. See [Built in role Contributor](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#contributor)
* Monitor Service Principal signins
* Monitor and react to consents to multi-tenant apps. See [Manage application access](README.md)
> TODO: What is the relation between RBAC and Service Principal

List all service principal:

    Connect-AzureAD -TenantId xyz
    Get-AzureADServicePrincipal

(There are about 20 service principals in my pretty empty tenant)

Link to [a good video that ties together a several identity concepts in Azure](https://www.youtube.com/watch?v=4v7ffXxOnwU)

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)