---
title: Vue VideoStreamDetail
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vue VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 1fc778060163047b80ad7c523e2ca93414a23e25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756055"
---
# <a name="videostreamdetail-view"></a>Vue VideoStreamDetail
 
La vue VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Description**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique dans une ligne de média.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs d’UC du point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs d’UC du point de terminaison de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur processeur du point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant est en cours d’exécution dans un environnement virtualisé. Pour plus [d’informations, voir la table Endpoint.](endpoint.md) <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé est en cours d’exécution dans un environnement virtualisé. Pour plus [d’informations, voir la table Endpoint.](endpoint.md) <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informations sur le chemin d’accès du média, telles que direct ou relayé. Pour plus [d’informations, voir le tableau MediaLine.](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|Transport  <br/> |int  <br/> |Type de transport : 0 correspond à UDP, 1 correspond à TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation.1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé est en dehors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nom du pays/de la région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelé. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port sur le service Edge A/V utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom de l’appareil de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 est câblé, 1 est sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté sur un réseau privé virtuel ou non. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Vitesse de la liaison réseau pour le système d’extrémité de l’appelant, en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 est câblé, 1 est sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé s’est connecté ou non sur un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |décimal(18,0)  <br/> |Vitesse de liaison réseau pour le point de terminaison de l’appelé (en bps).  <br/> |
|ConversationalMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réellement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne d’après les statistiques RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taux moyen de perte de paquets pendant l’appel.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux vidéo (protocole de transport en temps réel, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Résolution de la vidéo en pixels de largeur multipliée par la hauteur des pixels. Signalé sous la mesure d’une chaîne.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Vitesse de bit moyenne du flux vidéo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |décimal(9,4)  <br/> |Fréquence d’images de la vidéo reçue.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |décimal(9,4)  <br/> |Fréquence d’images de la vidéo envoyée.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Vitesse de bits vidéo maximale pendant la session vidéo.  <br/> |
|VideoPacketLossRate  <br/> |décimal(9,4)  <br/> |Taux auquel les paquets vidéo ont été perdus.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Pourcentage du nombre total d’images vidéo perdues.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Non utilisé.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantité moyenne de bande passante allouée à la vidéo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Pourcentage du nombre total d’images vidéo perdues.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direction du flux pour les informations d’identité p-asserted. 1 signifie que le sens du flux va de l’appelant à l’appelé ; 0 signifie que le sens du flux va de l’appelé à l’appelant.  <br/> |
   

