# Configure subscription and resource permissions

* Azure RBAC roles can be assigned to management groups, subscriptions or resource groups

## Permission to management groups

[Management groups](https://docs.microsoft.com/en-us/azure/governance/management-groups/overview)
* A management group is a "container" above subscriptions for organizing permissions
* It lets you manage permissions across any number of subscriptions
* All management groups are within a single tenant.
* There is a single root management group within the tenant, with display name "Tenant root group"  
* Settings at the root management group, such as Azure custom roles or Azure Policy policy assignments, affects all resources in the tenant.
* Any user, by default, can create new management groups within a tenant [Reference](https://docs.microsoft.com/en-us/azure/governance/management-groups/how-to/protect-resource-hierarchy#setting---require-authorization)

![Management groups](img/ManagementGroups.png | width=100))
Figure: Example showing relationship between management groups and subscriptions

## Permission to subscriptions

Use the Owner RBAC role to make a user administrator for a subscription

Example: [Add an other subscription administrator](https://docs.microsoft.com/en-us/azure/cost-management-billing/manage/add-change-subscription-administrator)

1. Select the subscription 
1. Select Access Control (IAM) -> Role assignments -> Add role assignment
1. Role dropdown -> Select correct role
1. Select the users or groups to assign access to
1. Save

## Permission to administrative units
See [Manage administrative units](14-Manage%20administrative%20units.md)

## Permission to resources (via a resource groups)

Example: [Grant a user access to create and manage virtual machines in a resource group](https://docs.microsoft.com/en-us/azure/role-based-access-control/quickstart-assign-role-user-portal)

1. Select the resource group
1. (same as for subscription, start at step 2)

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)
