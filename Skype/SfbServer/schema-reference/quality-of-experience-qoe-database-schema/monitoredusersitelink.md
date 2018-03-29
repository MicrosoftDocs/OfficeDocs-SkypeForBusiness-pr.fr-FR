---
title: Table MonitoredUserSiteLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est un tableau de prise en charge. Chaque enregistrement représente une liaison entre deux sites d’utilisateur.
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a>Table MonitoredUserSiteLink
 
La table MonitoredUserSiteLink est un tableau de prise en charge. Chaque enregistrement représente une liaison entre deux sites d’utilisateur.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaires et étrangères  <br/> |Référencé à partir de la [table de UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaires et étrangères  <br/> |Référence de la [table de UserSite](usersite.md).  <br/> |
   

