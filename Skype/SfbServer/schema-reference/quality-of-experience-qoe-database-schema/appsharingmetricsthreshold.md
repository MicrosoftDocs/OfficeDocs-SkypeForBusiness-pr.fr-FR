---
title: Table de AppSharingMetricsThreshold
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
description: La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité utilisés avec le partage de l’application. Ces seuils sont utilisés pour déterminer si l’application partage d’expérience doit être classée comme médiocres.
ms.openlocfilehash: 1ccf60fc9668d2ad2943929affad6fd4a078c789
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingmetricsthreshold-table"></a>Table de AppSharingMetricsThreshold
 
La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour les métriques de qualité utilisés avec le partage de l’application. Ces seuils sont utilisés pour déterminer si l’application partage d’expérience doit être classée comme médiocres.
  
Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CallType** <br/> |int  <br/> |Principal  <br/> |Type d’appel qui a été placé.  <br/> |
|**AppliedBandwidthLimitOptimal** <br/> |int  <br/> ||Limitation de la bande passante optimale pour le partage d’application. La valeur par défaut est de 1000000.  <br/> |
|**AppliedBandwidthLimitAcceptable** <br/> |int  <br/> ||Limitation de la bande passante acceptable pour le partage d’application. La valeur par défaut est de 500000.  <br/> |
|**SpoiledTilePercentTotalOptimal** <br/> |Decimal(5,2)  <br/> ||Taux optimal pour les mosaïques « endommagés » pour la classification d’une qualité de partage d’Application. Cette valeur est le pourcentage du contenu dans le fichier partagé qui n’ont pas reçu de l’Observateur. Contenu peut-être être ignorée (ou avariée) lorsque le fichier partagé ignore des carreaux à partir de la source des graphiques ou l’ASMCU mosaïques ignore les mosaïques à partir du fichier emprunteur respectivement. La valeur par défaut est de 11 %.  <br/> |
|**SpoiledTilePercentTotalAcceptable** <br/> |Decimal(5,2)  <br/> ||Taux de pourcentage acceptable de « endommagés » des mosaïques pour la classification d’une qualité de partage d’Application. Cette valeur est le pourcentage du contenu dans le fichier partagé qui n’ont pas reçu de l’Observateur. Contenu peut-être être ignorée (ou avariée) lorsque le fichier partagé ignore des carreaux à partir de la source des graphiques ou l’ASMCU mosaïques ignore les mosaïques à partir du fichier emprunteur respectivement. La valeur par défaut est de 36 pour cent.  <br/> |
|**JitterInterArrivalOptimal** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**JitterInterArrivalAcceptable** <br/> |int  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityOptimal** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyBurstDensityAcceptable** <br/> |float  <br/> ||Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageOptimal** <br/> |float  <br/> ||Valeur optimale du délai relatif à sens unique entre les extrémités de deux supports impliquées dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 seconde.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverageAcceptable** <br/> |float  <br/> ||Valeur optimale du délai relatif à sens unique entre les extrémités de deux supports impliquées dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 secondes.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageOptimal** <br/> |float  <br/> ||Valeur optimale de la mosaïque moyenne de RDP traitement latence dans le serveur de conférence en tant que sur la durée de la session de visualisation. La latence est la différence de temps entre lors du démarrage de la trame est codée sur le serveur (partagés ou MCU en fonction du scénario) et le même cadre de démarrer est décodé dans la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RDPTileProcessingLatencyAverageAcceptable** <br/> |float  <br/> ||Valeur acceptable de la mosaïque moyenne de RDP traitement latence dans le serveur de conférence en tant que sur la durée de la session de visualisation. La latence est la différence de temps entre lors du démarrage de la trame est codée sur le serveur (partagés ou MCU en fonction du scénario) et le même cadre de démarrer est décodé dans la visionneuse.  <br/> Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.  <br/> La colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

