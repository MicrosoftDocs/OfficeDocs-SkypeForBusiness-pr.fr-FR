---
title: Table TraceRoute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient les informations de routage émanant des appels. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 2f29d5c46d963cb456386e846d765032be8d5cae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411497"
---
# <a name="traceroute-table"></a>Table TraceRoute
 
La table TraceRoute contient les informations de routage émanant des appels. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Date et heure de début de l’appel.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Identificateur unique utilisé pour faire la distinction entre plusieurs appels qui peuvent avoir commencé à la même date et à la même heure.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> |Représente le type de ligne vidéo utilisé dans l’appel. Les valeurs autorisées sont les suivantes :  <br/> 0 - Audio  <br/> 1 - Vidéo  <br/> 2 - Vidéo panoramique  <br/> 3 - Partage d’application/bureau  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primaire  <br/> |Système d’extrémité qui a passé l’appel.  <br/> |
|**Saut** <br/> |int  <br/> ||Tronçon de réseau.  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Étranger  <br/> |Identificateur unique de l’adresse IP. Les informations d’adresse IP sont stockées dans la [table IPAddress](ipaddress.md).  <br/> |
|**RTT** <br/> |int  <br/> ||Durée de boucle. La durée de boucle mesure le temps nécessaire pour qu’un paquet vocal atteigne sa destination, puis renvoie une notification indiquant qu’il a été reçu.  <br/> |
   

