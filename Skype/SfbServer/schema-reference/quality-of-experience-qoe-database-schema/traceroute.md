---
title: Table TraceRoute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La table TraceRoute contient des informations de routage des appels. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212073"
---
# <a name="traceroute-table"></a>Table TraceRoute
 
La table TraceRoute contient des informations de routage des appels. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Date et heure de début de l’appel.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Identificateur unique utilisé pour faire la distinction entre plusieurs appels peuvent avoir commencé à la même date et en même temps.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire, étrangère  <br/> |Représente le type de ligne vidéo utilisée dans l’appel. Les valeurs autorisées sont les suivantes :  <br/> 0 - audio  <br/> 1 - vidéo  <br/> 2 - panoramique vidéo  <br/> 3 - application/partage du bureau  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |Point de terminaison qui a passé l’appel.  <br/> |
|**Tronçon** <br/> |int  <br/> ||Tronçon de réseau /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Étrangère  <br/> |Identificateur unique de l’adresse IP. Informations d’adresse IP sont stockées dans la [table IPAddress](ipaddress.md).  <br/> |
|**DURÉE ALLER-RETOUR** <br/> |int  <br/> ||Délai d’aller-retour. Le délai d’aller-retour mesure la quantité de temps que nécessaire à un paquet de voix pour parvenir à sa destination, puis envoyer notification arrière qu’elle a été reçue.  <br/> |
   

