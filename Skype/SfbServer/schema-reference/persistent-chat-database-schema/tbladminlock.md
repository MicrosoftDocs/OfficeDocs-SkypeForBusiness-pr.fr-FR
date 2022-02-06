---
title: tblAdminLock
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
---

# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, not null  <br/> |Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID du serveur qui détient le verrou.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID du principal qui détient le verrou.  <br/> |
   

