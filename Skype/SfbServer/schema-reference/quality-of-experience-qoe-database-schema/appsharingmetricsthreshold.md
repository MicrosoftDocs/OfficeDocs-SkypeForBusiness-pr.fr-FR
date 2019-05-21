---
title: Table AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’utilisation du partage d’application doit être considérée comme médiocre.
ms.openlocfilehash: d3e7bab384c5fffea59e165d5fdf4e6b3d0c09a9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295124"
---
# <a name="appsharingmetricsthreshold-table"></a>Table AppSharingMetricsThreshold
 
La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’utilisation du partage d’application doit être considérée comme médiocre.
  
Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Principal  <br/> |Type d’appel placé.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limite maximale de bande passante pour le partage d’application. La valeur par défaut est 1 million.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitation de bande passante acceptable pour le partage d’application. La valeur par défaut est 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |décimale (5; 2)  <br/> ||Taux de pourcentage optimal pour les vignettes «abîmées» permettant de classer une qualité de partage d’application. Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse. Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement. La valeur par défaut est 11%.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |décimale (5; 2)  <br/> ||Taux de pourcentage acceptable pour les vignettes «abîmées» permettant de classer une qualité de partage d’application. Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse. Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement. La valeur par défaut est 36%.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 secondes.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 secondes.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valeur optimale de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage. La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 millions.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valeur acceptable de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage. La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 millions.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

