---
title: Table Server
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table Server est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: e43e245e62b1b40f318d1920ae93d82ae9e8bad0e28436f31d9cc2f0fe54bac1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341619"
---
# <a name="server-table"></a>Table Server
 
La table Server est une table de prise en charge. Chaque enregistrement représente un serveur. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le serveur.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |Chaîne d’adresse MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Étranger  <br/> |1 : serveur de médiation  <br/> 2 : Serveur de conférence A/V16394 : service Edge A/V32769 : passerelle  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool à qui appartient le serveur. Applicable uniquement pour le serveur de conférence A/V.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

