---
title: Table UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805002"
---
# <a name="usersite-table"></a>Table UserSite
 
La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le site de l’utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |Différent  <br/> |Nom du site de l’utilisateur.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externes  <br/> |Référencé à partir de la [table région](region.md).  <br/> |
   

