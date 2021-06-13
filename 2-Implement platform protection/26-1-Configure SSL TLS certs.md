# Configure SSL/TLS certs

* Use an SSL/ TLS certificate to enable HTTPS on your site
* An application in Azure App Service can access public and private certificates that have been added to App Service
   * For example to authenticate against an external service, or to enrypt credentials
* Tiers F1 and D1 don't allow custom SSL, so adding a certificate does not make sense
* Certificates that can be added to App Service
   * Free App Service managed certificate
   * Not free App Service managed certificate
   * Certificate from Key Vault
   * Upload Private key certificate (.pfx)
   * Upload Public key certificate (.cer) to access remote resources (not for securing custom domains)

## Configure an app to use an SSL certificate

1. Create an App Service app
1. [Add the certificate to Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-certificate)
   * Upload a private certificate to App Service
      1. Export the certificate to .pfx
      1. Upload to App Service
   * Upload a public certificate to App Service
      1. Since public certs aren't used for SSL, the application code needs access to it. See note below.
   * Import an App Service certificate (free, or bought from Microsoft)
      1. Obtain certificate
      1. Store certificate in Key Vault   
      1. Import App Service Certificate
   * Import a certificate from Key Vault
      1. Must authorize the resource provider to be able to read from Key Vault
      1. Upload to App Service
1. [For custom domains, create a certificate binding](https://docs.microsoft.com/en-us/azure/app-service/configure-ssl-bindings#create-binding)

> If the application code needs to access to the certificate (not relevant for SSL certs):
>    * Add the certificate thumbprint to the WEBSITE_LOAD_CERTIFICATES app setting to make the certificate available to the app
>    * Pretty much same procedure for Container apps, Windows apps and for web apps

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)