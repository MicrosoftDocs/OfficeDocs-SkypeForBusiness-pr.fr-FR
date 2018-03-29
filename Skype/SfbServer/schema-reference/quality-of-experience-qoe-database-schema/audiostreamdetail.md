---
title: Vue de AudioStreamDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La vue AudioStreamDetail stocke des informations sur chaque flux de données audio dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 4dadc53f0641e2d59dc72b2add433c69fc9b8ad1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="audiostreamdetail-view"></a>Vue de AudioStreamDetail
 
La vue AudioStreamDetail stocke des informations sur chaque flux de données audio dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique d’une ligne de media.  <br/> |
|Heure de début  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|Heure de fin  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de la boîte de dialogue : 0 est la Skype pour Business Server à la branche de serveur de médiation ; 1 est le serveur de médiation pour jambe de passerelle RTPC.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indicateur signalant si l’appel a été ignoré ou non.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Si elle est présente, indique pourquoi un appel a été ignoré pas même si la mise en correspondance des ID du contournement. Une seule valeur est définie :  <br/> 0 x 0001 - ID de contournement inconnu pour l’adaptateur de réseau par défaut.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet de pool d’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Pool appelé nom de domaine complet.  <br/> |
|Appelant  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|Appelé  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelant. Consultez le [tableau de UserAgent](useragent.md) pour plus de détails. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Consultez le [tableau de UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur l’appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelé. Consultez la [table de l’agent utilisateur](useragent.md) pour plus d’informations. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Consultez le [tableau de UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelé.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelant.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelé.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nom du processeur de point de terminaison de l’appelant.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nom du processeur de point de terminaison de l’appelé.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs de processeur dans le point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs de processeur dans le point de terminaison de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur du processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur du processeur du point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant est en cours d’exécution dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CorrelationKey  <br/> ||Clé de corrélation. Référencé à partir de la [table de SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informations sur le chemin d’accès de média, tel que direct ou relayés. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport : UDP est de 0, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau de l’intervalle : 1 signifie appelant est à l’intérieur du réseau d’entreprise, 0 signifie l’appelant est à l’extérieur du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé est à l’intérieur du réseau de l’intervalle : 1 signifie appelé est à l’intérieur du réseau d’entreprise, 0 signifie l’appelé est en dehors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nom du pays/de la région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’A / V Edge service utilisé par l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clé de l’adresse IP de l’A / V Edge service utilisé par l’appelé. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 est câblé, 1 est sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel : 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelant en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 est câblé, 1 est sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel : 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelé en bits/s.  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |MOS de conversation à bande étroite des sessions audio (basées sur les deux flux de données audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle appliquée dans le flux du côté envoi donné étant donné les différents paramètres de stratégie (TURN, API, SDP, stratégie de serveur, etc.). Ne doit ne pas être confondue avec la bande passante effective, car il peut y avoir une faible bande passante efficace basée sur l’estimation de la bande passante. Il s’agit essentiellement de la bande passante maximale que le flux de données d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilité du réseau moyenne à partir des statistiques de protocole de contrôle en temps réel (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Bougé maximal du réseau lors de l’appel.  <br/> |
|PacketLossRate  <br/> |Decimal(5,4)  <br/> |Taux de perte de paquet moyenne lors de l’appel.  <br/> |
|PacketLossRateMax  <br/> |Decimal(5,4)  <br/> |Perte de paquet maximale observée au cours de l’appel.  <br/> |
|BurstDensity  <br/> |Decimal(9,4)  <br/> |Densité moyenne de perte de paquets pendant les pics de pertes lors de l’appel.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durée moyenne de perte de paquets pendant les pics de pertes lors de l’appel.  <br/> |
|BurstGapDensity  <br/> |Decimal(9,4)  <br/> |Densité moyenne de perte de paquets au cours des intervalles entre les pics de perte de paquets.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durée moyenne des écarts entre les pics de perte de paquets.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux de données audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|DegradationAvg  <br/> |Decimal (3,2)  <br/> |Dégradation de MOS de réseau pour l’appel entière. La plage est de 0.0 à 5.0. Cette métrique indique le montant de que la MOS de réseau a été réduite en raison de la perte de gigue et de paquet. Pour une qualité acceptable elle doit être inférieure à 0,5.  <br/> |
|DegradationMax  <br/> |Decimal (3,2)  <br/> |Dégradation du réseau MOS maximale lors de l’appel.  <br/> |
|DegradationJitterAvg  <br/> |Decimal (3,2)  <br/> |Dégradation du réseau MOS due au gigue.  <br/> |
|DegradationPacketLossAvg  <br/> |Decimal (3,2)  <br/> |Réseau MOS engendrés par la perte de paquets.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Le codec audio utilisé pour l’appel, référencé à partir de la [table de PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taux d’échantillonnage du flux audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Niveau de signal audio analogique après contrôle de Gain pour les données audio envoyées par l’appelant. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Niveau de signal audio de l’audio, l’appelant a reçu. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio analogique après contrôle de Gain pour les données audio envoyées par l’appelant. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio analogique après contrôle de Gain pour l’audio reçus par l’appelant. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Echo renvoie perte amélioration pour l’appelant. L’unité de cette mesure est dB. Les valeurs faibles représentent moins écho. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Problèmes de moyennes par cinq minutes pour le rendu de haut-parleur de l’appelant. De bonne qualité, il doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Capturent les anomalies moyennes par cinq minutes pour microphone de l’appelant. Pour une bonne qualité, ce doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|CallerTimestampDriftRateMic  <br/> |Decimal(9,2)  <br/> |Microphone périphérique dérive fréquence d’horloge l’appelant, par rapport à l’horloge du processeur.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |Decimal(9,2)  <br/> |Du haut-parleur périphérique dérive fréquence d’horloge l’appelant, par rapport à l’horloge du processeur.  <br/> |
|CallerTimestampErrorMicMs  <br/> |Decimal(9,2)  <br/> |Microphone moyenne capture flux tampon erreur d’exécution, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |Decimal(9,2)  <br/> |Erreur de cachet de temps flux, en millisecondes, de rendu de moyenne du haut-parleur de l’appelant dans les 20 dernières secondes de l’appel.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Commutateur de voix est un mode half duplex avec possibilité de réduction des interruptions. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement d’écho pour l’appelant. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerEchoPercentMicIn  <br/> |Decimal(5,2)  <br/> |Pourcentage du temps lorsque l’écho est détecté dans le flux de capture de microphone de l’appelant. Si un casque est utilisé, la valeur doit être faible.  <br/> |
|CallerEchoPercentSend  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans l’appelant envoie flux. Pourcentage élevé d’écho dans envoi de flux une indication de la fuite de l’écho.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation de la passerelle pour l’audio de l’appelant ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. De bonne qualité, la plage acceptable doit être de 30 à-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Piste audio du niveau de signal reçu sur le serveur de médiation de la passerelle pour l’appelant. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour la qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Automatique de gain (AGC) de contrôle sur le côté serveur de médiation appliqué à des données audio de l’appelant.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Moyenne quadratique (RMS) du signal entrant à l’appelant pour jusqu'à 30 premières secondes de l’appel.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Représente le niveau de signal audio analogique après le contrôle de Gain pour les données audio envoyée par l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Niveau de signal audio de l’audio, l’appelé reçu. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio analogique après contrôle de Gain pour les données audio envoyées par l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio analogique après contrôle de Gain pour l’audio reçus par l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Echo renvoyer amélioration de perte de l’appelé. L’unité de cette mesure est dB. Les valeurs faibles représentent moins écho. Cette mesure n’est pas signalée par le A / V Conferencing Server ou IP téléphones.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Problèmes de moyennes par cinq minutes pour le rendu de haut-parleur de l’appelé. De bonne qualité, il doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Capturent les anomalies moyennes par cinq minutes pour microphone de l’appelé. Pour une bonne qualité, ce doit être inférieure à 1 par cinq minutes. Non signalé par A / V Conferencing serveurs, serveurs de médiation ou IP téléphones.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |Decimal(9,2)  <br/> |Microphone périphérique dérive fréquence d’horloge l’appelé, par rapport à l’horloge du processeur.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |Decimal(9,2)  <br/> |Haut-parleur périphérique dérive fréquence d’horloge l’appelé, par rapport à l’horloge du processeur.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |Decimal(9,2)  <br/> |Microphone moyenne capture flux tampon erreur d’exécution, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |Decimal(9,2)  <br/> |Erreur de cachet de temps flux, en millisecondes, de rendu de moyenne du haut-parleur de l’appelé dans les 20 dernières secondes de l’appel.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Commutateur de voix est un mode half duplex avec possibilité de réduction des interruptions. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement de l’écho de l’appelé. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CalleeEchoPercentMicIn  <br/> |Decimal(5,2)  <br/> |Pourcentage du temps lorsque l’écho est détecté dans le flux de capture de microphone de l’appelé. Si un casque est utilisé, la valeur doit être faible.  <br/> |
|CalleeEchoPercentSend  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans l’appelé d’envoyé le flux. Pourcentage élevé d’écho dans envoi de flux une indication de la fuite de l’écho.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation de la passerelle pour l’audio de l’appelé ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour la qualité, la plage acceptable doit être [30 à -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Piste audio du niveau de signal reçu sur le serveur de médiation de la passerelle de l’appelé. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour la qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Automatique de gain (AGC) de contrôle sur le côté serveur de médiation appliqué à des données audio de l’appelé.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Moyenne quadratique (RMS) du signal entrant à l’appelé pour jusqu'à 30 premières secondes de l’appel.  <br/> |
|RatioConcealedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons permettant des dissimuler générées par le correcteur audio à des exemples typiques.  <br/> |
|RatioStretchedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons étirés générées par le correcteur audio à des exemples typiques.  <br/> |
|RatioCompressedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons compressés générées par le correcteur audio à des exemples typiques.  <br/> |
|Aller-retour  <br/> |int  <br/> |Délai d’aller-retour à partir des statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Temps d’aller-retour maximale pour le flux de données audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |Decimal (3,2)  <br/> |Moyenne à large bande MOS de réseau pour l’appel. Cette mesure dépend de la perte de paquets, l’instabilité et codec utilisé. La plage est 1.0 à 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |Decimal (3,2)  <br/> |Large bande minimale MOS de réseau pour l’appel.  <br/> |
|SendListenMOS  <br/> |Decimal (3,2)  <br/> |Moyenne prévisible à large bande à l’écoute de MOS score audio envoyés, y compris le niveau de reconnaissance vocale, niveau de bruit et capturer des caractéristiques du périphérique.  <br/> |
|SendListenMOSMin  <br/> |Decimal (3,2)  <br/> |SendListenMOS minimale pour l’appel.  <br/> |
|RecvListenMOS  <br/> |Decimal (3,2)  <br/> |Score moyen de large bande prévue MOS d’écoute audio reçus à partir du réseau, y compris le niveau de reconnaissance vocale, niveau de bruit, codec, des conditions réseau et caractéristiques des périphériques de capture.  <br/> |
|RecvListenMOSMin  <br/> |Decimal (3,2)  <br/> |RecvListenMOS minimale pour l’appel.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indique si l’audio FEC a été utilisé pour l’appel.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indique la direction de la p-affirmée identifient les informations ; 1 signifie que la direction du flux de données est celui de l’appelant à l’appelé ; 0 signifie que la direction du flux de données est de l’appelé vers l’appelant.  <br/> |
   

