---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
ms.openlocfilehash: a5a8802f3821fff3d08c2365d4f76655b5824606
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610571"
---
# <a name="monitoredusersitelink-table"></a>Table MonitoredUserSiteLink
 
La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir [de la table UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référence à partir de [la table UserSite](usersite.md).  <br/> |
   

