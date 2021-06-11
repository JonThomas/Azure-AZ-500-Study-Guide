# Implement Azure Disk Encryption

## Linux VMs

[Azure Disk Encryption for Linux VMs](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/disk-encryption-overview)

* Uses DM-Crypt feature in Linux to encrypt OS- and data-disks
* Requires Key Vault to control and manage disk encryption keys

## Setting up disk encryption

[Create and encrypt a Windows VM with the Azure CLI](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/disk-encryption-cli-quickstart)

1. Create a resource group
1. Create a key vault, enabled for disk encryption
1. Optionally add a Key Encryption Key to the vault for extra security
1. Encrypt the VM using one of the following commands (encryption key is generated and stored to key vault automatically)

> az vm encryption enable -g MyResourceGroup --name MyVM --disk-encryption-keyvault myKV

> use the Set-AzVMDiskEncryptionExtension commandlet

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)