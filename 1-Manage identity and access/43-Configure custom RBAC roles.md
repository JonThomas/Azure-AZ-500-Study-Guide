# Configure custom RBAC roles

* Azure comes with many built in roles: [Azure RBAC roles reference](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles)
* If none of the built in roles fit, you can create your own custom roles.
* Typically, a custom role is made by modifying an existing role, or by combining permissions used in different roles
* A role consists of **Actions**, **NotActions**, **DataActions** and **NotDataActions**. These operations dictate what the role can and can't do.
* The operations are described using the following format: 
   * {Company}.{ProviderName}/{resourceType}/{action}.
   * The wildcard '*' means All actions
   * Action operation example: Microsoft.Authorization/*/Delete
   * Data action operation example: Microsoft.Storage/storageAccounts/blobServices/containers/blobs/delete (Delete blob data)
* Role scope
   * Restrict the role to a specific resource: "/subscriptions/{sub-id}/resourceGroups/{rg-name}/{resource-name}"

## Example role
    {
      "Name": "Virtual Machine Operator",
      "Id": "88888888-8888-8888-8888-888888888888",
      "IsCustom": true,
      "Description": "Can monitor and restart virtual machines.",
      "Actions": [
        "Microsoft.Storage/*/read",
        "Microsoft.Network/*/read",
        "Microsoft.Compute/*/read",
        "Microsoft.Compute/virtualMachines/start/action",
        "Microsoft.Compute/virtualMachines/restart/action",
        "Microsoft.Authorization/*/read",
        "Microsoft.ResourceHealth/availabilityStatuses/read",
        "Microsoft.Resources/subscriptions/resourceGroups/read",
        "Microsoft.Insights/alertRules/*",
        "Microsoft.Insights/diagnosticSettings/*",
        "Microsoft.Support/*"
      ],
      "NotActions": [],
      "DataActions": [],
      "NotDataActions": [],
      "AssignableScopes": [
        "/subscriptions/{subscriptionId1}",
        "/subscriptions/{subscriptionId2}",
        "/providers/Microsoft.Management/managementGroups/{groupId1}"
      ]
    }


[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)