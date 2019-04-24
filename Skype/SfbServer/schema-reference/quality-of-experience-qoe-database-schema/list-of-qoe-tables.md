---
title: Liste des tables QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Le schéma de base de données comprend les tables suivantes.
ms.openlocfilehash: c3ab045e67f38082910f5a2870d4e8c0c8e595b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212220"
---
# <a name="list-of-qoe-tables"></a>Liste des tables QoE
 
Le schéma de base de données comprend les tables suivantes. 
  
**Tables de prise en charge**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec le partage d’application.  <br/> |
|[Table CodecDescription](codecdescription.md) <br/> |Mappe des identificateurs de codec uniques à leur codec correspondant.  <br/> |
|[Table IPAddress](ipaddress.md) <br/> |Mappe des adresses IP pour les identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience.  <br/> |
|[Table NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience.  <br/> |
|[Table PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Stocke des informations qui indiquent si (et quand) obsolètes Quality of Experience enregistrements seront automatiquement supprimés de la base de données QoE.  <br/> |
|[Table TraceRoute](traceroute.md) <br/> |Stocke les informations de routage pour les appels.  <br/> |
|[Table UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.  <br/> |
|[Table VideoMetricsThreshold](videometricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec les appels vidéo.  <br/> |
|[Table UserAgent](useragent.md) <br/> |Stocke les chaînes de protocole SIP (Session Initiation) utilisateur Agent (UA) et les types utilisés dans des sessions audio et vidéos.  <br/> |
|[Table User](user-0.md) <br/> |Utilisateur de magasins, de conférence et URI de téléphone utilisés dans des sessions audio et vidéos.  <br/> |
|[Table Endpoint](endpoint.md) <br/> |Stocke les noms d’ordinateur de nom de domaine complet des systèmes d’extrémité participant à des sessions audio et vidéos.  <br/> |
|[Table Pool](pool.md) <br/> |Stocke les noms des pools pour les mesures de données appartient.  <br/> |
|[Table Device](device.md) <br/> |Stocke les périphériques de capture et afficher les périphériques qui sont utilisés dans un appels audio/vidéo.  <br/> |
|[Table DeviceDriver](devicedriver.md) <br/> |Stocke le pilote pour le périphérique de capture et le périphérique de rendu qui sont utilisés dans les appels audio/vidéo.  <br/> |
|[Table Conference](conference.md) <br/> |Stocke les URI de conférence pour les scénarios de conférence ou le DialogID pour d’autres scénarios.  <br/> |
|[Table SessionCorrelation](sessioncorrelation.md) <br/> |Stocke le CorrelationID pour les appels PSTN.  <br/> |
|[Table PayloadDescription](payloaddescription.md) <br/> |Stocke le Codec utilisé dans les appels audio/vidéo.  <br/> |
|[Table AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Stocke la source de la bande passante utilisée dans les appels audio/vidéo.  <br/> |
|[Table MacAddress](macaddress.md) <br/> |Stocke l’adresse MAC des systèmes d’extrémité participant à des sessions audio et vidéos.  <br/> |
|[Table Dialog](dialog.md) <br/> |Enregistre l’ID de la boîte de dialogue des sessions audio et vidéo.  <br/> |
|[Table Region](region.md) <br/> |Stocke la région réseau définie dans le paramètre NCS.  <br/> |
|[Table UserSite](usersite.md) <br/> |Stocke le site réseau défini dans le paramètre NCS.  <br/> |
|[Table Subnet](subnet.md) <br/> |Stocke le sous-réseau défini dans le paramètre NCS.  <br/> |
|[Table MonitoredRegionLink](monitoredregionlink.md) <br/> |Stocke le lien de région défini dans le paramètre NCS.  <br/> |
|[Table MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Stocke les liens de site réseau définis dans le paramètre NCS.  <br/> |
|[Table EndpointSubnet](endpointsubnet.md) <br/> |Stocke le sous-réseau du système d’extrémité participant à une session audio et vidéo.  <br/> |
|[Table Server](server.md) <br/> |Stocke le nom de domaine complet ou l’adresse IP du serveur que parcourt le média.  <br/> |
   
**Tables de données de mesure**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingStream](appsharingstream.md) <br/> |Stocke les mesures de qualité de l’expérience pour les flux de réseau utilisés pour le partage d’application. Qualité de mesures de l’expérience pour les flux de réseau utilisés pour le partage d’application.  <br/> |
|[Table Session](session.md) <br/> |Stocke des informations générales sur une session audio ou audio/vidéo. Une session est définie comme une boîte de dialogue SIP audio ou vidéo entre deux points de terminaison.  <br/> |
|[Table MediaLine](medialine-0.md) <br/> |Stocke des informations sur chaque ligne de média dans une session. Une ligne de média est une collection d’un ou plusieurs flux audio et vidéos. En règle générale, une ligne de média unique aura deux flux, audio ou vidéos.  <br/> |
|[Table AudioStream](audiostream.md) <br/> |Stocke les mesures de qualité des médias audio pour chaque flux audio dans la ligne de média.  <br/> |
|[Table AudioSignal](audiosignal.md) <br/> |Stocke les mesures de qualité du média audio dans la ligne de média. Cela inclut l’annulation de l’écho acoustique (AEC) et les mesures de réglage de gain automatique.  <br/> |
|[Table VideoStream](videostream.md) <br/> |Stocke les mesures de qualité du média vidéo pour chaque flux audio dans la ligne de média.  <br/> |
|[Table AudioClientEvent](audioclientevent.md) <br/> |Stocke les mesures de qualité de média audio collectées à partir de l’événement client.  <br/> |
|[Table VideoClientEvent](videoclientevent.md) <br/> |Stocke les mesures de qualité vidéo collectées à partir de l’événement client.  <br/> |
|**Table DiagnosticData** <br/> |Stocke les données de diagnostic qui est à usage interne uniquement.  <br/> |
   
**Tables de données de synthèse**

|**Table**|**Description**|
|:-----|:-----|
|**Table ServerSummary** <br/> |Stocke les données de synthèse pour les serveurs, ces données sont utilisées pour la qualité de l’expérience (QoE) reporting uniquement.  <br/> |
|**Table UserSummary** <br/> |Stocke les données de synthèse pour les utilisateurs, ces données sont utilisées pour QoE reporting uniquement.  <br/> |
|**Table CallTypeSummary** <br/> |Magasin des données de synthèse pour les types d’appels, ces données sont utilisées pour QoE reporting uniquement.  <br/> |
   
**Tables pour une utilisation interne par le serveur de surveillance**

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**Table FrontEnd** <br/> |À usage interne uniquement.  <br/> |
|**Table des tâches** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**MetricsThreshold** <br/> |À usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |À usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Fuseaux horaires** <br/> |À usage interne uniquement.  <br/> |
|**Table CallSummary** <br/> |À usage interne uniquement.  <br/> |
|**Table DeviceCallSumary** <br/> |À usage interne uniquement.  <br/> |
|**Table tenant** <br/> |À usage interne uniquement.  <br/> |
|**VideoCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
|**ASCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
   

