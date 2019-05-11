---
title: Table MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Chaque enregistrement représente une ligne de média. (Une seule session audio généralement contient une seule ligne de média audio. Un audio et vidéo (A / V) session généralement contient un média audio et une ligne de média vidéo, bien que la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé.
ms.openlocfilehash: 42c770486c3b2b457e1715dfa5c5a5b028022f26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920144"
---
# <a name="medialine-table"></a>Table MediaLine
 
Chaque enregistrement représente une ligne de média. (Une seule session audio généralement contient une seule ligne de média audio. Un audio et vidéo (A / V) session généralement contient un média audio et une ligne de média vidéo, bien que la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Paramètre ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de la Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de la Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |audio principal est de 0, 1 est la vidéo principale et 2 vidéo panoramique, 3 est l’Application/partage du bureau, 16 correspond à la vidéo en fonction de partage d’écran (VbSS). Cette étiquette doit être unique au sein d’une seule session.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Cette colonne est présente, mais non utilisé dans Microsoft Lync Server 2013. Plus d’informations sur la connectivité utilisée pour une ligne de média sont capturés dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informations sur les processus établissement ICE (Interactive Connectivity) décrites dans les indicateurs de bits. Pour plus d’informations, reportez-vous à la *Qualité de l’expérience Monitoring Server Spécification de protocole* , disponible en téléchargement. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identique à CallerIceWarningFlags, mais sur le côté de l’appelé. Pour plus d’informations, reportez-vous à la *Qualité de l’expérience Monitoring Server Spécification de protocole* , disponible en téléchargement. <br/> |
|**Sécurité** <br/> |tinyint  <br/> | <br/> |Le profil de sécurité en cours d’utilisation. 0 correspond à aucun, 1 SRTP, 2 V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 est UDP, 1 est TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP de l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Port utilisé par l’appelant. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Étrangère <br/> |Le sous-réseau de l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 signifie que l’appelant est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Étrangère  <br/> |Adresse mac de l’appelant, référencée depuis [la table MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP du A / V Edge service utilisé par l’appelant. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur A / V Edge de service à l’appelant.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Étrangère  <br/> |Capturer le périphérique utilisé par l’appelant. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Étrangère  <br/> |Rendu d’appareil utilisé par l’appelant. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de capture de l’appelant, référencé depuis la [DeviceDriver table](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de rendu de l’appelant, référencé depuis la [DeviceDriver table](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Étrangère  <br/> |Indique comment l’appelant s’est connecté au réseau. Valeurs sont obtenues à partir de la [table NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs par défaut sont 0 pour une connexion câblée ' 1 pour une connexion Wi-Fi ; et 3 pour une connexion Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Étrangère  <br/> |L’appelant BSSID en cas d’utilisation sans fil. Référencé à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Lien de l’appelant. 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|**CallerLinkSpeed** <br/> |Decimal(18,0)  <br/> ||Vitesse de la liaison réseau, en bits/s, pour le point de terminaison de l’appelant.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP du destinataire de l’appel. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Port utilisé par le récepteur de l’appel.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Étrangère  <br/> |Sous-réseau de l’appelé. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 signifie récepteur de l’appel est à l’intérieur du réseau d’entreprise, 0 signifie que le récepteur de l’appel est en dehors du réseau.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Étrangère  <br/> |Adresse Mac de l’appelé. Référencé depuis la [table MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP du A / V Edge service utilisé par le récepteur de l’appel. Voir la [table IPAddress](ipaddress.md) pour plus d’informations. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur A / V Edge par le récepteur de l’appel de Service.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |étrangère  <br/> |Capturer le périphérique utilisé par le récepteur de l’appel. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Étrangère  <br/> |Périphérique utilisé par le récepteur de l’appel de rendu. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de capture du destinataire de l’appel. Référencé depuis la [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Étrangère  <br/> |Pilote de périphérique de rendu du destinataire de l’appel. Référencé depuis la [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Étrangère  <br/> |Indique comment l’appelé connectés au réseau. Valeurs sont obtenues à partir de la [table NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs par défaut sont 0 pour une connexion câblée ' 1 pour une connexion Wi-Fi ; et 3 pour une connexion Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Étrangère  <br/> |L’appelé BSSID en cas d’utilisation sans fil. Référencé à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Lien du destinataire de l’appel ; 1 correspond à un réseau privé virtuel (VPN), 0 non VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |Decimal(18,0)  <br/> | <br/> |Vitesse de la liaison réseau, en bits/s, pour le point de terminaison du destinataire de l’appel.  <br/> |
|**ConversationalMOS** <br/> |Decimal (3,2)  <br/> | <br/> |Note MOS qualité de la conversation à bande étroite des sessions audio (basées sur les deux flux audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Il s’agit de la bande passante effective à appliquer au flux côté envoi donné donné différents paramètres de stratégie (activer, API, SDP, stratégie de serveur, etc.). Il ne doit ne pas être confondu avec la bande passante effective, car il peut y avoir une bande passante réduite efficace en fonction de l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale que le flux d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Il s’agit de la source de l’extrémité de la bande passante imposée en cours. Il décrit la limite de bande passante provenance (« Stratégie de serveur », « Activer le serveur », « Modalité » et ainsi de suite). Référencé à partir de la [table AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Appelant** <br/> |bit  <br/> | <br/> |Indique si les mesures de l’appelant a été reçues ; 1 pour Oui, une valeur null est aucun.  <br/> |
|**Appelé** <br/> |bit  <br/> | <br/> |Indique si les mesures du récepteur d’appel ont été reçues ; 1 pour Oui, une valeur null est aucun.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indique si le rapport est une partie de la session ou de la session terminée.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indique si un appel a été classé comme médiocre (valeur 1) ou un appel de bonne qualité (0).  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |Entier très petit  <br/> ||Indique si l’appelant est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indique si l’appelant est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP réflexive de l’utilisateur qui a passé l’appel. Dans les organisations qui utilisent NAT (traduction d’adresses réseau), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Étrangère  <br/> |Description du périphérique du pilote WiFi employé par l’utilisateur qui a passé l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Étrangère  <br/> |Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent NAT (traduction d’adresses réseau), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Étrangère  <br/> |Description du pilote WiFi employé par l’utilisateur qui a reçu l’appel du périphérique.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Étrangère  <br/> |Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
   

