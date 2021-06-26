# Manage permissions to secrets, certificates, and keys

## Authorization

Authorization uses a combination of Azure RBAC and Azure Key Vault access policies.
When a user is granted permissions to read keys, they can read all keys: Key Vault doesn't support permissions on object level (for example permission to a specific key)

* Azure RBAC roles
   * Key Vault Contributor ()

## Key

* A key is
* Key permissions: 
   * Get

## Secret

* Secret: A connectionstring or password
* Secret permissions: 
   * Get: Read the value of the password (Decrypt key)

## Certificates

* A certificate is

[Return to Secure data and applications](README.md)

[Return to Table of Contents](../README.md)