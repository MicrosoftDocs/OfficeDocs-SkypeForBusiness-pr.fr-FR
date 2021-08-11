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
ms.openlocfilehash: 10df067fe95f244aea2fa9987b4962efaef9fbe32fbbfbe5b0e9f6ed9f6392e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279960"
---
# <a name="subnet-table"></a>Table Subnet
 
La table Subnet est une table de prise en charge. Chaque enregistrement représente un sous-réseau défini dans un paramètre de configuration réseau.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Primaire, étrangère  <br/> |Représentation sous forme d’entier de l’adresse IP de sous-réseau.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Masque de sous-réseau.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Étranger  <br/> |Référencé à partir [de la table UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Description du sous-réseau.  <br/> |
   

