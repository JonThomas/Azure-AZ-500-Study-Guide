# Implement Service Endpoints

[Implement Service Endpoints](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview)

* A VNet Virtual Service Endpoint provides secure and direct connectivity to Azure Services
   * Used for example to connect your Azure resource directly to CosmosDb, KeyVault or SQLServer, without using a public IP address
* Currently (as of 30th of May 2021), [13 services](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-service-endpoints-overview) exposes sevice endpoints in most Azure regions.
* Whitout using a Service Endpoint, traffic from a VNet to an Azure Service uses an public IP address 
* Service Endpoints are free of charge
* Using a service endpoint is beneficial, because:
   * Improved security: 
      * The identity configured in your VNet is extended to the service
      * No public IP address in necessary.
      * Traffic to the service is only allowed from your VNet
   * It provides optimal routing between your resource and the service (Not over the internet: Service Endpoints are using Azure backbone network)
      * Less internet traffic makes it easier to monitor the other internet traffic
   * Simple to set up
      * No public IP to set up 
      * No NAT-ing
      * Gateway devices aren't necessary

## Limitations

* The VNet must have been deployed using the Azure Resouce Manager
* Service endpoints can't be used from on-premise
   * To access service endpoints from on-premise, use Express Route, or allow public IP addresses from your on-premise by adding them through the firewall configuration for service resources
* Service endpoints work across regions for most cases, but not with Azure SQL, and not always with geo redundant- or read-only geo redundant storage

## Setup

1. Enable a service endpoint on a subnet in your VNet.
   1. Multipe service endpoints can be configured on a subnet.
1. Create a VNet rule to secure the Service Endpoints to your VNet

## Considerations

* Network Security Groups allow outbound traffic to the internet, and traffic from you VNet to Service Endpoints by default

![VNet service endpoint overview](img/VNetServiceEndpointOverview.png)

Figure: Showing relationship between VNet, Azure services (here: Azure Storage), and how to use Service Endpoint from On-Premise

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)