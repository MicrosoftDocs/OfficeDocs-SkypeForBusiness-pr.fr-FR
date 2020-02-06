---
title: Table Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805202"
---
# <a name="subnet-table"></a>Table Subnet
 
La table de sous-réseau est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans les paramètres de configuration du réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Etranger principal  <br/> |Représentation entière de l’adresse IP du sous-réseau.  <br/> |
|**Masque_sous_réseau** <br/> |int  <br/> ||Masque de sous-réseau.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Externes  <br/> |Fait référence à partir de la [table UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar  <br/> ||Description du sous-réseau.  <br/> |
   

