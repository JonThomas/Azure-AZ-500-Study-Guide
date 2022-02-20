# Implement Conditional Access Policies including Multi-Factor Authentication

[Implement Conditional Access Policies including Multi-Factor Authentication](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/best-practices)

Conditional access policies:
* Using location, network location (IP), group membership, application, devices and real time risk detection ... ("**_automatically analyze signals_**")
* ... to block or allow users, require MFA, require compliant device, force password change or require terms of use
* Conditional access polices are enforced after first factor authentication
* Real time risk detection, using [Identity Protection](25-Configure%20Azure%20AD%20Identity%20Protection.md)
   * User risk (High, Medium, Low)
   * Sign in risk (High, Medium Low)

## Examples
* Require 2FA for everyone signing on from outside company perimeter.
* Require 2FA for all administrators
* Deny access for devices without malware protection

## Pricing

* Condiational access policies requires the second highest [Active Directory subscription license](https://azure.microsoft.com/en-us/pricing/details/active-directory/): Azure AD Premium P1


[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)