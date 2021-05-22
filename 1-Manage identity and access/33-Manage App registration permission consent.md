# Manage App registration permission consent

## Consent workflow (Delegated permissions)

1. Declare the set of delegated permissions the application needs, using the Azure portal
1. App must obtain a unique authorization code, using the */authorize* endpoint
1. */authorize* endpoint prompts user to sign in (if not already signed in)
1. User is show a consent page, if he hasn't already consented.
1. An authorization code is returned to the application, which is used to obtain access token

## Application permissions
* Application permissions are granted when setting up the application

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)