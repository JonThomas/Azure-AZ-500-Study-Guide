# Manage App registration permission consent

Consent workflow
1. Declare the set of delegated permissions the application needs, using the Azure portal
2. App must obtain a unique authorization code, using he /authorize endpoint
3. /authorize endpoint prompts user to sign in (if not already signed in)
4. User is show a consent page, if he hasn't already consented.
5. An authorization code is returned to the application, which is used to obtain access token

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)