---
title: Table Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La table serveur est une table de prise en charge. Chaque enregistrement représente un serveur.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294711"
---
# <a name="server-table"></a>Table Server
 
La table serveur est une table de prise en charge. Chaque enregistrement représente un serveur. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant le serveur.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Chaîne d’adresses MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Externes  <br/> |1: serveur de médiation  <br/> 2: service de conférence a/V Server16394: service32769 Edge A/V: passerelle  <br/> |
|**PoolName** <br/> |nvarchar  <br/> ||Regroupement auquel appartient le serveur. Applicable uniquement au serveur de conférence A/V.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||Pour un usage interne uniquement.  <br/> |
   

