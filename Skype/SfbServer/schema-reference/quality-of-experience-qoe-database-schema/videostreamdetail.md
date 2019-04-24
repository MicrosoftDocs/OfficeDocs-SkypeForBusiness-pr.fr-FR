---
title: Vue videostreamdetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vue Videostreamdetail stocke des informations sur chaque flux vidéo dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6bafdbed3152bc73b2988e31877d8b7203557d46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211996"
---
# <a name="videostreamdetail-view"></a>Vue videostreamdetail
 
La vue Videostreamdetail stocke des informations sur chaque flux vidéo dans la base de données. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Description**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique au sein d’une ligne de média.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs de processeur de point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de cœurs d’UC du système d’extrémité de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur de point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse du processeur de point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informations sur le chemin d’accès des médias, tels que direct ou relayés. Consultez la [table MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Plus d’informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|Transport  <br/> |int  <br/> |Type de transport : 0 est UDP, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau d’entreprise. 1 signifie que l’appelant est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur de l’organisation réseau.1 signifie appelé situé à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve en dehors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nom de pays/région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nom de pays/région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du A / V Edge service utilisé par l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port sur A / V Edge service utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clé de l’adresse IP a / V Edge service utilisé par l’appelé. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port sur A / V Edge service utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 pour câblée, 1 pour sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal(18,)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelant en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 pour câblée, 1 pour sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé connecté via un réseau privé virtuel. 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en bits/s).  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |Note MOS qualité de la conversation à bande étroite des sessions audio (basées sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle à appliquer au flux côté envoi donné donné différents paramètres de stratégie (activer, API, SDP, stratégie de serveur, etc.). Il ne doit ne pas être confondu avec la bande passante effective, car il peut y avoir une bande passante réduite efficace en fonction de l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale que le flux d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne à partir des statistiques de contrôle protocole RTCP (Real Time).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Gigue réseau maximum pendant l’appel.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée d’aller-retour d’après les statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée d’aller-retour maximale pour le flux audio.  <br/> |
|PacketLossRate  <br/> |Decimal(5,4)  <br/> |Taux de perte de paquets moyenne pendant l’appel.  <br/> |
|PacketLossRateMax  <br/> |Decimal(5,4)  <br/> |Perte maximale de paquets observée pendant l’appel.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |Résolution de la vidéo en pixels de large multiplié par pixels de haut. Indiqué sous forme de chaîne.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |Decimal(9,4)  <br/> |Fréquence d’images vidéo reçue.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |Decimal(9,4)  <br/> |Fréquence d’images vidéo envoyée.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Vitesse de transmission vidéo maximale au cours de la session vidéo.  <br/> |
|VideoPacketLossRate  <br/> |Decimal(9,4)  <br/> |Fréquence à laquelle les paquets vidéo ont été perdues.  <br/> |
|VideoFrameLossRate  <br/> |Decimal(9.4)  <br/> |Pourcentage du total des images vidéo perdues.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Non utilisé.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantité moyenne de bande passante allouée à la vidéo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |Decimal(9.4)  <br/> |Pourcentage du total des images vidéo qui ont été perdues.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direction du flux d’informations p-asserted-identity. 1 signifie que la direction du flux va de l’appelant à l’appelé ; 0 signifie que la direction du flux va de l’appelé à l’appelant.  <br/> |
   

