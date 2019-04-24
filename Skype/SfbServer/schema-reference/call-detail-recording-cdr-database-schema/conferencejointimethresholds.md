---
title: Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de synthèse de conférence participer à temps. Le rapport de synthèse du temps de participer à une conférence résume le volume de temps requis pour les utilisateurs à prendre part à une conférence ; Ces valeurs sont signalés comme une moyenne et d’une des catégories suivantes :'
ms.openlocfilehash: d6fbae0d077719782b3e93c0fe008ee35ce3370e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213290"
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
   

