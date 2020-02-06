---
title: Affichage MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: Le mode MediaLine stocke les informations relatives à chaque ligne multimédia dans la base de données. Une seule session audio contient généralement une ligne multimédia audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: b22408ddc40f1df6452895327e8a67800ef24eb9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808192"
---
# <a name="medialine-view"></a>Affichage MediaLine
 
Le mode MediaLine stocke les informations relatives à chaque ligne multimédia dans la base de données. Une seule session audio contient généralement une ligne multimédia audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**taille**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |DateHeure  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|Sécurité  <br/> |tinyint  <br/> |Profil de sécurité en cours d’utilisation. 0 est aucun, 1 est SRTP, 2 est v1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Type de transport. 0 correspond au protocole UDP, 1 au port TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant figure ou non dans le réseau de l’organisation. 1 désigne l’appelant au sein du réseau d’entreprise. 0 signifie que l’appelant se trouve hors du réseau.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Adresse MAC de l’interface réseau utilisée par l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant communiquée par le service Edge A/V. Cette adresse peut être différente de l’CallerIPAddr si le client est situé derrière un NAT par exemple.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de rendu de l’appelant.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Description du pilote WiFi de l’appelant.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |Version du pilote WiFi de l’appelant.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Détails de la connexion réseau de l’appelant. Pour plus d’informations, voir la [table NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |Identifiant de l’ensemble de services standard utilisé par les appelants WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appel est inclus dans le réseau d’entreprise. 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Adresse MAC de l’interface réseau utilisée par le destinataire.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |Adresse IP du destinataire indiquée par le service Edge A/V. Cette adresse peut être différente de l’CalleeIPAddr si le client est situé derrière un NAT par exemple.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |Nom de l’appareil de capture du destinataire.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de l’appareil de capture du appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Description du pilote WiFi de l’appelant.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Version du pilote WiFi de l’appelant.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Détails de la connexion réseau du destinataire. Pour plus d’informations, voir la [table NetworkConnectionDetail](networkconnectiondetail.md) . <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Identificateur du jeu de service utilisé par la connexion WiFi de l’appelant.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant est connecté via un réseau privé virtuel. 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|ConversationalMOS  <br/> |décimale (3, 2)  <br/> |La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Il s’agit de la bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Cela ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitation par l’estimation de bande passante.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Source de la bande passante imposée. Il décrit l’emplacement vers lequel la limite de bande passante provient (par exemple, « serveur de stratégie », « activer le serveur » ou « modalité »).  <br/> |
|Appelant  <br/> |bit  <br/> |Indique si les mesures de l’appelant ont été reçues ; 1 est oui, 0 est non.  <br/> |
|Appelé  <br/> |bit  <br/> |Indique si les mesures du destinataire de l’appel ont été reçues. 1 est oui, 0 est non.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indique s’il s’agit d’une portion de l’appel ou de l’appel complet.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indique si un appel a été considéré comme un appel médiocre (1) ou comme bon appel (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indique si l’appelant s’est connecté au réseau via le protocole ICE (établissement de connectivité Internet).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indique si l’utilisateur s’est connecté au réseau à l’aide du protocole ICE (établissement d’une connexion Internet).  <br/> |
   

