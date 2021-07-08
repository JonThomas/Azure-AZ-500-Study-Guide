# Transfer Azure subscriptions between Azure AD tenants

## Concepts

* Tenant
   * Represents a single organization and the default directory assigned to it. The "default active directory".
   * Azure tenant is a dedicated and trusted Azure Active Directory's instance. 
   * A tenant is automatically created when your organization signs up for a Microsoft cloud service subscription, such as Microsoft Azure, Microsoft Intune, or Office 365. 

* Subscription:
   * Represents a billing entity and a security boundary. A subscription can only trust one tenant/ directory.
   * Azure tenant is a directory, whereas subscription is an object that represents a "folder" where you can put in your resources.
   * Subscriptions are tied to tenants. A single tenant can have many subscriptions, but vice versa is not possible.

## Transfer subscription to an other tenant

* Why?
   * Company merge, and you want to consolidate subscriptions
   * Consolidate a free subscription into company default tenant
   * An application depends on a subscription
* Some resources are not transferred to the other tenant
   * Users, Groups and Service principals must be recreated (or re-mapped) in the new tenant
   * Role assigmnents must be reassigned to the new resources
   * Custom roles are deleted
* Requires downtime
* Any key vaults must be reconfigured in the new tenant
* Encrypted data at rest might be unrecoverable if encryption key is tied to subscription
* Who? 
   * Only the billing administrator of an account can transfer ownership of a subscription




[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)