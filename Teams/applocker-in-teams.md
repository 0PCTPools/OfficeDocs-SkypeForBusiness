---
title: AppLocker application control policies in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection: 
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Learn how to enable the Teams desktop client application with Applocker application control policies.
appliesto: 
- Microsoft Teams
---

# AppLocker application control policies in Microsoft Teams

This article explains how to enable the Teams desktop client app with AppLocker application control policies. Use of AppLocker is designed to restrict program and script execution by non-administrative users (for more information and guidance on Applocker, see [What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker). The process for enabling Teams with Applocker requires the creation of AppLocker-based whitelisting policies. Policies are created with Group Policy management software and/or tje use of Windows PowerShell cmdlets for Applocker (see the [Applocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) for more information). The Applocker policy is saved in XML format and can be edited with any text or XML editor.

## Teams whitelisting with AppLocker

AppLocker rules are organized into collections of rules. AppLocker rules apply to the targeted app, and they are the components that make up the AppLocker policy.  

To whitelist Teams, we recommend that you use the publisher condition rules since all Teams app files are digitally code-signed.
  
We do not recommend the use of the file path and/or hash because the rule would have to be updated with every Teams client app update.

Since Teams desktop client files are digitally code-signed, the publisher condition identifies an app based on its digital signature and extended attributes. The digital signature contains information about the company that created the app (the publisher). The extended attributes, which are obtained from the binary resource, contain the name of the product that the file is part of and the version number of the application. The Teams app product name is set to `Microsoft Teams` or `Microsoft Teams Update`.

### Examples of publisher condition rules

For the Teams client app (all files, all versions):

`Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS`

For the Teams client update (all files, all versions):

`Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS UPDATE`

## Related topics
[What is AppLocker?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
[Applocker technical reference](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)