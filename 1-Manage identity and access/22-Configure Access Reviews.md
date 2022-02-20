# Configure Access Reviews

[Configure Access Reviews](https://docs.microsoft.com/en-us/azure/active-directory/governance/access-reviews-overview)

* An access review is performed to make sure no one is a member of a group they shouldn't be in
* Can also configure self reviews: Users will be asked to review their own access
* Access reviews are manual so prefer automation, for example by using [dynamic group membership](12-Manage%20Azure%20AD%20directory%20groups.md)
* Recurring reviews can be set up, and reviewers will be notified.
* Can monitor Azure roles out of the box. If [PIM](21-Monitor%20privileged%20access%20for%20Azure%20AD%20Privileged%20Identity%20Management%20(PIM).md) is activated, Azure AD roles and RBAC roles can also be monitored.

See also [Access reviews in the SC-900 study guide](https://github.com/JonThomas/Azure-SC-900-Study-Guide/blob/master/2-Microsoft%20Identity%20and%20Access%20Management%20Solutions/42-Describe%20what%20entitlement%20management%20and%20access%20reviews%20is.md#azure-ad-access-reviews)

# Tips

* When setting up a review for a group, assign the reviewers to be owners of that group
* When reviewing guests or a large number of users, they can do the review themselves

## Pricing

* Access revies is one of only six services that requires the highest [Active Directory subscription license](https://azure.microsoft.com/en-us/pricing/details/active-directory/): Azure AD Premium P2
* Buy a P2 license for each reviewer, self-reviewer, ...

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)