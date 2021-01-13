---
title: Table UserSite
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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799914"
---
# <a name="usersite-table"></a>Table UserSite
 
La table UserSite est une table de prise en charge. Chaque enregistrement représente un site d’utilisateurs défini dans les paramètres de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de ce site utilisateur.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Uniques  <br/> |Nom du site utilisateur.  <br/> |
|**RegionKey** <br/> |int  <br/> |Étranger  <br/> |Référencé à partir [de la table Region](region.md).  <br/> |
   

