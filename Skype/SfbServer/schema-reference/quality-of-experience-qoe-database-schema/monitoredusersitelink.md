---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateur.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874258"
---
# <a name="monitoredusersitelink-table"></a>Table MonitoredUserSiteLink
 
La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé depuis la [UserSite table](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référence de la [UserSite table](usersite.md).  <br/> |
   

