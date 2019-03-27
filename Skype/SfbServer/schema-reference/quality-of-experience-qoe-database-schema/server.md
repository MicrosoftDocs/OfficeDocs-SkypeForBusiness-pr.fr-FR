---
title: Table Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table des serveurs est une table de prise en charge. Chaque enregistrement représente un seul serveur.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874307"
---
# <a name="server-table"></a>Table Server
 
La table des serveurs est une table de prise en charge. Chaque enregistrement représente un seul serveur. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le serveur.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Chaîne d’adresse MAC.  <br/> |
|**Type de serveur** <br/> |int  <br/> |Étrangère  <br/> |1 : serveur de médiation  <br/> 2 : A / V Conferencing Server16394 : A Edge a / V v32769 : passerelle  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Pool que le serveur appartient. Applicable uniquement aux A / V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

