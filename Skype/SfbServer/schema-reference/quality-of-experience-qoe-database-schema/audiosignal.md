---
title: Table AudioSignal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Chaque enregistrement représente des mesures de signal audio pour un point de terminaison. En règle générale, chaque appel possède deux enregistrements, un pour l’appelant et un pour l’appelé.
ms.openlocfilehash: 1e4f7bf92448d4f2efefe3bfad4e1ca556ad44b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761782"
---
# <a name="audiosignal-table"></a>Table AudioSignal
 
Chaque enregistrement représente des mesures de signal audio pour un point de terminaison. En règle générale, chaque appel possède deux enregistrements, un pour l’appelant et un pour l’appelé. 
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primaire  <br/> |0 : données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Représente le niveau de signal audio du contrôle de gain post-analogique. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Voir SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Représente le niveau de bruit audio du contrôle de gain post-analogique. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Voir SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Mesure Amélioration de la perte de retour d’écho. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|**AudioSpetchGlitchRate** <br/> |int  <br/> | <br/> |Nombre moyen de problèmes par période de cinq minutes pour le rendu des haut-parleurs. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Nombre moyen de problèmes par période de 5 minutes pour la capture du microphone. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Vitesse de dérive de l’horloge du microphone par rapport à l’horloge du processeur.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Vitesse de dérive de l’horloge du haut-parleur par rapport à l’horloge processeur.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Vitesse de dérive de l’horloge du haut-parleur par rapport à l’horloge processeur.  <br/> Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Erreur moyenne d’horodat du flux de rendu du haut-parleur, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée. Causes de l’entrée du commutateur vocal :  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La cause peut être une combinaison de ces causes individuelles. ENTER_VS_FORCEORCONVERGENCE ne peut être activée que par la clé de regkey à des fins de test.  <br/> Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causes d’un événement d’écho :  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La cause peut être une combinaison de ces causes individuelles.  <br/> |
|**EchoPercentMicIn** <br/> |décimal(5,2)  <br/> | <br/> |Pourcentage du temps où un écho a été détecté dans le flux de capture du microphone. En règle générale, les valeurs sont faibles pour les casques ou combinés, et plus élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui supportent l’annulation de l’écho sonore à l’aide de l’appareil, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.  <br/> |
|**EchoPercentSend** <br/> |décimal(5,2)  <br/> ||Pourcentage de temps où un écho est détecté dans le flux envoyé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; Cela s’applique uniquement au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Contrôle de gain automatique (AGC) côté serveur de médiation.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Le carré de la moyenne racine (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Niveau de signal reçu sur le canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Niveau de signal reçu sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Niveau de bruit reçu sur le canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Niveau de bruit reçu sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Niveau de signal tel qu’envoyé sur le canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Niveau de signal tel qu’envoyé sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Niveau de bruit tel qu’envoyé sur le canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Niveau de bruit tel qu’envoyé sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Niveau dans dBFS du signal envoyé au haut-parleur pour la lecture. Prend en compte les ajustements de gain effectués sur le signal reçu. <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Niveau dans dBFS du contenu parasite dans le signal envoyé au haut-parleur pour la lecture <br/> |

