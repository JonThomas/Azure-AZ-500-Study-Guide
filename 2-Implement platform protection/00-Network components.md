# Network Components

## Subnet

[Why subnet your network? The benefits of subnetting](https://community.spiceworks.com/networking/articles/2476-why-subnet-your-network-the-benefits-of-subnetting)

Class A IP-range: 16.7 million addresses (10.x.x.x)
Class B IP-range: 65.000 devices (10.10.x.x)
Class C IP-range: 254 devices (10.10.10.x)

### Benefits

1. Avoids early internet problem of assigning 16.7 million precious IPv4 addresses to a single organization
1. Can set up logical network divisions
   * Boundaries between departments: One subnet for sales, one for marketing, ...
1. Imporove network security
   * Logical divisions gives control over who can access what, by setting rules on traffic between subnets
1. Improve network performance and speed 
   * Network broadcasting is reduced by containing it wihtin a subnet instead of the whole net

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)