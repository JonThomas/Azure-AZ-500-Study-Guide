# Configure App registration permission scopes

* Permission scope = Permission sets = the set of permissions that an app requests/ needs/ offers, for example to access files, a persons calendar or the Azure key vault
* Scope definition: Scope is one ore more resources that the access applies to
* Scope answers the question: "**Where** does access apply?"
* Azure Identity Platform supports several well defined [OpenId Connect scopes](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent#openid-connect-scopes) and resource-based permissions.
* An app can request permission from users or administrators, who can grant them access.
   * The request is normally performed by appending the permission to the application Id URI, for example https://graph.microsoft.com/Calendars.Read
   * Some high privilege permissions can only be requested using an [administrator consent endpoint](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent#admin-restricted-permissions)
      * For example:
      * Read all user's full profiles by using User.Read.All
      * Write data to an organization's directory by using Directory.ReadWrite.All
* An application can request permissions by sending a GET request to the login provider, including the requested permissions as space separated list:
   * If the user hasn't already been granted these permissions, the Identity Platform asks the user to grant these permissions

        &scope=
        https%3A%2F%2Fgraph.microsoft.com%2Fcalendars.read%20
        https%3A%2F%2Fgraph.microsoft.com%2Fmail.send

## Delegated permissions vs Application permissions

* Application permissions: For background services without signed-in user. 
   * Permission can only be granted by an administrator.
   * Permissions are granted when setting up the application
   * *Effective permissions* are the permissions granted
* Delegated persmissions: For apps running in a user context.
   * Example: User must consent to let the app access the users calendar in Azure
   * Permision is granted when user logs in
   * *Effective permissions* are the least common denominator of the curent signed in users permissions and the apps permissions

![Scopes](img/Scopes.png | width=100)
Figure: Scope hierarchy

Link to [a good video that ties together a several identity concepts in Azure, including scopes](https://www.youtube.com/watch?v=4v7ffXxOnwU)



[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)