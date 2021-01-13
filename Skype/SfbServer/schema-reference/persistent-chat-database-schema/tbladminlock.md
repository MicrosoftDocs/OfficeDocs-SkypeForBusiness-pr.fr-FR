---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809884"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
  
**Columns**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, not null  <br/> |Date et heure d’expiration du verrou. Le propriétaire peut étendre cette valeur de manière périodique.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID du serveur qui détient le verrou.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID du principal qui détient le verrou.  <br/> |
   

