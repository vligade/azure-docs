---
title: Securing Privileged Access in Azure AD | Microsoft Docs
description: A topic that explains the approaches for securing privileged access across Azure, Azure Active Directory and Microsoft Online Services.
services: active-directory
documentationcenter: ''
author: barclayn
manager: mtillman
editor: mwahl

ms.assetid: 235a0ce9-1daf-4433-8f65-9c6afcd64d08
ms.service: active-directory
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 09/17/2017
ms.author: kgremban
ms.custom: pim

---
# Securing privileged access in Azure AD
Securing privileged access is a critical first step to help protect business assets in a modern organization. Privileged accounts are accounts that administer and manage IT systems. Cyber-attackers target these accounts to gain access to an organization’s data and systems. To secure privileged access, you should isolate the accounts and systems from the risk of being exposed to a malicious user.

More users are starting to get privileged access through cloud services. This can include global administrators of Office365, Azure subscription administrators, and users who have administrative access in VMs or on SaaS apps.

Microsoft recommends you follow this roadmap on [Securing Privileged Access](https://technet.microsoft.com/library/mt631194.aspx).

For customers using Azure Active Directory, Office 365, or other Microsoft services and applications, these principles apply whether user accounts are managed and authenticated by Active Directory or in Azure Active Directory. The following sections provide more information on Azure AD features to support securing privileged access.

## Azure Multi-Factor Authentication
To increase the security of administrator authentication, you should require two-step verification before granting privileges. Two-step verification is a method of verifying who you are that requires the use of more than just a username and password. It provides a second layer of security to user sign-ins and transactions.

Azure Multi-Factor Authentication (MFA) is Microsoft's two-step verification solution, which helps safeguard access to data and applications while meeting user demand for a simple sign-in process. It delivers strong authentication via a range of easy verification options including:

- phone calls
- text messages
- mobile app notifications
- mobile app verification codes
- third-party OATH tokens

For an overview of how Azure Multi-Factor Authentication works see the following video:

> [!VIDEO https://channel9.msdn.com/Blogs/Azure/Windows-Azure-Multi-Factor-Authentication/player]

For more information, see [MFA for Office 365 and MFA for Azure](https://blogs.technet.microsoft.com/ad/2014/02/11/mfa-for-office-365-and-mfa-for-azure/).

## Time-bound privileges
Some organizations may find that they have too many users in highly privileged roles. A user might have been added to the role for a particular activity, like to sign up for a service, but didn't use those privileges frequently afterward.

To lower the exposure time of privileges and increase your visibility into their use, limit users to only taking on their privileges "just in time" (JIT), or assign these roles for a shortened duration with confidence the privileges will be revoked automatically. For Azure Active Directory, Azure Resources (Preview) and Microsoft Online Services, you can use [Azure AD Privileged Identity Management (PIM)](https://aka.ms/AzurePIM).

![PIM dashboard][2]

## Attack detection
[Azure Active Directory Identity Protection](../active-directory-identityprotection.md) provides a consolidated view into risk events and potential vulnerabilities affecting your organization’s identities. Based on risk events, Identity Protection calculates a user risk level for each user, enabling you to configure risk-based policies to automatically protect the identities of your organization. These policies, along with other conditional access controls provided by Azure Active Directory and EMS, can automatically block the user or offer suggestions that include password resets and multi-factor authentication enforcement.

![Azure AD Identity Protection][3]

## Conditional access
With conditional access control, Azure Active Directory checks the specific conditions you choose when authenticating a user, before allowing access to an application. Once those conditions are met, the user is authenticated and allowed access to the application.

## Related articles
* Enable [Azure Multi-Factor Authentication](../authentication/howto-mfa-getstarted.md)
* Enable [Azure AD Privileged Identity Management](../active-directory-privileged-identity-management-configure.md)
* Enable [Azure AD Identity Protection](../active-directory-identityprotection.md)
* Enable [conditional access controls](../active-directory-conditional-access-azure-portal.md)

For more information on building a complete security roadmap, see the “Customer responsibilities and roadmap” section of the [Microsoft Cloud Security for Enterprise Architects](https://aka.ms/securecustomer) document. For more information on engaging Microsoft services to assist with any of these topics, contact your Microsoft representative or visit our [Cybersecurity solutions page](https://www.microsoft.com/en-us/microsoftservices/campaigns/cybersecurity-protection.aspx).

<!--Image references-->
[1]: ../media/active-directory-privileged-identity-management-configure/Search_PIM.png
[2]: ../media/active-directory-privileged-identity-management-configure/PIM_Dash.png
[3]: ../media/active-directory-identityprotection/29.png
