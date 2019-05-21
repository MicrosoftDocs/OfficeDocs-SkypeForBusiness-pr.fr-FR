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
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient les informations de routage des appels. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294627"
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
   

