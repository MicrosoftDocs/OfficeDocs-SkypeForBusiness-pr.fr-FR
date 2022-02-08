---
title: Table AppSharingMetricsThreshold
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
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables des mesures de qualité de l’expérience (QoE) utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’expérience de partage d’application doit être qualifiée de médiocre.
ms.openlocfilehash: 8287f8e141f3d883d50a0fa9783b08b3f4bfbb19
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384152"
---
# <a name="appsharingmetricsthreshold-table"></a>Table AppSharingMetricsThreshold
 
La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables des mesures de qualité de l’expérience (QoE) utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’expérience de partage d’application doit être qualifiée de médiocre.
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Primaire  <br/> |Type d’appel passé.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limite de bande passante optimale pour le partage d’application. La valeur par défaut est 1 000 000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limite de bande passante acceptable pour le partage d’application. La valeur par défaut est 500 000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |décimal(5,2)  <br/> ||Taux de pourcentage optimal pour les vignettes « ingrables » pour la classification d’une qualité de partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 11.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |décimal(5,2)  <br/> ||Taux de pourcentage acceptable pour les vignettes « ingrables » pour la classification d’une qualité de partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 36.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 seconde.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 s.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valeur optimale de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. La latence est la différence de temps entre le moment où l’image de démarrage est codée sur le serveur (partageur ou MCU selon le scénario) et la même image de démarrage est décodée sur la visionneuse.  <br/> Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valeur acceptable de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. La latence est la différence de temps entre le moment où l’image de démarrage est codée sur le serveur (partageur ou MCU selon le scénario) et la même image de démarrage est décodée sur la visionneuse.  <br/> Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

