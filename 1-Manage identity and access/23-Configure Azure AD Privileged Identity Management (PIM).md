# Configure Azure AD Privileged Identity Management (PIM)

[Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-getting-started)

* Privileged Identity Management (PIM) provides time-based and approval-based role activated access to resources
* It is possible to get notified when privileged roles are activated
* PIM can force a user to:
   * Use multi-factor authentication
   * Request approval for activation
   * Provide a business reason for activation
* PIM can be used to provide just-in-time access to all Azure AD roles and Azure roles, but not the following classic subscription admin roles: 
   * Account Administrator
   * Service Administrator
   * Co-administrator

[Configure PIM](https://docs.microsoft.com/en-us/azure/active-directory/privileged-identity-management/pim-deployment-plan)

* PIM also enables you to define scope for role assignments using [Administrative Units](14-Manage%20administrative%20units.md) and custom roles
* There are different steps for preparing PIM for Azure AD roles and for Azure roles

See also PIM in the SC-900 study guide

## Pricing
PIM is one of only six services that requires the highest [Active Directory subscription license](https://azure.microsoft.com/en-us/pricing/details/active-directory/): Azure AD Premium P2


[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)