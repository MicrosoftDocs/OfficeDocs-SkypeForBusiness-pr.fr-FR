---
title: Vue de VideoStreamDetail
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La vue VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: d102a5e99cfcecb7d5e2e35b113e13509662af4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="videostreamdetail-view"></a>Vue de VideoStreamDetail
 
La vue VideoStreamDetail stocke des informations sur chaque flux vidéo dans la base de données. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Description**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID unique d’une ligne de media.  <br/> |
|Heure de début  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|Heure de fin  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de coeurs de processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Nombre de coeurs de processeur du point de terminaison de l’appelé.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur du processeur du point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur du processeur du point de terminaison de l’appelé.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant est en cours d’exécution dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelé s’exécute dans un environnement virtualisé. Voir le [tableau du point de terminaison](endpoint.md) pour plus d’informations. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informations sur le chemin d’accès de média, tel que direct ou relayés. Consultez le [tableau de MediaLine](medialine-0.md) pour plus d’informations. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|Transport  <br/> |int  <br/> |Type de transport : UDP est de 0, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est à l’extérieur du réseau.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur de l’organisation réseau.1 signifie appelé est à l’intérieur du réseau d’entreprise, 0 signifie l’appelé est en dehors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nom du site de l’appelé.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nom du pays/de la région du site de l’appelé.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’A / V Edge service utilisé par l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port sur A / V Edge service utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Clé de l’adresse IP de l’A / V Edge service utilisé par l’appelé. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port sur A / V Edge service utilisé par l’appelé.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelé.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelé.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant : 0 est câblé, 1 est sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CallerLinkSpeed  <br/> |Decimal(18,)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelant en bits/s.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelé : 0 est câblé, 1 est sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé connectés via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |Decimal(18,0)  <br/> |Vitesse de la liaison réseau pour le point de terminaison de l’appelé (en bits/s).  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |MOS de conversation à bande étroite des sessions audio (basées sur les deux flux de données audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle appliquée dans le flux du côté envoi donné étant donné les différents paramètres de stratégie (TURN, API, SDP, stratégie de serveur, etc.). Ne doit ne pas être confondue avec la bande passante effective, car il peut y avoir une faible bande passante efficace basée sur l’estimation de la bande passante. Il s’agit essentiellement de la bande passante maximale que le flux de données d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilité du réseau moyenne à partir des statistiques de protocole de contrôle en temps réel (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Bougé maximal du réseau lors de l’appel.  <br/> |
|Aller-retour  <br/> |int  <br/> |Délai d’aller-retour à partir des statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Temps d’aller-retour maximale pour le flux de données audio.  <br/> |
|PacketLossRate  <br/> |Decimal(5,4)  <br/> |Taux de perte de paquet moyenne lors de l’appel.  <br/> |
|PacketLossRateMax  <br/> |Decimal(5,4)  <br/> |Perte de paquet maximale observée au cours de l’appel.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets de flux vidéo (temps réel Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimations de la bande passante pour le flux audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec utilisé pour l’appel, référencé à partir de la [table de PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |Résolution de la vidéo dans multiplié par la hauteur des pixels pixels de large. Signalé comme une chaîne.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |Decimal(9,4)  <br/> |Fréquence de réception de vidéo.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |Decimal(9,4)  <br/> |Fréquence d’images de la vidéo envoyée.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Vitesse de transmission vidéo maximale lors de la session vidéo.  <br/> |
|VideoPacketLossRate  <br/> |Decimal(9,4)  <br/> |Taux auquel les paquets vidéo ont été perdues.  <br/> |
|VideoFrameLossRate  <br/> |Decimal(9.4)  <br/> |Pourcentage du nombre total de trames vidéo qui sont perdues.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Non utilisé.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Durée moyenne de la bande passante allouée pour la vidéo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |Decimal(9.4)  <br/> |Pourcentage du nombre total de trames vidéo qui ont été perdues.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direction du flux d’informations d’identité d’assertion-p. 1 signifie que la direction du flux de données est celui de l’appelant à l’appelé ; 0 signifie que la direction du flux de données est de l’appelé vers l’appelant.  <br/> |
   

