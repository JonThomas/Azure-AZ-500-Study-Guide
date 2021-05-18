# Configure Access Reviews

* An access review is performed to make sure no one is a member of a group the shouldn't be in
* Access reviews are manual so prefer automatation, for example [dynamic membership](12-Manage%20Azure%20AD%20directory%20groups.md)
* Recurring reviews can be set up, and reviewers will be notified.
* Can monitor Azure roles out of the box. If [PIM](21-Monitor%20privileged%20access%20for%20Azure%20AD%20Privileged%20Identity%20Management%20(PIM).md) is activated, Azure AD roles and RBAC roles can also be monitored.

# Tips

* When setting up a review for a group, assign the reviewers to be owners of that group
* When reviewing guests or a large number of users, they can do the review themselves??


## Pricing

* Access revies is one of only six services that requires the highest [Active Directory subscription license](https://azure.microsoft.com/en-us/pricing/details/active-directory/): Azure AD Premium P2
* Buy a P2 license for each reviewer, self-reviewer, ...

[Return to Manage identity and access](README.md)

[Return to Table of Contents](../README.md)