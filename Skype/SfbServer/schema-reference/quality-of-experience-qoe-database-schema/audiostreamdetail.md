---
title: Affichage AudioStreamDetail
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: L’affichage AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3485ac8e8f2f38e7440ef723dfa40b3530589fc8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741860"
---
# <a name="audiostreamdetail-view"></a>Affichage AudioStreamDetail
 
L’affichage AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique dans une ligne de média.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de boîte de dialogue : 0 est la Skype Entreprise Server de serveur de médiation ; 1 est la partie serveur de médiation vers passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indicateur signalant si l’appel a été contourné ou non.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Si une valeur est présente, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Une seule valeur est définie :  <br/> 0x0001 - ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool des appelants.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool des appelés.  <br/> |
|Appelant  <br/> |nvarchar(450)  <br/> |URI de l’appelant.  <br/> |
|Appelé  <br/> |nvarchar(450)  <br/> |URI de l’appelé.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Type de l’agent utilisateur de l’appelant. Pour plus [d’informations, voir le tableau UserAgent.](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelé.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Type de l’agent utilisateur de l’appelé. Pour plus [d’informations, voir la table UserAgent.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Catégorie de l’agent utilisateur de l’appelé. Pour plus d’informations, voir la [table UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelé.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelant.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Système d’exploitation (OS) du point de terminaison de l’appelé.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nom du processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nom du processeur du point de terminaison de l’appelé.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs d’UC dans le point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs d’UC dans le point de terminaison de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur processeur du point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant est en cours d’exécution dans un environnement virtualisé. Pour plus [d’informations, voir la table Endpoint.](endpoint.md) <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé est en cours d’exécution dans un environnement virtualisé. Pour plus [d’informations, voir la table Endpoint.](endpoint.md) <br/> |
|CorrelationKey  <br/> ||Clé de corrélation. Référencé à partir [de la table SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informations de connexion sur le chemin d’accès des médias : directe ou mise en attente, par exemple. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport : 0 correspond à UDP, 1 correspond à TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur du réseau interne : 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant se trouve à l’extérieur du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé se trouve à l’intérieur du réseau interne : 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve à l’extérieur du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nom du pays/de la région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelé. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom de l’appareil de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 est câblé, 1 est sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.  <br/> |
|CallerLinkSpeed  <br/> |décimal(18,0)  <br/> |Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 est câblé, 1 est sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le système d’extrémité de l’appelé, en bits/s.  <br/> |
|ConversationalMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taux moyen de perte de paquets pendant l’appel.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|BurstDensity  <br/> |décimal(9,4)  <br/> |Densité moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durée moyenne de perte de paquets pendant les rafales de pertes au cours de l’appel.  <br/> |
|BurstGapDensity  <br/> |décimal(9,4)  <br/> |Densité moyenne de perte de paquets pendant les intervalles entre rafales de pertes de paquets.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durée moyenne des intervalles entre les rafales de pertes de paquets.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|DegradationAvg  <br/> |décimal(3,2)  <br/> |Dégradation de la note MOS qualité réseau pour l’appel entier. La plage va de 0.0 à 5.0. Cette mesure montre la baisse de la note MOS qualité réseau pour cause de gigue et de perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0.5.  <br/> |
|DegradationMax  <br/> |décimal(3,2)  <br/> |Dégradation de la note MOS qualité réseau maximale pendant l’appel.  <br/> |
|DegradationJitterAvg  <br/> |décimal(3,2)  <br/> |Dégradation de la note MOS qualité réseau causée par la gigue.  <br/> |
|DegradationPacketLossAvg  <br/> |décimal(3,2)  <br/> |Dégradation de la note MOS qualité réseau causée par la perte de paquets.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Niveau de signal audio pour les données audio reçues par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé reçu par l’appelant. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Amélioration de la perte du retour d’écho pour l’appelant. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerSpeappelezGlitchRate  <br/> |int  <br/> |Nombre moyen de problèmes sonores par période de cinq minutes pour le rendu des haut-parleurs de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Nombre moyen de problèmes par période de cinq minutes pour la capture du microphone de l’appelant. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Vitesse de dérive de l’horloge du microphone de l’appelant par rapport à l’horloge du processeur.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Vitesse de dérive de l’horloge du haut-parleur de l’appelant par rapport à l’horloge du processeur.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Moyenne de l’erreur d’horodat du flux de rendu du haut-parleur de l’appelant, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement d’écho pour l’appelant. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CallerEchoPercentMicIn  <br/> |décimal(5,2)  <br/> |Pourcentage de temps où un écho est détecté dans le flux de capture du microphone de l’appelant. Si un casque est utilisé, cette valeur doit être faible.  <br/> |
|CallerEchoPercentSend  <br/> |décimal(5,2)  <br/> |Pourcentage de temps où un écho est détecté dans le flux d’envoi de l’appelant. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelant ; Cela s’applique uniquement au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelant. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Contrôle de gain automatique (AGC) côté serveur de médiation appliqué à l’audio de l’appelant.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Valeur quadratique moyenne du signal entant pour l’appelant au cours des 30 premières secondes au maximum de l’appel.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Représente le niveau de signal audio du réglage de puissance post-analogique pour les données audio envoyées par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Niveau de signal audio pour les données audio reçues par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio envoyé par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Niveau de bruit audio du réglage de puissance post-analogique pour le contenu audio reçu par l’appelé. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Amélioration de la perte du retour d’écho pour l’appelé. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeSpeappelezGlitchRate  <br/> |int  <br/> |Nombre moyen de problèmes par période de cinq minutes pour le rendu des haut-parleurs de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Nombre moyen de problèmes par période de cinq minutes pour la capture du microphone de l’appelé. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Vitesse de dérive de l’horloge du microphone de l’appelé, par rapport à l’horloge du processeur.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Vitesse de dérive de l’horloge du haut-parleur de l’appelé, par rapport à l’horloge du processeur.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Moyenne de l’erreur d’horodat du flux de rendu du haut-parleur de l’appelé, en millisecondes, au cours des 20 dernières secondes de l’appel.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement d’écho pour l’appelé. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CalleeEchoPercentMicIn  <br/> |décimal(5,2)  <br/> |Pourcentage de temps où un écho est détecté dans le flux de capture du microphone de l’appelé. Si un casque est utilisé, cette valeur doit être faible.  <br/> |
|CalleeEchoPercentSend  <br/> |décimal(5,2)  <br/> |Pourcentage de temps où un écho est détecté dans le flux d’envoi de l’appelé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelé ; Cela s’applique uniquement au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Niveau de signal reçu sur le serveur de médiation à partir de la passerelle pour l’audio de l’appelé. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Contrôle de gain automatique (AGC) côté serveur de médiation appliqué à l’audio de l’appelé.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Valeur quadratique moyenne du signal entant pour l’appelé au cours des 30 premières secondes au maximum de l’appel.  <br/> |
|RatioConcealedSamplesAvg  <br/> |décimal(5,2)  <br/> |Taux moyen d’échantillons masqués générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|RatioStretchedSamplesAvg  <br/> |décimal(5,2)  <br/> |Taux moyen d’échantillons étirés générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|RatioCompressedSamplesAvg  <br/> |décimal(5,2)  <br/> |Taux moyen d’échantillons compressés générés par la réparation du contenu audio par rapport aux échantillons standard.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité réseau moyenne en large bande pour l’appel. Cette mesure dépend de la perte de paquets, de la gigue et du codec utilisé. La plage est comprise entre 1.0 et 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité réseau minimale en large bande pour l’appel.  <br/> |
|SendListenMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio envoyé, y compris le niveau de voix, le niveau sonore et les caractéristiques du périphérique de capture.  <br/> |
|SendListenMOSMin  <br/> |décimal(3,2)  <br/> |Valeur SendListenMOS minimale pour l’appel.  <br/> |
|RecvListenMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité d’écoute moyenne en large bande prédite pour le contenu audio reçu du réseau, y compris le niveau de voix, le niveau sonore, le codec, les conditions réseau et les caractéristiques du périphérique de capture.  <br/> |
|RecvListenMOSMin  <br/> |décimal(3,2)  <br/> |Valeur RecvListenMOS minimale pour l’appel.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indique si la FEC audio a été utilisée pour l’appel.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indique la direction des informations PAI (P-Asserted-Identity) : 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
   

