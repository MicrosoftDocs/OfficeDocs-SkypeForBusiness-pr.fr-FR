---
title: Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de synthèse de conférence participer à temps. Le rapport de synthèse du temps de participer à une conférence résume le volume de temps requis pour les utilisateurs à prendre part à une conférence ; Ces valeurs sont signalés comme une moyenne et d’une des catégories suivantes :'
ms.openlocfilehash: 75df75e16d2a4ed34f667c94f2b2f0960f56e7ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901435"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
 
La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de synthèse de conférence participer à temps. Le rapport de synthèse du temps de participer à une conférence résume le volume de temps requis pour les utilisateurs à prendre part à une conférence ; Ces valeurs sont signalés comme une moyenne et d’une des catégories suivantes :
  
- Moins de 2 secondes.
    
- Entre 2 et 5 secondes.
    
- Entre 5 et 10 secondes.
    
- Plus de 10 secondes.
    
La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Principal  <br/> |Identificateur unique pour la classification.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite supérieure de la classification. Les valeurs autorisées sont les suivantes : <br/>  2 <br/>  5 <br/>  10 <br/> |
   

