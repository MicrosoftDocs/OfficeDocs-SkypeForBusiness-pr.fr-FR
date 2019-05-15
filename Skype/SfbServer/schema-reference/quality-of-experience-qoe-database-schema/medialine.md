---
title: Vue MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient généralement un média audio et une ligne de média vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 4fcfa22c17cc47c37e33d1f68bdab9815840c332
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920137"
---
# <a name="medialine-view"></a>Vue MediaLine
 
La vue MediaLine stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient généralement un média audio et une ligne de média vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**plus d’informations**|
|:-----|:-----|:-----|
|Paramètre ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé depuis la [MediaLine table](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Plus d’informations sur le processus de mise en place ICE (Interactive Connectivity) décrits dans les bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité de l’expérience Monitoring Server Spécification du protocole.  <br/> |
|Sécurité  <br/> |tinyint  <br/> |Profil de sécurité en cours d’utilisation. 0 correspond à aucun, 1 SRTP, 2 V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport. 0 est UDP, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’adresses IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau d’entreprise. 1 signifie que l’appelant est à l’intérieur du réseau d’entreprise. 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC ou interface réseau utilisé par l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du A / V Edge service utilisé par l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelant.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant tel que signalé par A / V Edge service. Cette adresse peut être différente qui le CallerIPAddr si le client se trouve derrière un NAT, par exemple.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Description du pilote Wifi de l’appelant.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Version du pilote Wifi de l’appelant.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de la connexion réseau de l’appelant. Consultez la [table NetworkConnectionDetail](networkconnectiondetail.md) pour plus d’informations. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Basic Service Set Identifier utilisé par la connexion WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Il peut s’agir d’adresses IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé à l’intérieur du réseau d’entreprise. 1 signifie que l’appelé se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé se trouve en dehors du réseau.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC ou interface réseau utilisé par l’appelé.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP du A / V Edge service utilisé par l’appelé. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelé.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Adresse IP appelé signalés par A / V Edge service. Cette adresse peut être différente qui le CalleeIPAddr si le client se trouve derrière un NAT, par exemple.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom du périphérique de rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom du pilote du périphérique de rendu de l’appelé.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Description du pilote Wifi de l’appelé.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Version du pilote Wifi de l’appelé.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de la connexion réseau de l’appelé. Consultez la [table NetworkConnectionDetail](networkconnectiondetail.md) pour plus d’informations. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Basic Service Set Identifier utilisé par la connexion WiFi de l’appelé.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé connecté via un réseau privé virtuel. 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |Note MOS qualité de la conversation à bande étroite des sessions audio (basées sur les deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Il s’agit de la bande passante effective à appliquer au flux côté envoi donné donné différents paramètres de stratégie (activer, API, SDP, stratégie de serveur, etc.). Il ne doit ne pas être confondu avec la bande passante effective, car il peut y avoir une bande passante réduite efficace en fonction de l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale que le flux d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Source de l’extrémité de la bande passante imposée en cours. Il décrit la limite de bande passante provenance (par exemple, « Stratégie de serveur », « Activer le serveur » ou « Modalité »).  <br/> |
|Appelant  <br/> |bit  <br/> |Indique si les mesures de l’appelant a été reçues ; 1 pour Oui, 0 correspond à aucun.  <br/> |
|Appelé  <br/> |bit  <br/> |Indique si les mesures du récepteur d’appel ont été reçues ; 1 pour Oui, 0 correspond à aucun.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indique si le rapport est une partie de l’appel ou pour l’intégralité de l’appel.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indique si un appel a été classé comme médiocre (1) ou un appel de bonne qualité (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indique si l’appelant est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indique si l’utilisateur appelé s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> |
   

