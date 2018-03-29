---
title: Table Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table du serveur est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>Table Server
 
La table du serveur est une table de prise en charge. Chaque enregistrement représente un serveur. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le serveur.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Chaîne de l’adresse MAC.  <br/> |
|**Type de serveur** <br/> |int  <br/> |Étrangère  <br/> |1 : serveur de médiation  <br/> 2 : A / V Conferencing Server16394 : A / V Edge service32769 : passerelle  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Pool qu'auquel appartient le serveur. Uniquement applicable pour les A / V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

