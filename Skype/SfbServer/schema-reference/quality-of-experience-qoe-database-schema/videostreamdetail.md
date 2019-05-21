---
title: Affichage VideoStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: Le mode VideoStreamDetail stocke les informations relatives à chaque flux vidéo dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: ee342de919ffca8b62c60f8c7b724f3dc7be0205
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294529"
---
# <a name="videostreamdetail-view"></a>Affichage VideoStreamDetail
 
Le mode VideoStreamDetail stocke les informations relatives à chaque flux vidéo dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Description**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |IDENTIFIant unique dans une ligne de médias.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorité de l’appel.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool d’appelant.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool d’appel.  <br/> |
|Appelant  <br/> |nvarchar (450)  <br/> |URI de l’appelant.  <br/> |
|Appelé  <br/> |nvarchar (450)  <br/> |URI de l’appelant.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CallerUserAgentType  <br/> |type  <br/> |Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgentDef](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Chaîne de l’agent utilisateur de l’appelant.  <br/> |
|CalleeUserAgentType  <br/> |type  <br/> |Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la [table UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, reportez-vous à la [table UserAgentDef](useragentdef-qoe.md) . <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nom du point de terminaison de l’appelant.  <br/> |
|Appelant  <br/> |nvarchar(128  <br/> |Système d’exploitation (se) du point de terminaison de l’appelant.  <br/> |
|CalleeOS  <br/> |nvarchar(128  <br/> |Système d’exploitation (se) du point de terminaison de l’appelé.  <br/> |
|CallerCPUName  <br/> |nvarchar(128  <br/> |Nom de l’UC du point de terminaison de l’appelant.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128  <br/> |Nom de l’UC du point de terminaison de l’appelant.  <br/> |
|CallerCPUNumberOfCores  <br/> |type  <br/> |Nombre de cœurs d’UC du point de terminaison de l’appelant.  <br/> |
|CalleeCPUNumberOfCores  <br/> |type  <br/> |Nombre de cœurs d’UC du point de terminaison de l’appelant.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur de l’UC du point de terminaison de l’appelant.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Vitesse de processeur de l’UC du point de terminaison de l’appelant.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Pour plus d’informations, voir la [table de points de terminaison](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indique si le système de l’appelant s’exécute dans un environnement virtualisé. Pour plus d’informations, voir la [table de points de terminaison](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Des informations sur le chemin multimédia, par exemple direct ou relayé. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|Transport  <br/> |int  <br/> |Le type de transport: 0 correspond au protocole UDP; 1 est le protocole TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant se trouve au sein du réseau de l’organisation. 1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appel se trouve hors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nom du site du ou des appelants.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Clé d’adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de capture du destinataire.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de l’appareil de capture du appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant: 0 est filaire, 1 est un réseau sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CallerLinkSpeed  <br/> |décimale (18)  <br/> |Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau du ou du destinataire: 0 est filaire, 1 est un téléphone sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |décimale (18, 0)  <br/> |Vitesse de liaison réseau pour le point de terminaison de l’appelant (en BPS).  <br/> |
|ConversationalMOS  <br/> |décimale (3, 2)  <br/> |La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Scintillement du réseau maximum lors de l’appel.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée de l’aller-retour des statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée de l’aller-retour maximal pour le flux audio.  <br/> |
|PacketLossRate  <br/> |décimale (5; 4)  <br/> |Taux moyen de perte de paquets lors de l’appel.  <br/> |
|PacketLossRateMax  <br/> |décimale (5; 4)  <br/> |Perte de paquets maximum observée pendant l’appel.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux vidéo (Real Time Transport Protocol, RTP).  <br/> |
|Bande passante  <br/> |int  <br/> |Estimations de bande passante pour le flux audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |car (9)  <br/> |Résolution de la vidéo, en pixels, de largeur multipliée par la hauteur en pixels. Signalée en tant que chaîne.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Vitesse de transmission moyenne du flux vidéo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |décimale (9; 4)  <br/> |Fréquence d’images de la vidéo reçue.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |décimale (9; 4)  <br/> |Fréquence d’images de la vidéo envoyée.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Débit vidéo maximum lors de la session vidéo.  <br/> |
|Cause du taux  <br/> |décimale (9; 4)  <br/> |Taux d’interruption des paquets vidéo.  <br/> |
|VideoFrameLossRate  <br/> |décimale (9.4)  <br/> |Pourcentage du nombre total de trames vidéo perdues.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Non utilisé.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantité moyenne de bande passante allouée pour la vidéo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |décimale (9.4)  <br/> |Pourcentage du nombre total de trames vidéo perdues.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direction du flux pour les informations d’identité affirmées p. 1 signifie que le sens du flux provient de l’appelant vers l’appelant; 0: le sens du flux provient de l’appelant.  <br/> |
   

