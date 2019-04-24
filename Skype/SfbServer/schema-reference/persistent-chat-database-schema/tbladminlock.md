---
title: tblAdminLock
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212662"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock contient le verrou d’administrateur nécessaire pour exécuter certaines commandes d’administration.
  
**Colonnes**

|**Colonne**|**Type**|**Description**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, non null  <br/> |Verrouiller la date d’expiration et l’heure. Le propriétaire peut étendre régulièrement cette valeur.  <br/> |
|lockServerID  <br/> |int, non null  <br/> |ID du serveur qui détient le verrou.  <br/> |
|lockActorID  <br/> |int, non null  <br/> |ID du principal qui détient le verrou.  <br/> |
   

