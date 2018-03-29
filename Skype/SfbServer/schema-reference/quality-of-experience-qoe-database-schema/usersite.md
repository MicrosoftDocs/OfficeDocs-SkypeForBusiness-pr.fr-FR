---
title: Table UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est un tableau de prise en charge. Chaque enregistrement représente un site de l’utilisateur défini dans le paramètre de configuration réseau.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>Table UserSite
 
La table UserSite est un tableau de prise en charge. Chaque enregistrement représente un site de l’utilisateur défini dans le paramètre de configuration réseau.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le site de l’utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Unique  <br/> |Nom de site de l’utilisateur.  <br/> |
|**RegionKey** <br/> |int  <br/> |Étrangère  <br/> |Référencé à partir de la [table de la région](region.md).  <br/> |
   

