---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou de l’administrateur qui est nécessaire pour exécuter certaines commandes de l’administrateur.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrou de l’administrateur qui est nécessaire pour exécuter certaines commandes de l’administrateur.
  
**Colonnes**

|**Colonne**|**Type de**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, non null  <br/> |Verrou d’expiration date et heure. Le propriétaire peut étendre cette valeur périodiquement.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID du serveur qui détient le verrou.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID de l’entité qui détient le verrou.  <br/> |
   

