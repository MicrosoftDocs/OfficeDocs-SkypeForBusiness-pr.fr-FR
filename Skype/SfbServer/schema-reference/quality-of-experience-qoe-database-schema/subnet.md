---
title: Table Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
ms.openlocfilehash: b0c10fae89fe76c184e3aaffec4e1166c4cdb94c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768312"
---
# <a name="subnet-table"></a>Table Subnet
 
La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaire, étrangère  <br/> |Représentation sous forme d’entier de l’adresse IP de sous-réseau.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Masque de sous-réseau.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Étranger  <br/> |Référencé à partir de [la table UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Description du sous-réseau.  <br/> |
   

