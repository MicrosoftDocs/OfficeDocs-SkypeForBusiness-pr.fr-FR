---
title: Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de résumé de conférence joindre le temps. Le rapport Résumé de conférence jointure temps résume le délai requis pour les utilisateurs avec succès à participer à une conférence ; Ces valeurs d’heure sont signalés à la fois sous la forme d’une moyenne et dans une des catégories suivantes :'
ms.openlocfilehash: 3646337c9e9f20ac0b1dabfdd5504ce83dfa5c40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015
 
La table ConferenceJoinTimeThresholds contient les limites de classification utilisés par le rapport de résumé de conférence joindre le temps. Le rapport Résumé de conférence jointure temps résume le délai requis pour les utilisateurs avec succès à participer à une conférence ; Ces valeurs d’heure sont signalés à la fois sous la forme d’une moyenne et dans une des catégories suivantes :
  
- Moins de 2 secondes.
    
- Entre 2 secondes et 5 secondes.
    
- Entre 5 et 10 secondes.
    
- Plus de 10 secondes.
    
La table ConferenceJoinTimeThresholds contient les valeurs de classement à 2 secondes, 5 secondes et 10 secondes.
  
Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Principal  <br/> |Identificateur unique pour la classification.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite supérieure pour la classification. Les valeurs autorisées sont les suivantes : <br/>  2 <br/>  5 <br/>  10 <br/> |
   

