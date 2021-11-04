---
title: Table UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.
ms.openlocfilehash: d8e7ccea49d00355a3e114833518cf5e6f762674
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737480"
---
# <a name="usersite-table"></a>Table UserSite
 
La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de ce site utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Uniques  <br/> |Nom du site utilisateur.  <br/> |
|**RegionKey** <br/> |int  <br/> |Étranger  <br/> |Référencé à partir [de la table Region](region.md).  <br/> |
   

