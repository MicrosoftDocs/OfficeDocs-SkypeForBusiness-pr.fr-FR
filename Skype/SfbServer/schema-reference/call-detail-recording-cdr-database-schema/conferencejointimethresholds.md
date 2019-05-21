---
title: Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence. Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:'
ms.openlocfilehash: 4b2f27b6ab826ff95c1478cf54e8a21c148b1d3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296496"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015
 
La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence. Le rapport Résumé de l’heure de la Conférence résume le temps nécessaire pour que les utilisateurs puissent rejoindre une conférence; ces valeurs d’heure sont communiquées tant en moyenne qu’à l’une des catégories suivantes:
  
- Moins de 2 secondes.
    
- Entre 2 secondes et 5 secondes.
    
- Entre 5 et 10 secondes.
    
- Plus de 10 secondes.
    
La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.
  
Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de la classification.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite supérieure de la classification. Les valeurs autorisées sont les suivantes : <br/>  2 <br/>  5 <br/>  0,10 <br/> |
   

