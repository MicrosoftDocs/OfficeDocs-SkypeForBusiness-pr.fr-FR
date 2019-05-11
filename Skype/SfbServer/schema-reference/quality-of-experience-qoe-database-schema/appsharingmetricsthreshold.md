---
title: Table AppSharingMetricsThreshold
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’application de partage de l’expérience doit être classée comme médiocre.
ms.openlocfilehash: 32a3a8e4942ad41fc7c1969c14c915bc95aa9e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924891"
---
# <a name="appsharingmetricsthreshold-table"></a>Table AppSharingMetricsThreshold
 
La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’application de partage de l’expérience doit être classée comme médiocre.
  
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Principal  <br/> |Type d’appel a été passé.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitation de bande passante optimale pour le partage d’application. La valeur par défaut est 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitation de bande passante acceptable pour le partage d’application. La valeur par défaut est 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |Decimal(5,2)  <br/> ||Taux optimal pour les mosaïques « altérées » pour classer une qualité de partage d’Application. Cette valeur est le pourcentage du contenu dans le fichier partagé qui n’a pas atteint le spectateur. Le contenu peut être ignoré (ou endommagé) lorsque le fichier partagé ignore les mosaïques à partir de la source graphique ou la ASMCU disposer en mosaïque ignore disposer en mosaïque à partir du fichier partagé respectivement. La valeur par défaut est % 11.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |Decimal(5,2)  <br/> ||Pourcentage acceptable pour les mosaïques « altérées » pour classer une qualité de partage d’Application. Cette valeur est le pourcentage du contenu dans le fichier partagé qui n’a pas atteint le spectateur. Le contenu peut être ignoré (ou endommagé) lorsque le fichier partagé ignore les mosaïques à partir de la source graphique ou la ASMCU disposer en mosaïque ignore disposer en mosaïque à partir du fichier partagé respectivement. La valeur par défaut est de 36 %.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valeur optimale pour le délai relatif à sens unique entre les points de terminaison deux multimédia impliquées dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est secondes 1.0.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valeur optimale pour le délai relatif à sens unique entre les points de terminaison deux multimédia impliquées dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 secondes.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valeur optimale de la mosaïque RDP moyenne de traitement latence dans le serveur de conférence en tant que pendant la durée de la session de visualisation. Latence est la différence entre lorsque l’image de démarrage est codée sur le serveur (partagé ou MCU en fonction du scénario) et la même image de démarrage est décodée dans la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valeur de la mosaïque RDP moyenne de traitement latence dans le serveur de conférence en tant que pendant la durée de la session de visualisation. Latence est la différence entre lorsque l’image de démarrage est codée sur le serveur (partagé ou MCU en fonction du scénario) et la même image de démarrage est décodée dans la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

