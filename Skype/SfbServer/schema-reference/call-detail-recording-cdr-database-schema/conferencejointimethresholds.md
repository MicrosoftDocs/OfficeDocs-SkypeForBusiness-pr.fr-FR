---
title: Table ConferenceJoinTimeThresholds dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: 'La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :'
ms.openlocfilehash: dfa7293307376b5fb5c86cec6f7504d363b005f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813304"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>Table ConferenceJoinTimeThresholds dans Skype Entreprise Server 2015
 
La table ConferenceJoinTimeThresholds contient les limites de classification utilisées par le rapport de synthèse du temps de connexion à la conférence. Ce rapport récapitule le temps nécessaire aux utilisateurs pour se joindre à une conférence. Ces valeurs de temps représentent à la fois une moyenne et l’une des catégories suivantes :
  
- Moins de 2 secondes.
    
- Entre 2 et 5 secondes.
    
- Entre 5 et 10 secondes.
    
- Plus de 10 secondes.
    
La table ConferenceJoinTimeThresholds contient les valeurs de classification 2 secondes, 5 secondes et 10 secondes.
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique de la classification.  <br/> |
|**ThresholdValue** <br/> |int  <br/> || Limite supérieure de la classification. Les valeurs autorisées sont les suivantes : <br/>  2  <br/>  5  <br/>  10  <br/> |
   

