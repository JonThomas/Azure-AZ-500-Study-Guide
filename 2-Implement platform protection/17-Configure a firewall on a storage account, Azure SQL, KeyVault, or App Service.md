# Configure a firewall on a storage account, Azure SQL, KeyVault, or App Service

[Configure a firewall on a storage account, Azure SQL, KeyVault, or App Service](https://docs.microsoft.com/en-us/azure/storage/common/azure-defender-storage-configure)

## Configure Azure Defender for Storage

[Configure Azure Defender for Storage](https://docs.microsoft.com/en-us/azure/storage/common/azure-defender-storage-configure)

* Protects data in Azure blogs, Azure files, and Data Lakes.
* Defender for Storage can be configured on the subscription level or on an individual storage account
* Azure Portal -> select storage account -> Settings -> Advanced Security -> Enable Azure Defender for Storage
* If the Storage Account is configured to only allow access from a Private endpoint or a VNet, then the content won't be accessible from a local computer, even when accessing the content through the Portal

## Configure Azure Defender for SQL

[Configure Azure Defender Azure SQL](https://docs.microsoft.com/en-us/azure/azure-sql/database/azure-defender-for-sql)

* Features:
   * Vulnerability assessment: Provides visibility into potential DB vulnerabilities, and includes steps on how to fix them
      * A storage account is automatically created to store vulnerablity scans
      * The weekly scan results can be sent on email
   * Advanced Threat Detection: Detects anomalous activity, provides alerts and recommended action
      * Alerts can be sent on email, or seen in the Azure portal
* Enabling Defender for Azure SQL requires SQL security manager role, or one of the database or server admin roles
* Azure Defender can be enabled on the subscription level, or on a particular server/ managed instance
   * Azure Defender can be enabled with one click to protect all databases on a server, or in a SQL Managed Instance. 

## Configure Azure Defender for Key Vault

[Configure Azure Key Vault firewalls and virtual networks](https://docs.microsoft.com/en-us/azure/key-vault/general/network-security)

* Defender for Key Vault is disabled by default
* "Allow trusted Microsoft Serices to bypass this firewall" - This option allows a set of Microsoft services - where Microsoft controls all of the code - to access Key Vault, for example Azure Backup or Azure Event Hub
* Give services with static IPs access to Key Vault by adding their IP-address to the firewalls allow list 
* Give services with dynamic IPs access to Key Vault by creating the resource in a Virtual Network, and add the VNet and the subnet to the firewalls allow list
* Access can also be given by setting up a private link between Key Vault and a resource in a VNet

## Configure Azure Defender for App Service

[Protect your web apps and APIs](https://docs.microsoft.com/en-us/azure/security-center/defender-for-app-service-introduction)

* Azure App Service is a fully managed platform for building and hosting your web apps and APIs. 
* Azure Defender for App Service can identify attacks targeting applications running on App Service.
   * This is made possible by monitoring requests, as they go through several gateways before they hit the application.
* Azure Defender is automatically enabled for App Service, if Defender is enabled on the subscription level. It not, then Azure Defender for App Service can be enabled within Azure Defender


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)