---
title: Affichage MediaLine
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
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 2a8f5ad413bb127e20d82927d804379b5e981636
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771870"
---
# <a name="medialine-view"></a>Affichage MediaLine
 
La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**détails**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé à partir de [la table MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelant. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit en indicateurs binaires pour l’appelé. Pour plus d’informations, voir Quality of Experience Monitoring Server Protocol Specification.  <br/> |
|Sécurité  <br/> |tinyint  <br/> |Le profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport. 0 est UDP, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant se trouve ou non à l’intérieur du réseau de l’organisation. 1 signifie que l’appelant est à l’intérieur du réseau de l’entreprise. 0 indique que l’appelant se trouve à l’extérieur du réseau.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC ou interface réseau utilisé par l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant signalée par le service Edge A/V. Cette adresse peut être différente de CallerIPAddr si le client se trouve derrière un dispositif NAT par exemple.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |Description du pilote Wifi de l’appelant.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Version du pilote Wifi de l’appelant.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de la connexion réseau de l’appelant. Pour plus [d’informations, voir la table NetworkConnectionDetail.](networkconnectiondetail.md) <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Identificateur BSSID (Basic Service Set Identifier) utilisé par la connexion WiFi de l’appelant.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel, 0 pour un réseau non VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé se trouve ou non à l’intérieur du réseau de l’entreprise. 1 signifie que l’appelé est à l’intérieur du réseau de l’entreprise, 0 indique que l’appelé se trouve à l’extérieur du réseau.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC ou interface réseau utilisé par l’appelé.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelé. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelé.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé signalée par le service Edge A/V. Cette adresse peut être différente de CallerIPAddr  si le client se trouve derrière un dispositif NAT par exemple.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nom de l’appareil de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Description du pilote Wifi de l’appelé.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |Version du pilote Wifi de l’appelé.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de la connexion réseau de l’appelé. Pour plus [d’informations, voir la table NetworkConnectionDetail.](networkconnectiondetail.md) <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Identificateur d’ensemble de services de base utilisé par la connexion WiFi de l’appelé.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé s’est connecté via un réseau privé virtuel : 1 pour un réseau privé virtuel (VPN), 0 pour un réseau non-VPN.  <br/> |
|ConversationalMOS  <br/> |décimal(3,2)  <br/> |Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante effectivement appliquée au flux côté envoi d’après différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Source de la capacité de bande passante imposée. Il décrit l’emplacement d’où vient la limite de bande passante (par exemple, « Serveur de stratégie », « SERVEUR TURN » ou « Modalité »).  <br/> |
|Appelant  <br/> |bit  <br/> |Indique si des mesures ont été reçues de la part de l’appelant ; 1 pour oui, 0 pour non.  <br/> |
|Appelé  <br/> |bit  <br/> |Indique si des mesures ont été reçues de la part du récepteur de l’appel ; 1 pour oui, 0 pour non.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indique si le rapport s’applique à une partie de l’appel ou à l’intégralité de l’appel.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indique si un appel a été classé comme médiocre (1) ou bon (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indique si l’utilisateur appelé s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> |
   

