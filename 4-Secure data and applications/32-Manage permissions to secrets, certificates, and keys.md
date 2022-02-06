# Manage permissions to secrets, certificates, and keys

Manage permissions to [Secrets](https://docs.microsoft.com/en-us/azure/key-vault/secrets/about-secrets), [Certificates](https://docs.microsoft.com/en-us/azure/key-vault/about-keys-secrets-and-certificates#key-vault-certificates), and [Keys](https://docs.microsoft.com/en-us/azure/key-vault/about-keys-secrets-and-certificates#key-vault-keys)

## General notes

* When a user is granted permissions to read keys, they can read all keys: Key Vault doesn't support permissions on object level (for example permission to a specific key)
* The two planes in Key Vault have individual access controls:
   * Management plane: Where a user manages the key store
   * Data plane: Where the Key Vault content is stored

## Access a Key Vault

A new key vault can be set up to be accessed using Access Policies or RBAC Roles:

### Vault Access Policy

Three ways for an application to access the key vault (all three requires Azure AD):

* Application-only
   * The application represents service principal or managed identity
   * _objectid_ for the application must be specified in the access policy (_applicationid_ must *not* be specified)
* User-only
   * User accesses key vault from app registered in the tenant, for example Azure portal or Azure powershell.
   * _objectid_ for the application must be specified in the access policy (_applicationid_ must *not* be specified)
* Application-plus-user (compound identity)
   * The user is required to access the key vault from a specific application and the application must use the on-behalf-of authentication (OBO) flow to impersonate the user. 
   * Both _objectid_ (representing the user) and _applicationid_ (representing the application) must be specified in the access policy

### Azure RBAC roles

[Provide access to Key Vault keys, certificates, and secrets with an Azure role-based access control](https://docs.microsoft.com/en-us/azure/key-vault/general/rbac-guide)

To use RBAC roles with Key Vault, the key vault must be configured to use the 'Azure role-based access control' permission model 

* The _Key Vault Contributor_ role is valid for the Management plane only (Similar to [Storage account](13-Configure%20Azure%20AD%20authentication%20for%20Azure%20Storage.md#azure))
* Many roles exist for the data plane. Examples:
   * Key Vault Administrator (Perform all data plan operations). Cannot manage key vault resources or manage role assignments
   * Key Vault Certificate Officer (Perfor any action on certificates)
   * Key Vault Secrets Officer (Perfor any action on secrets)
   * Key Vault Crypto Officer (Perfor any action on keys)

## Keys

* A key is
* Key permissions: 
   * Get

## Secrets

(About Azure Key Vault secrets)[https://docs.microsoft.com/en-us/azure/key-vault/secrets/about-secrets]

* Secret: A connectionstring or password
* Secret permissions: 
   * Get: Read a secret (the value of the password) and tags on the secret
   * List: List all secrets, versions and tags of the secrets in the vault
   * Set: Create a secret
   * Delete
   * Recover: Recover a deleted secret
   * Backup: Back up a secret 
   * Restore: Restore a secres that has been backed up to a key vault
   * Purge (privileged): Permanently delete a deleted secret

## Certificates

* A certificate is

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)