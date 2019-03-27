---
title: Vue audiostreamdetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La vue Audiostreamdetail stocke des informations sur chaque flux audio dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c5078a0d936cce0dec29ddfee3813db7334aba71
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895285"
---
# <a name="audiostreamdetail-view"></a>Vue audiostreamdetail
 
La vue Audiostreamdetail stocke des informations sur chaque flux audio dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique au sein d’une ligne de média.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de dialogue : 0 correspond à la Skype pour Business Server vers le serveur de médiation ; 1 est le serveur de médiation vers branche de passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indicateur signalant si l’appel a été contourné ou non.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |S’il est présent, indique pourquoi un appel a été contourné pas même si le contournement de média ID correspondant. Une seule valeur est définie :  <br/> 0 x 0001 - ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN du pool de l’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN du pool de l’appelé.  <br/> |
|Appelant  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|Appelé  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelant. Voir la [table UserAgent](useragent.md) pour plus d’informations. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Consultez la [table UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne d’agent utilisateur appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type d’agent utilisateur de l’appelé. Voir la [table UserAgent](useragent.md) pour plus d’informations. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Consultez la [table UserAgentDef (QoE)](useragentdef-qoe.md) pour plus d’informations. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelé.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelant.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelé.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nom de l’UC du point de terminaison de l’appelant.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nom de l’UC du système d’extrémité de l’appelé.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs de processeur dans le point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs de processeur dans le point de terminaison de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur de point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur de point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CorrelationKey  <br/> ||Clé de corrélation. Référencé à partir de la [table SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Plus d’informations sur le chemin d’accès de média, tel que direct ou relayés. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Plus d’informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport : 0 est UDP, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau interne : 1 signifie que l’appelant est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé à l’intérieur du réseau interne : 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve en dehors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nom de pays/région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nom de pays/région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du A / V Edge service utilisé par l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clé de l’adresse IP a / V Edge service utilisé par l’appelé. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel : 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelant en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel : 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelé en bits/s.  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |Note MOS qualité de la conversation à bande étroite des sessions audio (basées sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle à appliquer au flux côté envoi donné donné différents paramètres de stratégie (activer, API, SDP, stratégie de serveur, etc.). Il ne doit ne pas être confondu avec la bande passante effective, car il peut y avoir une bande passante réduite efficace en fonction de l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale que le flux d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne à partir des statistiques de contrôle protocole RTCP (Real Time).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|PacketLossRate  <br/> |Decimal(5,4)  <br/> |Taux de perte de paquets moyenne pendant l’appel.  <br/> |
|PacketLossRateMax  <br/> |Decimal(5,4)  <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|BurstDensity  <br/> |Decimal(9,4)  <br/> |Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|BurstGapDensity  <br/> |Decimal(9,4)  <br/> |Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durée moyenne des intervalles entre rafales de pertes de paquets.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|DegradationAvg  <br/> |Decimal (3,2)  <br/> |Dégradation de la note MOS qualité réseau pour l’appel entière. Plage est 0.0 et 5.0. Cette mesure indique la quantité de que la note MOS qualité réseau a été réduite en raison de la perte de gigue et de paquets. Pour une qualité acceptable elle doit être inférieure à 0,5.  <br/> |
|DegradationMax  <br/> |Decimal (3,2)  <br/> |Dégradation de la note MOS qualité réseau maximale pendant l’appel.  <br/> |
|DegradationJitterAvg  <br/> |Decimal (3,2)  <br/> |Dégradation de la note MOS qualité réseau causée par la gigue.  <br/> |
|DegradationPacketLossAvg  <br/> |Decimal (3,2)  <br/> |Dégradation de la note MOS qualité réseau causée par la perte de paquets.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Le codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Analogique postérieures au niveau de signal audio contrôle de Gain pour l’audio envoyé par l’appelant. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Niveau du signal audio pour le son de l’appelant reçu. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Analogique postérieures au niveau de bruit audio contrôle de Gain pour l’audio envoyé par l’appelant. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieure à 35 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio contrôlez postérieures analogique pour le son de l’appelant reçu. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieure à 35 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Écho renvoyer amélioration de perte de l’appelant. L’unité de cette mesure est la base de données. Les valeurs inférieures représentent moins l’écho. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Problèmes moyens par cinq minutes pour le rendu des haut-parleurs de l’appelant. Pour une bonne qualité, il doit s’agir de moins d’une par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Capturent des problèmes moyens par cinq minutes de microphone de l’appelant. Pour une bonne qualité ce doit être inférieure à 1 par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|CallerTimestampDriftRateMic  <br/> |Decimal(9,2)  <br/> |Microphone débit horloge l’appelant, par rapport à l’horloge de l’UC.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |Decimal(9,2)  <br/> |Haut-parleur débit horloge l’appelant, par rapport à l’horloge de l’UC.  <br/> |
|CallerTimestampErrorMicMs  <br/> |Decimal(9,2)  <br/> |Moyenne de microphone capture flux erreur d’horodatage, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |Decimal(9,2)  <br/> |Flux erreur d’horodatage, en millisecondes, de rendu moyenne du haut-parleur de l’appelant dans les 20 dernières secondes de l’appel.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Basculement vocal est un mode semi-duplex avec possibilité de réduction des interruptions. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement d’écho pour l’appelant. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerEchoPercentMicIn  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans le flux de capture du microphone de l’appelant. Si le casque est utilisé, la valeur doit être faible.  <br/> |
|CallerEchoPercentSend  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans l’appelant de l’envoi flux. Pourcentage d’écho haute dans envoient des flux une indication de fuite d’écho.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Niveau du signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelant ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être 30 à dBoV-18.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Niveau du signal reçu sur le serveur de médiation à partir de la passerelle pour l’appelant s audio. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Réglage de puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelant.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Quadratique moyenne (RMS) du signal entant pour l’appelant jusqu'à 30 premières secondes de l’appel.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Représente le niveau du signal audio analogique consécutives à prendre le contrôle pour l’audio envoyé de l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Niveau du signal audio pour le son de l’appelé reçu. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être au moins 30 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Analogique postérieures au niveau de bruit audio contrôle de Gain pour l’audio envoyé par l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieure à 35 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Analogique postérieures au niveau de bruit audio contrôle de Gain pour l’audio reçu par l’appelé. L’unité de cette mesure est dBmo. Pour une qualité acceptable, il doit être inférieure à 35 dBmo. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Écho renvoyer amélioration de la perte de l’appelé. L’unité de cette mesure est la base de données. Les valeurs inférieures représentent moins l’écho. Cette mesure n’est pas signalée par A / V Conferencing Server ou l’adresse IP des téléphones.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Problèmes moyens par cinq minutes pour le rendu des haut-parleurs de l’appelé. Pour une bonne qualité, il doit s’agir de moins d’une par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Capturent des problèmes moyens par cinq minutes de microphone de l’appelé. Pour une bonne qualité ce doit être inférieure à 1 par cinq minutes. Ne pas signalés par A / V Conferencing Servers, les serveurs de médiation ou adresse IP des téléphones.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |Decimal(9,2)  <br/> |Microphone débit horloge l’appelé, par rapport à l’horloge de l’UC.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |Decimal(9,2)  <br/> |Haut-parleur débit horloge l’appelé, par rapport à l’horloge de l’UC.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |Decimal(9,2)  <br/> |Moyenne de microphone capture flux erreur d’horodatage, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |Decimal(9,2)  <br/> |Moyenne de haut-parleur de l’appelé rendu flux erreur d’horodatage, en millisecondes, dans les 20 dernières secondes de l’appel.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Basculement vocal est un mode semi-duplex avec possibilité de réduction des interruptions. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement d’écho de l’appelé. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CalleeEchoPercentMicIn  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans le flux de capture du microphone de l’appelé. Si le casque est utilisé, la valeur doit être faible.  <br/> |
|CalleeEchoPercentSend  <br/> |Decimal(5,2)  <br/> |Pourcentage de temps lorsque l’écho est détecté dans l’appelé envoie flux. Pourcentage d’écho haute dans envoient des flux une indication de fuite d’écho.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Niveau du signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelé ; Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être [30 à -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Niveau du signal reçu sur le serveur de médiation à partir de la passerelle de l’appelé s audio. Cela s’applique uniquement au serveur de médiation. L’unité de cette mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Réglage de puissance automatique côté serveur de médiation appliqué au contenu audio de l’appelé.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Quadratique moyenne (RMS) du signal entant pour l’appelé jusqu'à 30 premières secondes de l’appel.  <br/> |
|RatioConcealedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons masqués générés par soin audio aux échantillons communs.  <br/> |
|RatioStretchedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons étendus générés par soin audio aux échantillons communs.  <br/> |
|RatioCompressedSamplesAvg  <br/> |Decimal(5,2)  <br/> |Taux moyen d’échantillons compressés générés par soin audio aux échantillons communs.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |Decimal (3,2)  <br/> |Moyenne de bande passante réseau MOS pour l’appel. Cette mesure varie selon le codec utilisé, une instabilité et la perte de paquets. Plage est 1.0 et 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |Decimal (3,2)  <br/> |Minimale en bande passante réseau MOS pour l’appel.  <br/> |
|Valeur SendListenMOS  <br/> |Decimal (3,2)  <br/> |Moyenne de bande passante prédite MOS écoute score pour l’audio envoyé, y compris le niveau de voix, niveau sonore et les caractéristiques du périphérique de capture.  <br/> |
|SendListenMOSMin  <br/> |Decimal (3,2)  <br/> |SendListenMOS minimum pour l’appel.  <br/> |
|Valeur RecvListenMOS  <br/> |Decimal (3,2)  <br/> |Bande passante prédite moyenne note MOS qualité d’écoute pour l’audio reçu à partir du réseau, y compris le niveau de voix, niveau sonore, codec, les conditions réseau et caractéristiques du périphérique de capture.  <br/> |
|RecvListenMOSMin  <br/> |Decimal (3,2)  <br/> |RecvListenMOS minimum pour l’appel.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indique si la FEC audio a été utilisé pour l’appel.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indique la direction de la p-asserted identifier les informations ; 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
   

