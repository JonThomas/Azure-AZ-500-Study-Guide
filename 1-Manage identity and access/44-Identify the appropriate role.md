# Identify the appropriate role

## Classic subscription roles

## Azure AD roles

[Azure AD roles reference](https://docs.microsoft.com/en-us/azure/active-directory/roles/permissions-reference)

* Role: A collection of actions that the assigned identity can perform. Action examples: "Create disk". "Scale DB".
* A role answers the question: "**What** can be done"


* Global administrator
   * Only one who can set up [password writeback](15-Configure%20password%20writeback.md)
* Privileged role administrator
   * Can set up [Administrative units](14-Manage%20administrative%20units.md)
* User administrator
* Application developer
* Billing administrator
* ... and many more

## Azure roles, aka Azure resource roles
* Owner: Full access to the resources in Azure RBAC 
   * Use this role to add a new subscription administrator, for example
* Contributor: Full access to all resources, but can delegate responsibilities (add/ remove access; share image galleries; assign roles etc)
* Reader: Can view all resources, but can change anything
* ...
* User Access Administrator: Can manage user access to Azure resources. The only role other than Owner who can manage user access?

Link to [a good video that ties together a several identity concepts in Azure](https://www.youtube.com/watch?v=4v7ffXxOnwU)



[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)