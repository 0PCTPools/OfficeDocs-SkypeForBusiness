---
title: "Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013"
ms.author: kenwith
author: kenwith
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: "Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record."
---

# Configuring voice policies, PSTN usage records, and voice routes in Lync Server 2013
[]
Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.
  
The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record. 
  
> [!NOTE]
> You can also create voice policies with  *user*  scope and assign them to individual users or groups. 
  
For the detailed steps to perform each of these tasks, see the procedures in this section.
  
## In this section

- [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features.md)
    
- [View PSTN usage records in Lync Server 2013](view-pstn-usage-records.md)
    
- [Configuring voice routes for outbound calls in Lync Server 2013](configuring-voice-routes-for-outbound-calls.md)
    
- [Exporting and importing voice routing configuration in Lync Server 2013](exporting-and-importing-voice-routing-configuration.md)
    
- [Publish pending changes to the voice routing configuration in Lync Server 2013](publish-pending-changes-to-the-voice-routing-configuration.md)
    
- [Test voice routing in Lync Server 2013](test-voice-routing.md)
    

