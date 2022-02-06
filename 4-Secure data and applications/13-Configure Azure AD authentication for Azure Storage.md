# Configure Azure AD authentication for Azure Storage

[Configure Azure AD Authentication for Azure Storage](https://docs.microsoft.com/en-us/azure/storage/common/storage-auth-aad)

## Azure

[Assign an Azure role for access to blob data](https://docs.microsoft.com/en-us/azure/storage/blobs/assign-azure-role-data-access)

* Azure RBAC Roles
   * Storage Blob Data Owner - Owner. Data Lake Storage Get2 only.
   * Storage Blob Data Contributor - Read/ Write/ Delete on Blob storage resources
   * Storage Blob Data Reader - Read-only
   * Storage Blob Delegator - Can delegate access by issuing SAS' (Shared Access Signatures)
* Azure AD can be used to authenticate against any storage accounts.
* The RBAC _Contributor_ role is valid for the Management plane only (similar to [Key vault](32-Manage%20permissions%20to%20secrets,%20certificates,%20and%20keys.md#azure-rbac-roles))

## Hybrid environments

* Azure AD Domain Services (ADDS) in Azure can be used to allow an on-prem AD to perform the authentication to an Azure storage account

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)