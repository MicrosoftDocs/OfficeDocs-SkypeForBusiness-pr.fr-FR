---
title: Table UserSite
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La UserSite table est une table de prise en charge. Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885887"
---
# <a name="usersite-table"></a>Table UserSite
 
La UserSite table est une table de prise en charge. Chaque enregistrement représente un site utilisateur défini dans les paramètres de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le site de l’utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Unique  <br/> |Nom d’utilisateur du site.  <br/> |
|**RegionKey** <br/> |int  <br/> |Étrangère  <br/> |Référencé depuis la [Region table](region.md).  <br/> |
   

