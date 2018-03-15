---
title: "Administering users in a hybrid Lync Server 2013 deployment"
ms.author: kenwith
author: kenwith
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Ent_O365_Hybrid
ms.assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
description: "You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal. You must sign in by using your tenant administrator account to perform administration tasks."
---

# Administering users in a hybrid Lync Server 2013 deployment
[]
You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal. You must sign in by using your tenant administrator account to perform administration tasks.
  
## Moving Users Back to On-premises

> [!IMPORTANT]
> This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online. If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, [Moving users from Lync Online to Lync on-premises in Lync Server 2013](moving-users-from-lync-online-to-lync-on-premises.md). 
  
- Run the following cmdlets to move a user from Lync Online back to Lync on-premises:
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: 
  
 _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_. You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.
  
### To determine the Hosted Migration Service URL for your Office 365 tenant

1. Login to your Office 365 tenant as an administrator.
    
2. Open the **Lync admin center**.
    
3. With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Replace **webdir** in the URL with **admin**, resulting in the following: 
    
     `https://admin0a.online.lync.com`
    
5. Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

