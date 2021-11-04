---
title: Table MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 3cc8c11f049e98223c80756eb2dc83f1b9354ec7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768362"
---
# <a name="monitoredusersitelink-table"></a>Table MonitoredUserSiteLink
 
La table MonitoredUserSiteLink est une table de prise en charge. Chaque enregistrement représente un lien entre deux sites d’utilisateurs.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référencé à partir [de la table UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Primaire, étrangère  <br/> |Référence à partir de [la table UserSite](usersite.md).  <br/> |
   

