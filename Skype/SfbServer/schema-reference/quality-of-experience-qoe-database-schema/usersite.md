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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294571"
---
# <a name="usersite-table"></a>Table UserSite
 
La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateur défini dans les paramètres de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le site de l’utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |Différent  <br/> |Nom du site de l’utilisateur.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externes  <br/> |Référencé à partir de la [table région](region.md).  <br/> |
   

