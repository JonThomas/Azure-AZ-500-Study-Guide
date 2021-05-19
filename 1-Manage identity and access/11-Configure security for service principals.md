# Configure security for service principals

## General
* A service principal functions as the identity for an application instance, including who can access it and which resources the application can access. Sort of like a Windows Service Account.
> Service principals is an AD concept, so the application has to be registered with AD. See [Manage application access](README.md)
* A service principal is created in each tenant where the application is used (so one application can have multiple service principals) In other words: The service principal references the Object Id of the application, not the globally unique Application Id.

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

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)