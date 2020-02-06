---
title: Table TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient les informations de routage des appels. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805112"
---
# <a name="traceroute-table"></a>Table TraceRoute
 
La table TraceRoute contient les informations de routage des appels. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Date et heure de début de l’appel.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Etranger principal  <br/> |Identificateur unique permettant de faire la distinction entre plusieurs appels qui pouvaient avoir commencé à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Etranger principal  <br/> |Représente le type de ligne vidéo utilisée lors de l’appel. Les valeurs autorisées sont les suivantes :  <br/> 0-audio  <br/> 1-vidéo  <br/> 2-vidéo panoramique  <br/> 3-partage de bureau et d’application  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |Point de terminaison ayant placé l’appel.  <br/> |
|**Relais** <br/> |int  <br/> ||Tronçon réseau/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Externes  <br/> |Identificateur unique de l’adresse IP. Les informations d’adresse IP sont stockées dans la [table IPAddress](ipaddress.md).  <br/> |
|**TEMPS** <br/> |int  <br/> ||Durée de l’aller-retour. Le temps d’aller-retour mesure la durée pendant laquelle un paquet vocal atteint sa destination et renvoie la notification de réception.  <br/> |
   

