# Configure authentication methods

[Configure authentication methods including password hash and Pass Through Authentication (PTA), OAuth and passwordless](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-methods)

![Azure AD Authentication methods](img/authentication-methods.png)
* OAuth
* Passwordless (most secure)

## Azure Ad Connect

[What is Azure AD Connect?](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-azure-ad-connect)

* Azure AD Connect is required for all hybrid authentication methods
* Using Azure AD Connect is free.
* Use the Synchronization Rules Editor to control which users are synced with Azure AD.

## Authentication in hybrid scenarios

[Choose the right authentication method for your Azure Active Directory hybrid identity solution](https://docs.microsoft.com/en-us/azure/security/fundamentals/choose-ad-authn)

### Pass Through Authentication (PTA)
[Pass through authentication](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-pta-how-it-works)
* Used to delegate authentication to on-site AD
   * On site password policies and sign-in hours are enforced using this authentication method
* Supports Account Disabling, Account lockout, Account expiration, Password expiration and Logon hours
* Requires more hardware than Password hash synchronization

### Password hash synchronization (PHS)
[Password hash synchronization](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-phs)
* Passwords are maintained in on-site AD, and a password hash is synchronized to Azure to enable sign in to Azure with on-site domain credentials
* Enables Leaked credential detection (with Azure AD Premium P2): User account will be tag'ed as "High risk" account if the username and password is found in a breach
* Supports only Account Disabling (not Account lockout, Account expiration, Password expiration or Logon hours)

### ADFS federation
* Ensures user authentication happens on-site: Passwords are not synced to Azure
* Lots of features, including smart card authentication

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)