# Implement Storage Service Encryption

Azure storage data, including Resource Manager account, is always encrypted at rest - using technology similar to BitLocker encryption on Windows.

## Encrypt data using Microsoft managed key

* This is the default encryption scheme
* Works with all storage services

## Encrypt data at rest using own key

* Customer Managed key
   * Works with Blob storage and Azure Files (and [Queues and Tables](https://docs.microsoft.com/en-us/azure/storage/common/account-encryption-key-create), if the storage uses an encryption key scoped to the account rather than to the service)
   * Key is stored in Key Vault
* Customer Provided key
   * Works with Blob storage
   * The key is provided on each Blob storage request
   * Key is stored in customers key store

## (BitLocker Drive Encryption - Used to encrypt VM disks)

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)