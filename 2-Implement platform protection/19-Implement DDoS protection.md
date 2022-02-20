# Implement Azure DDoS Protection

[Implement Azure DDoS Protection](https://docs.microsoft.com/en-us/azure/ddos-protection/ddos-protection-overview)

Learn: [Describe Azure DDoS protection](https://docs.microsoft.com/en-us/learn/modules/describe-basic-security-capabilities-azure/3-describe-azure-ddos-protection)

## About DDoS

* Three frequent types of attack:
   * Volumetric: Sending large volumes of seemingly legitimate traffic. Measured in bits per second
   * Protocol: Sending large volumes of protocol requests. Measured in packets per second
   * Resource (application) layer: Targets web application packets
* Azure DDoS protection tries to identify DDoS attacks, and will block traffic from the attacker.
* Azure can scale computing needs to meet demand during an attack, and at the same time ensure that the network load only reflects actual customer usage

## DDoS Basic

* Every property in Azure is protected by DDoS Basic for free.
   * Handled on cloud level by monitoring and real-time mitigation
* Includes Azure CDN
* There is nothing to set up or configure with DDoS Basic

## DDoS Standard

* DDoS Standard is designed for services deployed to Azure VNet resources.
   * For other services, DDoS Basic applies ??
* Can be enabled on a VNet, and requires no application or resource changes.
* DDoS Standard provides better logging, alerting and telemetry
   * Uses adaptive tuning and machine learning on the applications network traffic patterns to detect threats
* Policies are applied to public IP addresses
* DDoS Standard requires "network contributor" role to set up

## Features

* When deployed with a WAF (for example [Application Gateway](15-Configure%20a%20Web%20Application%20Firewall%20(WAF)%20on%20Azure%20Application%20Gateway.md)), DDoS protection protects at both level 3, 4 (the network layers) and level 7 (application level)
* Over 60 types of attacks can be mitigated
* See [full list of features](https://docs.microsoft.com/en-us/azure/ddos-protection/ddos-protection-overview#features)

## Pricing

* A DDoS Standard plan costs almost $3000 pr. month.
* Includes 100 public IP adresses
* Extra IP costs $30 pr. month
* There is no need to create more than one DDoS plan.

Addtional reading from the Azure networking team: [A summary of DDoS protection in 2020](https://azure.microsoft.com/en-us/blog/azure-ddos-protection-2020-year-in-review/)


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)