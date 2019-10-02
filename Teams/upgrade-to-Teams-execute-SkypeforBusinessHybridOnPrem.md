---
title: Upgrade to Teams from a Skype for Business on-premises deployment - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerations for upgrading to Teams from a Skype for Business on-premises deployment.  
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection: 
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
---

![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")

This article is part of Deployment and Implementation stage of your upgrade journey. Before proceeding, confirm that you’ve completed the following activities:

-   [Enlisted your project stakeholders](upgrade-enlist-stakeholders.md)
-   [Defined your project scope](https://aka.ms/SkypetoTeams-Scope)
-   [Understood coexistence and interoperability of Skype for Business and Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Chosen your upgrade journey](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Prepared your environment](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Prepared your organization](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Conducted a pilot](https://aka.ms/SkypeToTeams-Pilot)

# Upgrade from Skype for Business on-premises to Teams

If you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article. You'll need to set up hybrid connectivity with your Office 365 tenant, and determine coexistence requirements if you are moving your users to Teams in phases. 

> [!IMPORTANT]
> Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported. To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today. Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.

## Step 1: Configure hybrid connectivity 

The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity. 

Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## Step 2: Assign a coexistence and upgrade mode (if you are moving your users to Teams in phases)

If you want to move your users to Teams in phases, then you'll need to ensure that your Teams-only users can communicate with Skype for Business users.  You do this by specifying a coexistence mode.

Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen. For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md)and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).


## Step 3: Move users from Skype for Business on-premises to Teams Only

Ultimately, you'll want to move your users to Teams Only mode. This might involve one or two steps depending on your current on-premises environment.  

For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 



## Phone System and Teams upgrade

If you’re transitioning your Skype for Business deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider--and assuming that you’ve completed the phone number porting--upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.

If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing. For more information, see [Phone System Direct Routing](direct-routing-landing-page.md).
