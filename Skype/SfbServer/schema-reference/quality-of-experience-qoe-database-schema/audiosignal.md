---
title: Table AudioSignal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Chaque enregistrement représente la métrique du signal audio pour un point de terminaison. En règle générale, chaque appel a deux enregistrements, l’une est pour l’appelant, et une est appelé.
ms.openlocfilehash: 25d565538ecdf7cae15ff23f539a2e2eddf8680f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="audiosignal-table"></a>Table AudioSignal
 
Chaque enregistrement représente la métrique du signal audio pour un point de terminaison. En règle générale, chaque appel a deux enregistrements, l’une est pour l’appelant, et une est appelé. 
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principal  <br/> |0 : les données de l’appelé  <br/> 1 : données de l’appelant  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Représente le niveau de signal audio analogique après le contrôle de Gain. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Voir SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Représente le niveau de bruit audio analogique après le contrôle de Gain. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Voir SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Mesure de l’amélioration de perte de retour écho. L’unité de cette mesure est dB. Les valeurs faibles représentent moins écho. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Problèmes de moyennes par cinq minutes pour le rendu du haut-parleur. De bonne qualité, il doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Problèmes de moyennes par cinq minutes pour la capture du microphone. Pour une bonne qualité, ce doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |Decimal(9,2)  <br/> | <br/> |Microphone périphérique dérive fréquence d’horloge, par rapport à l’horloge du processeur.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur périphérique dérive fréquence d’horloge, par rapport à l’horloge du processeur.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur périphérique dérive fréquence d’horloge, par rapport à l’horloge du processeur.  <br/> Microphone moyenne capture flux tampon erreur d’exécution, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |Decimal(9,2)  <br/> | <br/> |Haut-parleur moyen rendu flux tampon erreur, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Commutateur de voix est un mode half duplex avec possibilité de réduction des interruptions. Causes d’entrée du commutateur vocal :  <br/> ENTER_VS_BADTS 0 X 01  <br/> ENTER_VS_ECHO 0 X 02  <br/> ENTER_VS_FORCEORCONVERGENCE 0 X 04  <br/> ENTER_VS_DNLP 0 X 08  <br/> La cause peut être une combinaison de ces causes individuels. ENTER_VS_FORCEORCONVERGENCE ne peut être activée que par la clé de Registre à des fins de test.  <br/> Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causes d’un événement d’écho :  <br/> ECHO_EVENT_BAD_TIMESTAMP 0 X 01  <br/> ECHO_EVENT_POSTAEC_ECHO 0 X 02  <br/> ECHO_EVENT_ANLP 0 X 04  <br/> ECHO_EVENT_DNLP 0 X 08  <br/> ECHO_EVENT_MIC_CLIPPING 0 X 10  <br/> ECHO_EVENT_BAD_STATE 0 X 20  <br/> La cause peut être une combinaison de ces causes individuels.  <br/> |
|**EchoPercentMicIn** <br/> |Decimal(5,2)  <br/> | <br/> |Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.  <br/> |
|**EchoPercentSend** <br/> |Decimal(5,2)  <br/> ||Pourcentage du temps lorsque l’écho est détecté dans le flux de données envoyé. Pourcentage élevé d’écho dans envoi de flux une indication de la fuite de l’écho.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Niveau de signal sur le serveur de médiation provenant de la passerelle ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour la qualité, la plage acceptable doit être [30 à -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Niveau de signal reçu sur le serveur de médiation de la passerelle. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour la qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Automatique de gain (AGC) de contrôle sur le côté serveur de médiation.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |La moyenne quadratique (RMS) du signal entrant de jusqu'à 30 premières secondes de l’appel.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Niveau de signal comme reçu sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Niveau de signal comme reçue sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Niveau de bruit comme reçu sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Niveau de bruit comme reçue sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Niveau du signal envoyé sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Niveau du signal envoyé sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Niveau de bruit comme envoyé sur canal 1.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Niveau de bruit comme envoyé sur le canal 2.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

