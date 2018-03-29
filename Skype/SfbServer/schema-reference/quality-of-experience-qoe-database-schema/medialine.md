---
title: Vue de MediaLine
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: La vue MediaLine stocke des informations sur chaque ligne de support dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient en général un média audio et une ligne de la vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 11905ae9ccc67bb166702f4d43f19d1b52bfbe7b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="medialine-view"></a>Vue de MediaLine
 
La vue MediaLine stocke des informations sur chaque ligne de support dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient en général un média audio et une ligne de la vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Référencé à partir de la [table de MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs pour l’appelant. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus d’établissement de connexion Interactive (ICE) décrite en bits indicateurs de l’appelé. Pour plus d’informations, reportez-vous à la qualité d’expérience Monitoring Server Spécification du protocole.  <br/> |
|Sécurité  <br/> |tinyint  <br/> |Profil de sécurité en cours d’utilisation. 0 signifie aucun, 1 SRTP, 2 V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport. UDP est de 0, 1 est TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelant. Il peut s’agir des adresses IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant est à l’intérieur du réseau de l’organisation. la valeur 1 signifie que l’appelant est à l’intérieur du réseau d’entreprise. 0 signifie que l’appelant est à l’extérieur du réseau.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC de l’interface réseau utilisée par l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’A / V Edge service utilisé par l’appelant. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelant.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Adresse d’IP de l’appelant comme signalé par l’A / V Edge service. Cette adresse peut être différente que la CallerIPAddr si le client se trouve derrière un NAT, par exemple.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nom du périphérique de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelant.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Description du pilote de Wi-Fi de l’appelant.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Version du pilote Wi-Fi de l’appelant.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de connexion réseau de l’appelant. Consultez le [tableau de NetworkConnectionDetail](networkconnectiondetail.md) pour plus d’informations. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Basic Service Set Identifier utilisé par des appelants de connexion WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’appelé. Il peut s’agir des adresses IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelé.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelé à l’intérieur du réseau d’entreprise. 1 appelé est à l’intérieur du réseau d’entreprise, 0 signifie que l’appelé est en dehors du réseau.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Adresse MAC de l’interface réseau utilisée par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Adresse IP de l’A / V Edge service utilisé par l’appelé. Consultez le [tableau d’adresse IP](ipaddress.md) pour plus d’informations. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur A / V Edge service utilisé par l’appelé.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |AdresseIP l’appelé comme signalé par l’A / V Edge service. Cette adresse peut être différente que la CalleeIPAddr si le client se trouve derrière un NAT, par exemple.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nom du périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nom de périphérique du rendu de l’appelé.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de capture de l’appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nom de pilote de périphérique de rendu de l’appelé.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Description du pilote l’appelé Wifi.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Version du pilote Wi-Fi de l’appelé.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Détails de connexion réseau de l’appelé. Consultez le [tableau de NetworkConnectionDetail](networkconnectiondetail.md) pour plus d’informations. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Basic Service Set Identifier utilisé par la connexion Wi-Fi de l’appelé.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelé connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|ConversationalMOS  <br/> |Decimal (3,2)  <br/> |MOS de conversation à bande étroite des sessions audio (basées sur les deux flux de données audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Il s’agit de la bande passante réelle appliquée dans le flux du côté envoi donné étant donné les différents paramètres de stratégie (activer, API, SDP, stratégie de serveur, etc.). Cela ne doit ne pas être confondu avec la bande passante effective, car il peut y avoir une faible bande passante efficace basée sur l’estimation de la bande passante. Il s’agit essentiellement de la bande passante maximale que le flux de données d’envoi peut prendre intervenant dans les limites imposées par l’estimation de la bande passante.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Source de l’embout de la bande passante est imposée. Il décrit la limite de bande passante provenance (par exemple, « Policy Server », « Arrêter le serveur » ou « Modalité »).  <br/> |
|Appelant  <br/> |bit  <br/> |Indique si les métriques de l’appelant a été reçues ; 1 pour Oui, 0 est aucun.  <br/> |
|Appelé  <br/> |bit  <br/> |Indique si les métriques de destinataire de l’appel a été reçus ; 1 pour Oui, 0 est aucun.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indique si le rapport est pour une partie de l’appel ou l’appel terminé.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indique si un appel a été classé comme un appel faible (1) ou comme un appel de bonne (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indique si l’appelant est connecté au réseau en utilisant le protocole de la glace (établissement de connectivité Internet).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indique si l’utilisateur appelé connecté au réseau en utilisant le protocole de la glace (établissement de connectivité Internet).  <br/> |
   

