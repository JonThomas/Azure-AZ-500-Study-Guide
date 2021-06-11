# Configure SSL/TLS certs

* An application in Azure App Service can access public and private certificates that have been added to App Service
   * For example to authenticate against an external service, or to enrypt credentials
* Tiers F1 and D1 don't allow custom SSL, so adding a certificate does not make sense
* Certificates that can be added to App Service
   * Free App Service managed certificate
   * Not free App Service managed certificate
   * Certificate from Key Vault
   * Upload Private certificate
   * Upload Public certificate

## Configure an app to use certificates

[Add a TLS/SSL certificate in Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-certificate)

1. Create an App Service app
1. Add the certificate to Azure App Service
1. Add the certificate thumbprint to the WEBSITE_LOAD_CERTIFICATES app setting to make the certificate available to the app
   * Pretty much same procedure for Container apps, Windows apps and for web apps

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)