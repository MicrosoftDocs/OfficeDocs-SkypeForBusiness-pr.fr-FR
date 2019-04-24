---
title: Table AudioSignal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Chaque enregistrement représente des mesures de signal audio d’un point de terminaison. En règle générale, chaque appel a deux enregistrements, une est pour l’appelant et une est pour l’appelé.
ms.openlocfilehash: 7a064f13b6f34f61dcfb72169a4b1620cd81b01f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212312"
---
# <a name="audiosignal-table"></a>Table AudioSignal
 
Chaque enregistrement représente des mesures de signal audio d’un point de terminaison. En règle générale, chaque appel a deux enregistrements, une est pour l’appelant et une est pour l’appelé. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Représente le niveau du signal audio analogique consécutives à prendre le contrôle. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consultez SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Représente le niveau de bruit audio analogique consécutives à prendre le contrôle. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieure à 35 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consultez SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Mesure de l’amélioration de perte de renvoyer l’écho. L’unité de cette mesure est la base de données. Les valeurs inférieures représentent moins l’écho. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Problèmes moyens par cinq minutes pour le rendu des haut-parleurs. Pour une bonne qualité, il doit s’agir de moins d’une par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Problèmes moyens par cinq minutes pour la capture du microphone. Pour une bonne qualité ce doit être inférieure à 1 par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |Decimal(9,2)  <br/> | <br/> |Microphone débit horloge, par rapport à l’horloge de l’UC.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur débit horloge, par rapport à l’horloge de l’UC.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur débit horloge, par rapport à l’horloge de l’UC.  <br/> Moyenne de microphone capture flux erreur d’horodatage, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur moyenne rendu flux erreur d’horodatage, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Basculement vocal est un mode semi-duplex avec possibilité de réduction des interruptions. Causes d’entrée de commutateur vocale :  <br/> ENTER_VS_BADTS 0 X 01  <br/> ENTER_VS_ECHO 0 X 02  <br/> ENTER_VS_FORCEORCONVERGENCE 0 X 04  <br/> ENTER_VS_DNLP 0 X 08  <br/> La cause peut être une combinaison de ces causes individuelles. ENTER_VS_FORCEORCONVERGENCE ne peut être activé par une clé de Registre à des fins de test.  <br/> Type de données pour cette colonne a été modifié dans Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causes d’un événement d’écho :  <br/> ECHO_EVENT_BAD_TIMESTAMP 0 X 01  <br/> ECHO_EVENT_POSTAEC_ECHO 0 X 02  <br/> ECHO_EVENT_ANLP 0 X 04  <br/> ECHO_EVENT_DNLP 0 X 08  <br/> ECHO_EVENT_MIC_CLIPPING 0 X 10  <br/> ECHO_EVENT_BAD_STATE 0 X 20  <br/> La cause peut être une combinaison de ces causes individuelles.  <br/> |
|**EchoPercentMicIn** <br/> |Decimal(5,2)  <br/> | <br/> |Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.  <br/> |
|**EchoPercentSend** <br/> |Decimal(5,2)  <br/> ||Pourcentage de temps lorsque l’écho est détecté dans les flux envoyé. Pourcentage d’écho haute dans envoient des flux une indication de fuite d’écho.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Niveau du signal sur le serveur de médiation provenant de la passerelle ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être [30 à -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Niveau du signal reçu sur le serveur de médiation à partir de la passerelle. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Réglage du côté serveur de médiation puissance automatique.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Moyenne quadratique (RMS) de signal de jusqu'à 30 premières secondes de l’appel.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Niveau du signal reçu sur le canal 1.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Niveau du signal reçu sur le canal 2.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Niveau sonore reçu sur le canal 1.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Niveau sonore reçu sur le canal 2.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Niveau du signal envoyé sur le canal 1.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Niveau du signal envoyé sur le canal 2.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Niveau sonore envoyé sur le canal 1.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Niveau sonore envoyé sur le canal 2.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Niveau dans dBFS du signal envoyé vers les haut-parleurs pour la lecture. Comptes pour les ajustements de gain apportées à du signal reçu. <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Niveau dans dBFS du contenu bruit du signal envoyé vers les haut-parleurs pour la lecture <br/> |

