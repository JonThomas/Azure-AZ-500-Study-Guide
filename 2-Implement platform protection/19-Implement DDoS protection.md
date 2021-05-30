# Implement DDoS protection

## DDoS Basic

* Every property in Azure is protected by DDoS Basic for free.
   * Handled on cloud level by monitoring and real-time mitigation
* There is nothing to set up or configure with DDoS Basic
* Includes Azure CDN

## DDoS Standard

* DDoS Standard is designed for services deployed in a VNet.
   * For other services, DDoS Basic applies
* Can be enabled on a VNet, and requires no application or resource changes.
* DDoS Standard provides better logging, alerting and telemetry
* DDoS Standard requires "network contributor" role to set up

## Features

* When deployed with a WAF (for example [Application Gateway](15-Configure%20a%20Web%20Application%20Firewall%20(WAF)), DDoS protection protects at both level 3, 4 (the network layers) and level 7 (application level)
* Over 60 types of attacks can be mitigated

## Pricing

* A DDoS Standard plan costs almost $3000 pr. month.
* Includes 100 public IP adresses
* Extra IP costs $30 pr. month
* There is no need to create more than one DDoS plan.

[Addtional DDoS reading](https://azure.microsoft.com/en-us/blog/azure-ddos-protection-2020-year-in-review/)


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)