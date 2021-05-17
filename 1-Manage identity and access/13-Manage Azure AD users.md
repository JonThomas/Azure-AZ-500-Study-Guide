# Manage Azure AD users

* An Azure user is required to access any Azure resource.
* Use Azure AD Connect to provide synchronization for on-premise user accounts and passwords and for single sign-on (SSO) functionality.

## Password policies
[Password policies](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-sspr-policy)

* Passwordpolicies can't be set up for AD native users, with the exception of password expiry
* UPN (User Principal Name) can contain the following special characters: ' . - _ ! # ^ ~
* Unicode characters are not allowed in passwords
* Two-gate administrator self service password reset (SSPR) policy states that two pieces of authentication data is required: email, auth app or phone (not security question)


[Return to Manage identity and access](README.md)
[Return to Table of Contents](../README.md)