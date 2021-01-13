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
ms.openlocfilehash: 7f26ed9053c65acb8cfd2e586edbd77fdfa7472b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802704"
---
# <a name="server-table"></a>Table Server
 
La table Server est une table de prise en charge. Chaque enregistrement représente un serveur. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le serveur.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |Index  <br/> |Chaîne d’adresse MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Étranger  <br/> |1 : serveur de médiation  <br/> 2 : Serveur de conférence A/V16394 : service Edge A/V32769 : passerelle  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Pool à qui appartient le serveur. Applicable uniquement pour le serveur de conférence A/V.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

