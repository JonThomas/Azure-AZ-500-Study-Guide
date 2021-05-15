# Configure security for service principals

* A service principal functions as the identity for an application instance, including who can access it and which resources the application can access
> Service principals is an AD concept, so the application has to be registered with AD. See [Manage application access](1-Manage%20identity%20and%20access%20(30-35%25).md)
* A service principal is created in each tenant where the application is used (so one application can have multiple service principals) In other words: The service principal references the Object Id of the application, not the globally unique Application Id.

List all service principal:
    Connect-AzureAD -TenantId xyz
    Get-AzureADServicePrincipal