---
title: Affichage AudioStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: Le mode AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 16f97fc367b171ceb0ddc5b5c0024bd88c7b5268
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295054"
---
# <a name="audiostreamdetail-view"></a>Affichage AudioStreamDetail
 
Le mode AudioStreamDetail stocke les informations relatives à chaque flux audio dans la base de données. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateHeure  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Fait référence à partir de la [table MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |IDENTIFIant unique dans une ligne de médias.  <br/> |
|StartTime  <br/> |DateHeure  <br/> |Heure de début de la session.  <br/> |
|EndTime  <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Catégorie de boîte de dialogue: 0 est le tronçon du serveur Skype entreprise Server to Mediation. 1 est le serveur de médiation pour le tronçon de passerelle PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Indicateur indiquant si l’appel a été ignoré ou non.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Le cas échéant, indique pourquoi un appel n’a pas été ignoré, même si les ID de contournement correspondent. Une seule valeur est définie:  <br/> 0x0001-ID de contournement inconnu pour la carte réseau par défaut.  <br/> |
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
|CorrelationKey  <br/> ||Clé de corrélation. Fait référence à partir de la [table SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Des informations sur le chemin multimédia, par exemple direct ou relayé. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informations sur le processus de création d’une connexion interactive (ICE) décrite dans les indicateurs bits pour l’appelant. Pour plus d’informations, reportez-vous à la spécification relative au protocole serveur pour le contrôle qualité.  <br/> |
|Transport  <br/> |tinyint  <br/> |Le type de transport: 0 correspond au protocole UDP; 1 est le protocole TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur du réseau intervalle: 1 désigne l’appelant à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Adresse IP de l’appelant. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Port utilisé par l’appelant.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indique si l’appelant se trouve à l’intérieur de l’intervalle réseau: 1 signifie que l’appelant se trouve à l’intérieur du réseau d’entreprise, 0 indique que l’appelant se trouve hors du réseau.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nom du site de l’appelant.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nom du site du ou des appelants.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nom du pays/de la région du site de l’appelant.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Clé d’adresse IP du service Edge A/V utilisé par l’appelant. Pour plus d’informations, voir la [table IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Port utilisé sur le service Edge A/V utilisé par l’appelant.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de capture de l’appelant.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de capture de l’appelant.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |Nom du pilote de périphérique de rendu de l’appelant.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de capture du destinataire.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nom de l’appareil de rendu de l’appelant.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote de l’appareil de capture du appelé.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nom du pilote du périphérique de rendu de l’appelant.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau de l’appelant: 0 est filaire, 1 est un réseau sans fil.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel: 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CallerLinkSpeed  <br/> |décimale (18, 0)  <br/> |Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Type de connexion réseau du ou du destinataire: 0 est filaire, 1 est un téléphone sans fil.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indique si l’appelant s’est connecté via un réseau privé virtuel: 1 est un réseau privé virtuel (VPN), 0 est non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |décimale (18, 0)  <br/> |Vitesse de liaison réseau pour le point de terminaison de l’appelant en bps.  <br/> |
|ConversationalMOS  <br/> |décimale (3, 2)  <br/> |La fonction de conversation à bande étroite des sessions audio (en fonction des deux flux audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Bande passante réelle appliquée au flux d’envoi indiqué en fonction de différents paramètres de stratégie (TURN, API, SDP, serveur de stratégie, etc.). Ce problème ne doit pas être confondu avec la bande passante effective, car il peut y avoir une bande passante effective plus faible en fonction de l’estimation de bande passante. Il s’agit essentiellement de la bande passante maximale que le flux d’envoi peut prendre en limitant l’estimation de la bande passante.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Gigue réseau moyenne des statistiques de protocole RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Scintillement du réseau maximum lors de l’appel.  <br/> |
|PacketLossRate  <br/> |décimale (5; 4)  <br/> |Taux moyen de perte de paquets lors de l’appel.  <br/> |
|PacketLossRateMax  <br/> |décimale (5; 4)  <br/> |Perte de paquets maximum observée pendant l’appel.  <br/> |
|BurstDensity  <br/> |décimale (9; 4)  <br/> |Densité moyenne de perte de paquets en rafales de pertes pendant l’appel.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durée moyenne de perte de paquets en rafales de pertes pendant l’appel.  <br/> |
|BurstGapDensity  <br/> |décimale (9; 4)  <br/> |Densité moyenne de perte de paquets lors de l’intervalle entre les pics de perte de paquets.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durée moyenne des espaces entre les pics de perte de paquets.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Nombre de paquets pour le flux audio.  <br/> |
|Bande passante  <br/> |int  <br/> |Estimations de bande passante pour le flux audio.  <br/> |
|DegradationAvg  <br/> |décimale (3, 2)  <br/> |Baisse de la dégradation du réseau pour l’ensemble de l’appel. La plage est 0,0 à 5,0. Cette mesure indique la somme que le coût du réseau a diminué en raison de la gigue et de la perte de paquets. Pour une qualité acceptable, elle doit être inférieure à 0,5.  <br/> |
|DegradationMax  <br/> |décimale (3, 2)  <br/> |Dégradation du réseau maximal pendant l’appel.  <br/> |
|DegradationJitterAvg  <br/> |décimale (3, 2)  <br/> |Baisse de la dégradation du réseau à l’origine de gigue.  <br/> |
|DegradationPacketLossAvg  <br/> |décimale (3, 2)  <br/> |Baisse de la dégradation du réseau à l’origine de la perte de paquets.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Le codec audio utilisé pour l’appel, référencé à partir de la [table PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taux d’échantillonnage pour le flux audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Le niveau du signal audio après le contrôle de gain analogique pour le son envoyé par l’appelant. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Niveau du signal audio de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Le niveau sonore de contrôle du bruit de l’appelant envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Le niveau de bruit audio de contrôle de gain analogique pour le son reçu par l’appelant. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Amélioration de la perte d’écho pour l’appelant. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |décimale (9; 2)  <br/> |Taux d’utilisation de l’horloge du périphérique microphone de l’appelant par rapport à l’horloge de l’UC.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |décimale (9; 2)  <br/> |Taux d’horloge des périphériques de haut-parleurs de l’appelant par rapport à l’horloge de l’UC.  <br/> |
|CallerTimestampErrorMicMs  <br/> |décimale (9; 2)  <br/> |Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |décimale (9; 2)  <br/> |Moyenne de l’erreur d’horodatage du flux de haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|CallerVsEntryCauses  <br/> |type  <br/> |Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement ECHO pour l’appelant. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CallerEchoPercentMicIn  <br/> |décimale (5; 2)  <br/> |Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du microphone de l’appelant. Si le casque est utilisé, la valeur doit être faible.  <br/> |
|CallerEchoPercentSend  <br/> |décimale (5; 2)  <br/> |Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé de l’appelant. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre-30 et-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelant.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Représente le niveau du signal audio du contrôle du gain sur le son de l’appel envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Niveau du signal audio pour le son de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Le niveau sonore de contrôle du bruit d’après-analogue pour le son de l’appel envoyé. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Le niveau sonore du contrôle du bruit de la fonction de gain analogique pour le son de l’appelant reçu. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Extension du retour de l’écho pour l’appelant. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur de l’appelant. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Moyenne des problèmes par cinq minutes pour la capture du micro de l’appelant. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |décimale (9; 2)  <br/> |Taux d’utilisation de l’horloge du périphérique du micro du destinataire, par rapport à l’horloge de l’UC.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |décimale (9; 2)  <br/> |Taux d’horloge de l’horloge du périphérique du présentateur, par rapport à l’horloge du processeur.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |décimale (9; 2)  <br/> |Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |décimale (9; 2)  <br/> |Moyenne de l’erreur d’horodatage du flux de rendu du haut-parleur de l’appelant, en millisecondes, au cours des dernières 20 secondes de l’appel.  <br/> |
|CalleeVsEntryCauses  <br/> |type  <br/> |Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causes d’un événement ECHO pour l’appelant. Pour plus d’informations, voir la [table MediaLine](medialine-0.md) . <br/> |
|CalleeEchoPercentMicIn  <br/> |décimale (5; 2)  <br/> |Pourcentage de temps pendant lequel l’écho est détecté dans le flux de capture du micro de l’appelant. Si le casque est utilisé, la valeur doit être faible.  <br/> |
|CalleeEchoPercentSend  <br/> |décimale (5; 2)  <br/> |Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé du destinataire du appel. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelant; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Reçu le niveau du signal sur le serveur de médiation de la passerelle pour le son de l’appelé. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Contrôle automatique de gain sur le côté du serveur de médiation appliqué au son de l’appelé.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Moyenne quadratique (quadratique) du signal entrant à l’appelant pour les 30 premières secondes de l’appel.  <br/> |
|RatioConcealedSamplesAvg  <br/> |décimale (5; 2)  <br/> |Taux moyen d’échantillons masqués générés par la correction audio sur des exemples classiques.  <br/> |
|RatioStretchedSamplesAvg  <br/> |décimale (5; 2)  <br/> |Taux moyen d’échantillons étirés générés par la correction audio sur des exemples classiques.  <br/> |
|RatioCompressedSamplesAvg  <br/> |décimale (5; 2)  <br/> |Taux moyen d’échantillons compressés générés par la correction audio sur des exemples classiques.  <br/> |
|RoundTrip  <br/> |int  <br/> |Durée de l’aller-retour des statistiques RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Durée de l’aller-retour maximal pour le flux audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |décimale (3, 2)  <br/> |MOS du réseau à bandes moyenne pour l’appel. Cette métrique dépend du niveau de perte de paquets, de gigue et de codec utilisés. La plage est 1,0 à 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |décimale (3, 2)  <br/> |Débit du réseau à large bande minimum pour l’appel.  <br/> |
|SendListenMOS  <br/> |décimale (3, 2)  <br/> |Score d’écoute de la bande moyenne prédite pour le son envoyé, avec les caractéristiques de niveau de voix, de niveau de bruit et de périphérique de capture.  <br/> |
|SendListenMOSMin  <br/> |décimale (3, 2)  <br/> |SendListenMOS minimum pour l’appel.  <br/> |
|RecvListenMOS  <br/> |décimale (3, 2)  <br/> |Score d’écoute de la bande moyenne prédite pour le son reçu du réseau, y compris le niveau de synthèse vocale, le niveau sonore, le codec, les conditions du réseau et les caractéristiques de l’appareil de capture.  <br/> |
|RecvListenMOSMin  <br/> |décimale (3, 2)  <br/> |RecvListenMOS minimum pour l’appel.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indique si l’audio FEC a été utilisé pour l’appel.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indique la direction des informations d’identification par le biais de la déclaration p; 1 signifie que le sens du flux provient de l’appelant vers l’appelant; 0: le sens du flux provient de l’appelant.  <br/> |
   

