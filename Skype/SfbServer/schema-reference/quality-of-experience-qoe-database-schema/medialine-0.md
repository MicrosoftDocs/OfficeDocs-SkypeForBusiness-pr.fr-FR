---
title: Table MediaLine
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Chaque enregistrement représente une seule ligne de media. (Une session audio généralement contient une seule ligne de média audio. Un audio et vidéo (A / V) session généralement contient un média audio et une ligne de média vidéo, bien que la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée.
ms.openlocfilehash: 03da40b97c6a067f13a9855cd51b1bbb4780f2ad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-table"></a>Table MediaLine
 
Chaque enregistrement représente une seule ligne de media. (Une session audio généralement contient une seule ligne de média audio. Un audio et vidéo (A / V) session généralement contient un média audio et une ligne de média vidéo, bien que la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateHeure  <br/> |Principal  <br/> |Référencé à partir de la [table de la Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principal  <br/> |Référencé à partir de la [table de la Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principal  <br/> |audio principal est de 0, 1 est la vidéo principale et 2 vidéo panoramique, 3 est le partage de bureau / l’Application. Cette étiquette doit être unique au sein d’une même session.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Cette colonne est présente mais non utilisé dans Microsoft Lync Server 2013. Informations sur la connectivité utilisée pour une ligne de support sont capturées dans les colonnes CallerConnectivityICE et CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrit dans les indicateurs de bits. Pour plus d’informations, reportez-vous à la *Qualité d’expérience Monitoring Server Spécification de protocole* , disponible au téléchargement. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Identique à CallerIceWarningFlags, mais sur le côté de l’appelé. Pour plus d’informations, reportez-vous à la *Qualité d’expérience Monitoring Server Spécification de protocole* , disponible au téléchargement. <br/> |
|**Sécurité** <br/> |tinyint  <br/> | <br/> |Le profil de sécurité en cours d’utilisation. 0 signifie aucun, 1 SRTP, 2 V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |UDP est de 0, 1 est TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP de l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Port utilisé par l’appelant. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Étrangère <br/> |Le sous-réseau de l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 signifie que l’appelant est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelant est à l’extérieur du réseau.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Étrangère  <br/> |Adresse mac de l’appelant, référencé à partir de la [table d’adresse MAC](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP de l’A / V Edge service utilisé par l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur A / V Edge service par l’appelant.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Étrangère  <br/> |Capturer le périphérique utilisé par l’appelant. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Étrangère  <br/> |Rendre un périphérique utilisé par l’appelant. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de capture de l’appelant, référencé à partir de la [table de DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de rendu de l’appelant, référencé à partir de la [table de DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Étrangère  <br/> |Indique la façon dont l’appelant est connecté au réseau. Les valeurs sont obtenues à partir de la [table de NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs typiques sont 0 pour une connexion filaire ' 1 pour une connexion Wi-Fi. et 3 pour une connexion Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Étrangère  <br/> |L’appelant 's BSSID si sans fil est utilisé. Référencé à partir de la [table d’adresse MAC](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Lien de l’appelant. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|**CallerLinkSpeed** <br/> |Decimal(18,0)  <br/> ||La vitesse de liaison réseau, en bits/s, pour le point de terminaison de l’appelant.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP du destinataire de l’appel. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Port utilisé par le destinataire de l’appel.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Étrangère  <br/> |Sous-réseau de l’appelé. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 récepteur d’appel est à l’intérieur du réseau d’entreprise, 0 signifie que destinataire de l’appel est en dehors du réseau.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Étrangère  <br/> |Adresse Mac d’appelé. Référencé à partir de la [table d’adresse MAC](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP de l’A / V Edge service utilisé par le destinataire de l’appel. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Port utilisé sur A / V Edge Service par le destinataire de l’appel.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |étrangère  <br/> |Capturer le périphérique utilisé par le destinataire de l’appel. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Étrangère  <br/> |Rendre un périphérique utilisé par le destinataire de l’appel. Référencé à partir de la [table de périphériques](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Étrangère  <br/> |Pilote de périphérique de capture du destinataire de l’appel. Référencé à partir de la [table de DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Étrangère  <br/> |Pilote de périphérique de rendu du destinataire de l’appel. Référencé à partir de la [table de DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Étrangère  <br/> |Indique comment l’appelé est connecté au réseau. Les valeurs sont obtenues à partir de la [table de NetworkConnectionDetail](networkconnectiondetail.md). Les valeurs typiques sont 0 pour une connexion filaire ' 1 pour une connexion Wi-Fi. et 3 pour une connexion Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Étrangère  <br/> |Appelé 's BSSID si sans fil est utilisé. Référencé à partir de la [table d’adresse MAC](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Liens du destinataire de l’appel ; 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |Decimal(18,0)  <br/> | <br/> |La vitesse de liaison réseau, en bits/s, pour le point de terminaison du destinataire de l’appel.  <br/> |
|**ConversationalMOS** <br/> |Decimal (3,2)  <br/> | <br/> |MOS de conversation à bande étroite des sessions audio (basées sur les deux flux de données audio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Il s’agit de la bande passante réelle appliquée dans le flux du côté envoi donné étant donné les différents paramètres de stratégie (TURN, API, SDP, stratégie de serveur, etc.). Ne doit ne pas être confondue avec la bande passante effective, car il peut y avoir une faible bande passante efficace basée sur l’estimation de la bande passante. Il s’agit essentiellement de la bande passante maximale que le flux de données d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Il s’agit de la source de l’embout de la bande passante est imposée. Il décrit la limite de bande passante provenance (« Policy Server », « Arrêter le serveur », « Modalité », etc.). Référencé à partir de la [table de AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Appelant** <br/> |bit  <br/> | <br/> |Indique si les métriques de l’appelant a été reçues ; 1 Oui, une valeur null est aucun.  <br/> |
|**Appelé** <br/> |bit  <br/> | <br/> |Indique si les métriques de destinataire de l’appel a été reçus ; 1 Oui, une valeur null est aucun.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indique si le rapport est pour une partie de la session ou pour l’intégralité de la session.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indique si un appel a été classé comme un appel faible (valeur 1) ou comme un appel de bonne (0).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indique si l’appelant est connecté au réseau en utilisant le protocole de la glace (établissement de connectivité Internet).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indique si l’appelant est connecté au réseau en utilisant le protocole de la glace (établissement de connectivité Internet).  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP réflexive de l’utilisateur qui a passé l’appel. Dans les organisations qui utilisent NAT (traduction d’adresses réseau), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Étrangère  <br/> |Description du périphérique pour le pilote Wi-Fi employée par l’utilisateur qui a passé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Étrangère  <br/> |Numéro de version du pilote Wi-Fi employée par l’utilisateur qui a passé l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Étrangère  <br/> |Adresse IP réflexive de l’utilisateur qui a reçu l’appel. Dans les organisations qui utilisent NAT (traduction d’adresses réseau), l’adresse IP réflexive est l’adresse IP du serveur proxy.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Étrangère  <br/> |Description du périphérique pour le pilote Wi-Fi employée par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Étrangère  <br/> |Numéro de version du pilote Wi-Fi employée par l’utilisateur qui a reçu l’appel.  <br/> Cette colonne a été introduite dans Microsoft Lync Server 2013.  <br/> |
   

