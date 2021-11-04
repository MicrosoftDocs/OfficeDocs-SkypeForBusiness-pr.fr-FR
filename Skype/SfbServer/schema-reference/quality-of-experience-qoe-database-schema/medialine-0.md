---
title: Table MediaLine
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Chaque enregistrement représente une ligne de média. (Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la vue Galerie est utilisée.
ms.openlocfilehash: ae2d776b47f7fe0ef172c9904ea77ae6188535fc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754283"
---
# <a name="medialine-table"></a>Table MediaLine
 
Chaque enregistrement représente une ligne de média. (Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la vue Galerie est utilisée.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Référencé à partir de [la table Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primaire  <br/> |Référencé à partir de [la table Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primaire  <br/> |0 est l’audio principal, 1 la vidéo principale et 2 la vidéo panoramique, 3 le partage d’application/bureau, 16 le partage d’écran vidéo (VbSS). Cette étiquette doit être unique au sein d’une seule session.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Cette colonne est présente, mais n’est pas utilisée dans Microsoft Lync Server 2013. Les informations sur la connectivité utilisée pour une ligne de média sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informations sur le processus ICE (Interactive Connectivity Establishment) décrit dans les indicateurs bits. Pour plus d’informations, reportez-vous à  *la spécification*  de protocole du serveur de surveillance de la qualité de l’expérience , disponible en téléchargement. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identique à CallerIceWarningFlags, mais côté appelé. Pour plus d’informations, reportez-vous à  *la spécification*  de protocole du serveur de surveillance de la qualité de l’expérience , disponible en téléchargement. <br/> |
|**Sécurité** <br/> |tinyint  <br/> | <br/> |Profil de sécurité en cours d’utilisation. 0 est AUCUN, 1 est SRTP, 2 est V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 est UDP, 1 est TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP de l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Port utilisé par l’appelant. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Étranger <br/> |Sous-réseau de l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est en dehors du réseau.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Étranger  <br/> |Adresse Mac de l’appelant, référencé à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur le service Edge A/V par l’appelant.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Étranger  <br/> |Appareil de capture utilisé par l’appelant. Référencé à partir de la [table Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Étranger  <br/> |Périphérique de rendu utilisé par l’appelant. Référencé à partir de la [table Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Étranger  <br/> |Pilote de l’appareil de capture de l’appelant, référencé à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Étranger  <br/> |Pilote du périphérique de rendu de l’appelant, référencé à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Étranger  <br/> |Indique comment l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de [la table NetworkConnectionDetail.](networkconnectiondetail.md) Les valeurs classiques sont 0 pour une connexion câblé' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Étranger  <br/> |BSSID de l’appelant si la technologie sans fil est utilisée. Référencé à partir [de la table MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Lien de l’appelant. 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Vitesse de liaison réseau, en bps, du point de terminaison de l’appelant.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP du récepteur d’appel. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CalleePort** <br/> |bit  <br/> ||Port utilisé par le récepteur d’appels.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Étranger  <br/> |Sous-réseau de l’appelé. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 signifie que le récepteur d’appels se trouve à l’intérieur du réseau d’entreprise, 0 signifie que le récepteur d’appels se trouve à l’extérieur du réseau.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Étranger  <br/> |Adresse Mac de l’appelé. Référencé à partir [de la table MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP du service Edge A/V utilisé par le récepteur d’appels. Pour plus [d’informations, voir la table IPAddress.](ipaddress.md) <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur le service Edge A/V par le récepteur d’appels.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |étranger  <br/> |Périphérique de capture utilisé par le récepteur d’appels. Référencé à partir de la [table Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Étranger  <br/> |Périphérique de rendu utilisé par le récepteur d’appels. Référencé à partir de la [table Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Étranger  <br/> |Pilote de l’appareil de capture du récepteur d’appels. Référencé à partir [de la table DeviceDriver.](devicedriver.md)  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Étranger  <br/> |Pilote du périphérique de rendu du récepteur d’appels. Référencé à partir [de la table DeviceDriver.](devicedriver.md)  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Étranger  <br/> |Indique comment l’appelé s’est connecté au réseau. Les valeurs sont obtenues à partir de [la table NetworkConnectionDetail.](networkconnectiondetail.md) Les valeurs classiques sont 0 pour une connexion câblé' 1 pour une connexion WiFi ; et 3 pour une connexion Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Étranger  <br/> |BSSID de l’appelé si la connexion sans fil est utilisée. Référencé à partir [de la table MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Lien du récepteur d’appels ; 1 est un réseau privé virtuel (VPN), 0 est un réseau non VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Vitesse de liaison réseau, en bps, du point de terminaison du récepteur d’appels.  <br/> |
|**ConversationalMOS** <br/> |décimal(3,2)  <br/> | <br/> |Note MOS qualité conversation à bande étroite des sessions audio (basés sur les deux flux audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Il s’agit de la bande passante réelle appliquée au flux côté envoi donné en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, et ainsi de suite). À ne pas confondre avec la bande passante effective car il peut exister une bande passante effective plus basse basée sur l’estimation de la bande passante. Il s’agit en fait de la bande passante maximale pouvant être traitée par le flux d’envoi en ne tenant pas compte des limites imposées par l’estimation de la bande passante.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Il s’agit de la source de la capacité de bande passante imposée. Il décrit d’où vient la limite de bande passante ( « Serveur de stratégie », « SERVEUR TURN », « Modalité », et ainsi de suite). Référencé à partir [de la table AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Indique si les mesures de l’appelant ont été reçues ; 1 est oui, une valeur null est non.  <br/> |
|**Appelé** <br/> |bit  <br/> | <br/> |Indique si les mesures du récepteur d’appels ont été reçues ; 1 est oui, une valeur null est non.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indique si le rapport est pour une partie de la session ou pour la session complète.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indique si un appel a été considéré médiocre (valeur 1) ou bon appel (0).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indique si l’appelant s’est connecté au réseau à l’aide du protocole ICE (Internet Connectivity Establishment).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP discrète de l’utilisateur qui a passé l’appel. Dans les organisations qui utilisent nat (traduction d’adresses réseau), l’adresse IP d’erreur est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Étranger  <br/> |Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a passé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Étranger  <br/> |Numéro de version du pilote WiFi employé par l’utilisateur qui a passé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Étranger  <br/> |Adresse IP discrète de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent nat (traduction d’adresses réseau), l’adresse IP d’erreur est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Étranger  <br/> |Description de l’appareil pour le pilote WiFi employé par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Étranger  <br/> |Numéro de version du pilote WiFi employé par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

