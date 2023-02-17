# Active Directory
## Introduction
Active Directory (AD) is a directory service for Windows network environments. It is a distributed, hierarchical structure that allows for centralized management of an organization's resources, including users, computers, groups, network devices, file shares, group policies, devices, and trusts.
AD has come under increasing attack in recent years cuz many features are arguably not "secure by default," and it can be easily misconfigured. This weakness can be leveraged to move laterally and vertically within a network and gain unauthorized access.

A basic AD user account with no added privileges can enumerate most objects within AD. This fact makes it extremely important to properly secure an AD implementation because ANY user account, regardless of their privilege level, can be used to enumerate the domain and hunt for misconfigurations and flaws thoroughly.
Also, multiple attacks can be performed with only a standard domain user account, showing the importance of a defense-in-depth strategy and careful planning focusing on security and hardening AD, network segmentation, and least privilege.

Active Directory Domaine Service, stores informations such as usernames and passwords and manage the right needed for autorized users to access this informations. 
It's difficult to manage properlly especially in large envirenement where it can be easially misconfigured
AD flaws can often be used to obtain a foothold (an internal access) to mive laterally and vertically within a network and access objects such as :
* ***Domain Computers***
* ***Domain users***
* ***Default Group infos***
* ***Default Domain Policy***
* ***Pawwsord Policy***
* ***Domain Trust***
* ***Organizational Units***
* ***Group Policy Objects***
* ***Access Control Lists***

## AD Structure
We must understand how AD is set up and the basics of administration before attempting to attack it

***AD*** is arranged in a hierarchical tree structure, with a forest at the top containing one or more domains, which can themselves have nested subdomains.

A forest is the security boundary within which all objects are under administrative control. A forest may contain multiple domains, and a domain may include further child or sub-domains. A domain is a structure within which contained objects (users, computers, and groups) are accessible.

A forst has many built-in Organizational Units (OUs), such as Domain Controllers, Users, Computers, and new OUs can be created as required. OUs may contain objects and sub-OUs, allowing for the assignment of different group policies.

#### Don't worry i got u, u'll understand all those terms in ur way

An AD ***STRUCTURE*** may look as follow

![net](https://etutorials.org/shared/images/tutorials/tutorial_63/f05tk11.jpg)

Here we could say that MICROSOFT.COM is the root domain and contains the subdomains (either child or tree root domains) UK.MICROSOFT.COM and US.MICROSOFT.COML as well as the other objects that make up a domain such as users, groups, computers, and more. 

It is common to see multiple domains (or forests) linked together via trust relationships in organizations that perform a lot of acquisitions. It is often quicker and easier to create a trust relationship with another domain/forest than recreate all new users in the current domain.
The two-way arrow represents a bidirectional trust between the two forests, meaning that users in INLANEFREIGHT.LOCAL can access resources in FREIGHTLOGISTICS.LOCAL and vice versa.
We can also see multiple child domains under each root domain. In this example, we can see that the root domain trusts each of the child domains, but the child domains in forest A do not necessarily have trusts established with the child domains in forest B.

## AD Terminology
d
