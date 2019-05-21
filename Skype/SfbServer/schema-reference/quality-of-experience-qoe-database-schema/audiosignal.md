---
title: Table AudioSignal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Chaque enregistrement représente les métriques du signal audio pour un point de terminaison. En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelant.
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295075"
---
# <a name="audiosignal-table"></a>Table AudioSignal
 
Chaque enregistrement représente les métriques du signal audio pour un point de terminaison. En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelant. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0: données du destinataire  <br/> 1: données de l’appelant  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Représente le niveau du signal audio après le contrôle du gain. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Voir SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Représente le niveau de bruit sonore du contrôle post-analogue. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Voir SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrique d’amélioration de retour d’écho. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Moyenne des problèmes par cinq minutes pour la capture du micro. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |décimale (9; 2)  <br/> | <br/> |Taux d’horloge de l’horloge du périphérique microphone par rapport à l’horloge de l’UC.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |décimale (9; 2)  <br/> | <br/> |Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |décimale (9; 2)  <br/> | <br/> |Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.  <br/> Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |décimale (9; 2)  <br/> | <br/> |Erreur d’horodatage moyenne du flux de rendu du présentateur, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|**VsEntryCauses** <br/> |type  <br/> | <br/> |Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Causes de l’entrée du commutateur vocal:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La cause peut être une combinaison de ces causes individuelles. ENTER_VS_FORCEORCONVERGENCE peut uniquement être activé par RegKey à des fins de test.  <br/> Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causes d’un événement ECHO:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La cause peut être une combinaison de ces causes individuelles.  <br/> |
|**EchoPercentMicIn** <br/> |décimale (5; 2)  <br/> | <br/> |Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.  <br/> |
|**EchoPercentSend** <br/> |décimale (5; 2)  <br/> ||Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Contrôle automatique de gain sur le côté serveur de médiation.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Le carré moyen racine (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Niveau du signal reçu sur le canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Niveau du signal reçu sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Niveau sonore reçu sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Niveau sonore reçu sur canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Niveau du signal envoyé sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Niveau du signal envoyé sur canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Niveau sonore tel qu’il est envoyé sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Niveau sonore tel qu’il est envoyé sur canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Niveau le plus haut du signal envoyé sur le haut-parleur pour la lecture. Comptes pour les ajustements de gain apportés au signal reçu. <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Niveau de la lecture du contenu du bruit du signal envoyé vers le haut-parleur pour la lecture <br/> |

