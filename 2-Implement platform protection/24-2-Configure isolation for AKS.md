# Configure isolation for AKS

* Isolation for AKS: The ability to deploy Kubernetes Cluster on isolated virtual machines
* Creating an Kubernetes Cluster also creates a Service Principal
   * The Service Principal needs to be granted the push and pull roles to read and pull images from the Azure Container Registry.
* [Enhance security in the AKS cluster with AD integration](https://docs.microsoft.com/en-us/azure/aks/concepts-identity#azure-ad-integration)

## Design clusters for multi-tenancy

* Teams and workloads (environments) can be logically isolated in the same cluster
* Logical isolation: A Kubernetes [Namespace](https://docs.microsoft.com/en-us/azure/aks/concepts-clusters-workloads#namespaces) creates a logical isolation boundary

![Kubernetes namespace](img/KubernetesNamespaces.png)

Figure: Namespaces logically group resources such as pods and deployments, to divide the AKS cluster and restrict access to the resources

* Physical isolation: Create a cluster for each team/ environment.
   * Use for example in a multi tenant scenario where not all tenants can be trusted, since multiple tenants are working on a shared common infrastructure.

[Return to Implement platform protection](README.md)

[Return to Table of Contents](../README.md)