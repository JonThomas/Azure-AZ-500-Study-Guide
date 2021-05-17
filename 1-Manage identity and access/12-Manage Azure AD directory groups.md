# Manage Azure AD directory groups

* Allows resource owner to set permissions to all members of the group.
* A group is a security boundary
* Groups can be configured to define membership based on rules (job title; department; ...): "Dynamic group membership". 
* Group owners can manage their own groups, allowing for distributed ownership: Self service group management.
* Security groups can have licenses (for example Office licenses) assigned to them, which gives members access to the applications: "Automatic licensing"

## [Group types](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal#group-and-membership-types)
* Security Group: Manages access to shared resources. A security group can have users, devices, groups and service principals as its members.
* Microsoft 365/ Active Directory Domain Services (ADDS) group: Gives members access to a shared mailbox, calendar, files, SharePoint site, and more

> Azure AD is primarily an Identity solution based on Graph API. There are no Organizational Units (OUs) or Group Policy Objects (GPOs)???
> ADDS (whether on prem or in the cloud) is an LDAP server that provides additional services, for example group policies, authentication, and trust features 
> https://www.apps4rent.com/blog/active-directory-domain-services-vs-azure-active-directory/

[Return to Manage identity and access](README.md)
[Return to Table of Contents](../README.md)