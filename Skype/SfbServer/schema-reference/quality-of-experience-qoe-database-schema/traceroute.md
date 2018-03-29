---
title: Table de détermination d’itinéraire
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient des informations de routage des appels. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>Table de détermination d’itinéraire
 
La table TraceRoute contient des informations de routage des appels. Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Date et heure de début de l’appel.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Identificateur unique utilisé pour faire la distinction entre plusieurs appels peuvent avoir commencé à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaires et étrangères  <br/> |Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :  <br/> 0 - audio  <br/> 1 - vidéo  <br/> 2 - vidéo panoramique  <br/> 3 - application/RDS  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |Point de terminaison ayant passé l’appel.  <br/> |
|**Saut** <br/> |int  <br/> ||Tronçon réseau /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Étrangère  <br/> |Identificateur unique de l’adresse IP. Informations d’adresse IP sont stockées dans la [table d’adresse IP](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Délai d’aller-retour. Le délai d’aller-retour mesure la quantité de temps que nécessaire à un paquet voix atteindre sa destination et puis envoyer une notification de rappel qu’il a été reçu.  <br/> |
   

