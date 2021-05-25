# Configure Azure Front Door service as an Application Gateway

* An "entry point", that enables highly scalable, fast and secure web applications
* Can be used to route client traffic to the fastest and most available application backend
   * Including URL-path based routing for requests
* Front Door is recilient, even in case of whole region failures
* Front Door provides several routing mechanisms to find the best backend environment
* Front Door privodes backend health monitoring options
   * It periodically sends a HTTP request to the backend and meaures the response time.
   * Default probe time is 30 requests pr. minute
   * 200 OK means the backend is up.
* Front Door routes DNS and HTTP traffic uses AnyCast (= **one to one-of-many**, vs for example Broadcast = one-to-all or Unicast = one-to-one), and always selects the closest, healthy environment:
   * Outer ring: Primary ring of environments. Contains environments closer to users. Preferred environments 
   * Inner ring: Falback ring of environments. Handles overflow from outer ring.
* Front Door uses Split TPS: Front Door optimizes network speed by breaking the end-to-end connection into multiple connections and using different parameters to transfer data across the different legs. The "short connection" between the end user and the Front Door environment means the connection gets established over three short roundtrips instead of three long round trips, which results in saving latency. The "long connection" between the Front Door environment and the backend can be pre-established and then reused
* The default domain is a subdomain of azurefd.net

## Features

* SSL offloading and SSL certificate management (auto-renewal and auto-provsioning)
* WAF: Provides protection against SQL injection, XSS, and many other exploits
   * WAF can also be deployed with Application Gateway
* Session affinity = ("sticky sessions"): Routes all requests from a client to the same backend
* Custom domain (overriding xyz.azurefd.net)

## Overlap with Application Gateway

[All features of Application Gateway](https://docs.microsoft.com/en-us/azure/application-gateway/features)

* SSL termination
* WAF
* URL-based routing
* Session affinity
* Multiple-site hosting
* HTTP to HTTPS redirection

## Features of Application Gateway only

* Autoscaling !!?? Isn't this required also by Front Door?
* Connection draining - gracefully removal of backens

## Azure load balancers

1. Front Door: Global routing, with top tier performance and reliability
1. Traffic Manager: Lacks TLS termination and application layer processing(?)
1. Application Gateway: Load balance between servers at the application layer, within a region
1. Load Balancer: Network layer load balancing

# Azure Front Door pricing
* Pay for ingoing data ...
* ... and outgoing data ...
* ... and for each request (by the 10.000s)


[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)