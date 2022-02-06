# Configure access control for storage accounts

[Configure Access Control for Storage Accounts](https://docs.microsoft.com/en-us/azure/storage/blobs/security-recommendations)

Storage:
* Blob
* File
* Table
* Queue
* Web
* DFS

## Creating storage account - security

* Infrastructure encryption can be enabled when creating the account (not enabled by default): Data is then encrypted at both the service level and at the infrastructure level
* Network connectivity is configured when creating a storage account, and a firewall will be added:
   * Public endpoints (all networks)
   * Public endpoints (selected VNets, se below)
   * Private endpoint (use a private IP from an Azure VNet to access the key vault)
      * Must choose a storage type (see above) and a VNet

## Access a storage account

* Using the storage account keys: Will gain access to the whole account from any location, for as long as the keys are valid
* Using Shared Access Signatures (SAS): Can configure fine grained access control

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)