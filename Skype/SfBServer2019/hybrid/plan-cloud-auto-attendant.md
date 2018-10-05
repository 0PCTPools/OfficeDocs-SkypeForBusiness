---
title: "Plan a Cloud Auto Attendant"
ms.author: jambirk
author: jambirk
manager: serdars 
ms.date: 7/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: 
description: "Overview of using a Cloud Auto Attendant with Skype for Business Server 2019."
---

# Plan Cloud Auto Attendant

[!INCLUDE [disclaimer](../disclaimer.md)]
Skype for Business Server 2019 hybrid implementations only use Cloud Voicemail Cloud Auto Attendants and do not integrate with Exchange Online.

## Overview

The Auto Attendant used with Exchange Unified Messaging (Exchange Server 2013 or Exchange Server 2016) is no longer available in Exchange Server 2019 or Exchange Online. If your implementation of Skype for Business Server 2019 integrates with either of these Exchange versions, you'll need to use the online Cloud Voice features associated with Phone System. This inherently means that you will have a hybrid implementation of Skype for Business Server 2019. See [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md) for details.

An Auto Attendant can include a greeting the caller can't interact with (this can be a different message during office hours and outside office hours) and menu choices the users can interact with either with a voice response or by pressing a telephone keypad. The options can connect callers to employees, an Operator, call queues used by entire departments, and other auto attendants that act as sub-menus to a main Auto Attendant. Each Auto Attendant is a distinct virtual user on your Skype for Business Server 2019 system. See [What are Phone System auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) for more detail on what Auto Attendants are and what options and features exist for Auto Attendants.

Also see:

- [Set up a Phone System auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md)
- [Automatically answer and route incoming calls](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls) 

## Requirements

The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.  Your requirements depend on your scenario:

- If you are already using Exchange UM online or on premises and you upgrade to Skype for Business 2019, you will need to capture the structure of your Auto attendants and re-create them in the cloud using Phone system Auto Attendants. For more information, see [Manually moving an Exchange UM Auto Attendant to Cloud Auto Attendant](configure-cloud-auto-attendant.md#manually-moving-an-exchange-um-auto-attendant-to-cloud-auto-attendant).

- For a new configuration of Cloud Auto Attendants, follow the steps outlined in [Configure Cloud Auto Attendants](configure-cloud-auto-attendant.md).

In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud Auto Attendant service:

- Hybrid connectivity. If you already have Skype for Business Server deployed, and you want to enable Cloud Auto Attendant for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments. This is sometimes called a split domain configuration. 

   For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).

- Your online implementation will need to have a plan that includes Phone System licenses described at [Office 365 Enterprise E1, E3, and E4](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e1-e3-e4) or [Office 365 Enterprise E5](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing).

- If you have an on-premises only deployment (that is, only Exchange Server 2019 and Skype for Business Server 2019 on-premises servers) but you want to take advantage of Cloud Auto Attendant, you need the ON-PREM license.

- Create on premise endpoints for each Auto Attendant, including assigning phone numbers and licenses. Note that you now have the ability to assign licenses used by online services like Phone System to on-premise phone numbers.
- Implement a new Cloud Auto Attendant service with Skype for Business Online and Phone System. See [Configure cloud auto attendant](configure-cloud-auto-attendant.md) for implementation details.


## Migration and interoperability

If you are planning to deploy Skype for Business Server 2019 and/or Exchange Server 2019, you must plan your migration carefully to ensure continued support for Auto Attendants. Keep the following in mind:

- Exchange Server 2019 no longer provides Exchange UM functionality
- Skype for Business Server 2019 no longer integrates with Exchange Online UM

Version interoperability and supported topologies for Cloud Auto Attendants are listed in the following table. For the preview release, Cloud Auto Attendants only work with Skype for Business Server 2019 and Exchange Server 2019 or Exchange Online.


| | Exchange Server 2013 | Exchange Server 2016 | Exchange Server 2019 | Exchange Online |
|:---    |:---|:---|:---|:--- |
| Skype for Business Server 2019 | Exchange Server UM | Exchange Server UM | Cloud Auto Attendant | Cloud Auto Attendant
Skype for Business Server 2015 | Exchange Server UM | Exchange Server UM |  | Cloud Auto Attendant <br> Exchange Online UM* |
Lync Server 2013  | Exchange Server UM | Exchange Server UM | | Cloud Auto Attendant <br> Exchange Online UM* |

\* Until deprecated.

Microsoft recommends the following migration paths:

- If you are upgrading to Skype for Business Server 2019, you can use Exchange UM in Exchange Server 2013 or 2016, but you must upgrade to Cloud Auto Attendant if you are using Exchange Server 2019.

- If you are upgrading to Exchange Server 2019, and you are using previous versions of Exchange Server UM for Skype for Business Server voice messaging, Microsoft recommends that you upgrade to Skype for Business Server 2019 before the mailbox upgrade.  Otherwise, voice messaging capabilities will be lost. 


For more information about planning your migration, see [Plan for Skype for Business Server and Exchange Server migration](plan-um-migration.md).


### Migrating a previously implemented Exchange UM Auto Attendant system

Currently we don't support automated migration to the Cloud of a UM auto attendant system created in Exchange 2013 or 2016. To manually re-create an Auto Attendant system, you'll need to:

1. Use Exchange admin powershell commands to review the structure of the old Auto Attendant system, including any nested Auto Attendants and call queues.  
2. Create copies of text-to-speech scripts or recorded messages associated with each UM Auto Attendant node.
3. Create on premise endpoints for each Auto Attendant node, including assigning phone numbers and licenses to the objects. Note that you now have the ability to assign on-premise phone numbers licenses used by online services like Phone System.
4. Implement a new Cloud Auto Attendant service with Skype for Business Online and Phone System. See [Configure cloud auto attendant](configure-cloud-auto-attendant.md) for implementation details. As you do this, upload the text-to-speech scripts or recorded messages associated with each UM Auto Attendant node.

See [Manually moving an Exchange UM Auto Attendant to Cloud Auto Attendant](configure-cloud-auto-attendant.md#manually-moving-an-exchange-um-auto-attendant-to-cloud-auto-attendant) for details on these steps.

## Additional planning resources

The tutorial titled [Small business example - Set up an Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) goes through the process of gathering information about user needs, planning a structure of Auto Attendants and users (and possibly Call Queues, which are not yet supported for hybrid implementations), writing the menu prompts, and implementing the plan in the Online Admin center. review the tutorial and use the exercises there to create your plan.

When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to [Configure Cloud Auto Attendant](configure-cloud-auto-attendant.md).

## See Also

[Configure Cloud Auto Attendant](configure-cloud-auto-attendant.md)

[Enable custom prompt recording using the telephone user interface](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[What are Phone System auto attendants?](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)

[Set up a Phone System auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant.md)

Exchange UM: [Automatically answer and route incoming calls](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md)

[Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).