---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399528"
---
# <a name="monitoredusersitelink-table"></a>Table MonitoredUserSiteLink
 
La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir de [la table UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référence à partir de [la table UserSite](usersite.md).  <br/> |
   

