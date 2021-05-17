# Configure authentication methods

![Azure AD Authentication methods](img/authentication-methods.png)
* OAuth
* Passwordless (most secure)

## Authentication in hybrid scenarios
### Pass Through Authentication (PTA)
[Pass through authentication](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-pta-how-it-works)
* Used to delegate authentication to on-site AD

### Password hash synchronization
[Password hash synchronization](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-phs)
* Passwords are maintained in on-site AD, and a password hash is synchronized to Azure to enable sign in to Azure with on-site domain credentials
* Enables Leaked credential detection: User account will be tag'ed as "High risk" account if the username and password is found in a breach


[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)

TODO: https://docs.microsoft.com/en-us/azure/security/fundamentals/choose-ad-authn