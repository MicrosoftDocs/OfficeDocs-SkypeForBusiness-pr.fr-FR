---
title: Liste des tables de qualité de l’expérience (QoE)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Le schéma de base de données comprend les tables suivantes.
ms.openlocfilehash: 0532d1574bcbbe80a58195d2c14ea6920375153f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767292"
---
# <a name="list-of-qoe-tables"></a>Liste des tables de qualité de l’expérience (QoE)
 
Le schéma de base de données comprend les tables suivantes. 
  
**Tables de prise en charge**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec le partage d’application.  <br/> |
|[Table CodecDescription](codecdescription.md) <br/> |Mappe des identificateurs de codec uniques à leur codec correspondant.  <br/> |
|[Table IPAddress](ipaddress.md) <br/> |Mappe des adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).  <br/> |
|[Table NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience (QoE).  <br/> |
|[Table PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Stocke des informations qui indiquent si (et quand) les enregistrements de qualité de l’expérience obsolètes seront automatiquement supprimés de la base de données QoE.  <br/> |
|[Table TraceRoute](traceroute.md) <br/> |Stocke des informations de routage pour les appels.  <br/> |
|[Table UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Cartes identificateurs d’agent utilisateur aux noms descriptifs de l’agent.  <br/> |
|[Table VideoMetricsThreshold](videometricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les mesures de qualité de l’expérience utilisées avec les appels vidéo.  <br/> |
|[Table UserAgent](useragent.md) <br/> |Stocke les chaînes et les types d’agent utilisateur du protocole SIP (Session Initiation Protocol) utilisés dans des sessions audio et vidéo.  <br/> |
|[Table User](user-0.md) <br/> |Stocke les URI de l’utilisateur, de conférence et de téléphone utilisés dans des sessions audio et vidéo.  <br/> |
|[Table Endpoint](endpoint.md) <br/> |Stocke le nom de domaine complet (FQDN) de l’ordinateur des systèmes d’extrémité participant à des sessions audio et vidéo.  <br/> |
|[Table Pool](pool.md) <br/> |Stocke les noms des pools auxquels appartiennent les données de mesure.  <br/> |
|[Table Device](device.md) <br/> |Stocke les appareils de capture et les appareils de rendu qui sont utilisés dans les appels audio/vidéo.  <br/> |
|[Table DeviceDriver](devicedriver.md) <br/> |Stocke le pilote de l’appareil de capture et de l’appareil de rendu qui sont utilisés dans les appels audio/vidéo.  <br/> |
|[Table Conference](conference.md) <br/> |Stocke les URI de conférence pour les scénarios de conférence ou le DialogID pour d’autres scénarios.  <br/> |
|[Table SessionCorrelation](sessioncorrelation.md) <br/> |Stocke le CorrelationID pour les appels PSTN.  <br/> |
|[Table PayloadDescription](payloaddescription.md) <br/> |Stocke le Codec utilisé dans les appels audio/vidéo.  <br/> |
|[Table AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Stocke la source de la bande passante utilisée dans les appels audio/vidéo.  <br/> |
|[Table MacAddress](macaddress.md) <br/> |Stocke l’adresse MAC des systèmes d’extrémité participant à des sessions audio et vidéo.  <br/> |
|[Table dialog](dialog.md) <br/> |Stocke l’ID de dialogue des sessions audio et vidéo.  <br/> |
|[Table Region](region.md) <br/> |Stocke la région du réseau définie dans le paramètre NCS.  <br/> |
|[Table UserSite](usersite.md) <br/> |Stocke le site réseau défini dans le paramètre NCS.  <br/> |
|[Table Subnet](subnet.md) <br/> |Stocke le sous-réseau défini dans le paramètre NCS.  <br/> |
|[Table MonitoredRegionLink](monitoredregionlink.md) <br/> |Stocke le lien de région défini dans le paramètre NCS.  <br/> |
|[Table MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Stocke les liens du site réseau définis dans le paramètre NCS.  <br/> |
|[Table EndpointSubnet](endpointsubnet.md) <br/> |Stocke le sous-réseau du système d’extrémité participant à une session audio et vidéo.  <br/> |
|[Table Server](server.md) <br/> |Stocke le nom complet ou l’adresse IP du serveur via lequel passe le média.  <br/> |
   
**Tableaux de données de mesure**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingStream](appsharingstream.md) <br/> |Stocke les mesures de qualité de l’expérience de la transmission réseau utilisée pour le partage d’application. Mesures de qualité de l’expérience de la transmission réseau utilisée pour le partage d’application.  <br/> |
|[Table Session](session.md) <br/> |Stocke les informations globales sur une session audio ou audio/vidéo. Une session est définie en tant que dialogue SIP audio ou vidéo entre deux points d’extrémité.  <br/> |
|[Table MediaLine](medialine-0.md) <br/> |Stocke les informations sur chaque ligne de média dans une session. Une ligne de média est une collection d’un ou plusieurs flux audio et vidéo. Généralement, une ligne de média unique aura deux flux, soit audio ou vidéo.  <br/> |
|[Table AudioStream](audiostream.md) <br/> |Stocke les mesures de qualité du média audio pour chaque flux audio dans la ligne de média.  <br/> |
|[Table AudioSignal](audiosignal.md) <br/> |Stocke les mesures de qualité du média audio dans la ligne de média, notamment les mesures de suppression d’écho et de réglage de puissance automatique.  <br/> |
|[Table VideoStream](videostream.md) <br/> |Stocke les mesures de qualité du média vidéo pour chaque flux audio dans la ligne de média.  <br/> |
|[Table AudioClientEvent](audioclientevent.md) <br/> |Stocke les mesures de qualité du média audio collectées à partir de l’événement client.  <br/> |
|[Table VideoClientEvent](videoclientevent.md) <br/> |Stocke les mesures de qualité du média vidéo collectées à partir de l’événement client.  <br/> |
|**Table DiagnosticData** <br/> |Stocke les données de diagnostic qui sont destinées à un usage interne exclusivement.  <br/> |
   
**Tables des données de synthèse**

|**Table**|**Description**|
|:-----|:-----|
|**Table ServerSummary** <br/> |Stocke les données de synthèse pour les serveurs, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).  <br/> |
|**Table UserSummary** <br/> |Stocke les données de synthèse pour les utilisateurs, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).  <br/> |
|**Table CallTypeSummary** <br/> |Stocke les données de synthèse pour les types d’appel, ces données étant essentiellement utilisées pour les rapports de qualité de l’expérience (QoE).  <br/> |
   
**Tables à utilisation interne par le serveur de surveillance**

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**Table FrontEnd** <br/> |À usage interne uniquement.  <br/> |
|**Table Task** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**MetricsThreshold** <br/> |À usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |À usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**TimeZones** <br/> |À usage interne uniquement.  <br/> |
|**Table CallSummary** <br/> |À usage interne uniquement.  <br/> |
|**Table DeviceCallSumary** <br/> |À usage interne uniquement.  <br/> |
|**Table Tenant** <br/> |À usage interne uniquement.  <br/> |
|**VideoCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
|**ASCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
   

