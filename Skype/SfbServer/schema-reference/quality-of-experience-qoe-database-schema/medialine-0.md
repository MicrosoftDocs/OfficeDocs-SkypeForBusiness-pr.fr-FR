---
title: Table MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Chaque enregistrement représente une ligne multimédia. (Une session audio est généralement composée d’une seule ligne de média audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.
ms.openlocfilehash: f9ededade35e5654a89b68343f44094f4319ae70
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294893"
---
# <a name="medialine-table"></a>Table MediaLine
 
Chaque enregistrement représente une ligne multimédia. (Une session audio est généralement composée d’une seule ligne de média audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo, bien que la session puisse contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référence à partir de la [table de session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référence à partir de la [table de session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |0 correspond au son principal, 1 correspond à la vidéo principale et 2 correspond à la vidéo panoramique, 3 au partage d’applications et de bureau, 16 correspond au partage d’écran vidéo (VbSS). Cette étiquette doit être unique au sein d’une même session.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Cette colonne est présente mais n’est pas utilisée dans Microsoft Lync Server 2013. Les informations relatives à la connectivité utilisée pour une ligne multimédia sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs de bits. Pour plus d’informations, reportez-vous à la *spécification qualité de l’expérimentation du protocole serveur* , disponible au téléchargement. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identique à CallerIceWarningFlags, mais au côté de l’appelant. Pour plus d’informations, reportez-vous à la *spécification qualité de l’expérimentation du protocole serveur* , disponible au téléchargement. <br/> |
|**Sécurité** <br/> |tinyint  <br/> | <br/> |Profil de sécurité utilisé. 0 est aucun, 1 est SRTP, 2 est v1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 correspond au protocole UDP, 1 au port TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP de l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Port utilisé par l’appelant. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Externes <br/> |Sous-réseau de l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Externes  <br/> |Adresse MAC de l’appelant, référencée à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port utilisé par l’appelant sur le service Edge A/V.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Externes  <br/> |Appareil de capture utilisé par l’appelant. Référence à partir de la [table Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Externes  <br/> |Périphérique de rendu utilisé par l’appelant. Référence à partir de la [table Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Externes  <br/> |Pilote pour l’appareil de capture de l’appelant, référencé à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Externes  <br/> |Pilote de l’appareil de rendu de l’appelant, référencé à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externes  <br/> |Indique la manière dont l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de la [table NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi; et 3 pour une connexion Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Externes  <br/> |BSSID de l’appelant, si la technologie sans fil est utilisée. Référencée à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Le lien de l’appelant. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|**CallerLinkSpeed** <br/> |décimale (18, 0)  <br/> ||La vitesse de connexion du réseau, en BPS, pour le point de terminaison de l’appelant.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP du destinataire de l’appel. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CalleePort** <br/> |bit  <br/> ||Port utilisé par le destinataire de l’appel.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Externes  <br/> |Sous-réseau de l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 signifie que le destinataire de l’appel se trouve à l’intérieur du réseau d’entreprise, 0 correspond au destinataire de l’appel hors du réseau.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Externes  <br/> |Adresse MAC du destinataire. Fait référence à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP du service Edge A/V utilisée par le destinataire de l’appel. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur le service Edge A/V par le destinataire de l’appel.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |externes  <br/> |Appareil de capture utilisé par le destinataire de l’appel. Référence à partir de la [table Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Externes  <br/> |Périphérique de rendu utilisé par le destinataire de l’appel. Référence à partir de la [table Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Externes  <br/> |Pilote de l’appareil de capture du destinataire de l’appel. Fait référence à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Externes  <br/> |Pilote de l’appareil de rendu du destinataire de l’appel. Fait référence à partir de la [table DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externes  <br/> |Indique la manière dont l’appelant s’est connecté au réseau. Les valeurs sont obtenues à partir de la [table NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs par défaut sont 0 pour une connexion câblée' 1 pour une connexion WiFi; et 3 pour une connexion Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Externes  <br/> |Le BSSID de l’appelant si la technologie sans fil est utilisée. Référencée à partir de la [table MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Le lien du destinataire de l’appel; 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |décimale (18, 0)  <br/> | <br/> |La vitesse de connexion du réseau, en BPS, pour le point de terminaison du destinataire de l’appel.  <br/> |
|**ConversationalMOS** <br/> |décimale (3, 2)  <br/> | <br/> |La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |type  <br/> ||Il s’agit de la source de la bande passante qui est imposée. Il décrit l’emplacement à partir duquel la limite de bande passante provient («serveur de stratégie», «activer le serveur», «modalité», etc.). Fait référence à partir de la [table AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Appelant** <br/> |bit  <br/> | <br/> |Indique si les mesures de l’appelant ont été reçues; 1 est oui, la valeur null est non.  <br/> |
|**Appelé** <br/> |bit  <br/> | <br/> |Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, la valeur null est non.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indique si l’état correspond à une partie de la session ou à la session complète.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indique si un appel a été considéré comme un appel médiocre (valeur de 1) ou comme bon appel (0).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |Sa  <br/> ||Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP réflexive de l’utilisateur qui a placé l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Externes  <br/> |Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a placé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Externes  <br/> |Numéro de version du pilote WiFi utilisé par l’utilisateur qui a placé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Externes  <br/> |Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent la traduction d’adresses réseau (NAT), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Externes  <br/> |Description de l’appareil pour le pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Externes  <br/> |Numéro de version du pilote WiFi utilisé par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

