---
title: tblAdminLock
ms.prod: SKYPEFORBUSINESS
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
---


# tblAdminLock
[]
tblAdminLock contains the administrator lock that is needed to run some administrator commands.
  
    
    


**Columns**


|**Column**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, not null  <br/> |Lock expiration date and time. The owner can extend this value periodically.  <br/> |
|lockServerID  <br/> |int, not null  <br/> |ID of the server that owns the lock.  <br/> |
|lockActorID  <br/> |int, not null  <br/> |ID of the principal that owns the lock.  <br/> |
   

