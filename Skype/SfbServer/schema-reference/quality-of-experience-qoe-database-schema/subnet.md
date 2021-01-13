---
title: Table Subnet
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
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
ms.openlocfilehash: b4683c654d5d188d2f5096dd7ec9da124001f68b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831334"
---
# <a name="subnet-table"></a>Table Subnet
 
La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaire, étrangère  <br/> |Représentation sous forme d’entier de l’adresse IP de sous-réseau.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Masque de sous-réseau.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Étranger  <br/> |Référencé à partir de [la table UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Description du sous-réseau.  <br/> |
   

