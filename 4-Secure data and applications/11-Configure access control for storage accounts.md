# Configure access control for storage accounts

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

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)