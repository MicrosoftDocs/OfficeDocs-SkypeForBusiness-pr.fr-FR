---
title: Liste des tables QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Le schéma de base de données se compose des tables suivantes.
ms.openlocfilehash: ba6f439d97692a40fd485a2c550da079092d7365
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294914"
---
# <a name="list-of-qoe-tables"></a>Liste des tables QoE
 
Le schéma de base de données se compose des tables suivantes. 
  
**Tableaux pris en charge**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application.  <br/> |
|[Table CodecDescription](codecdescription.md) <br/> |Mappe des identificateurs de codec uniques au codec correspondant.  <br/> |
|[Table IPAddress](ipaddress.md) <br/> |Mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation.  <br/> |
|[Table NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation.  <br/> |
|[Table PurgeSettings](purgesettings-qoe.md) <br/> |Stocke les informations qui spécifient si (et quand) les enregistrements de qualité d’expérimentation obsolètes seront automatiquement supprimés de la base de données QoE.  <br/> |
|[Table TraceRoute](traceroute.md) <br/> |Stocke les informations d’acheminement des appels.  <br/> |
|[Table UserAgentDef](useragentdef-qoe.md) <br/> |Mappe des identificateurs d’agent utilisateur aux noms descriptifs de l’agent.  <br/> |
|[Table VideoMetricsThreshold](videometricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec les appels vidéo.  <br/> |
|[Table UserAgent](useragent.md) <br/> |Stocke les chaînes d’agent utilisateur SIP (Session Initiation Protocol) et les types UA utilisés dans les sessions audio et vidéo.  <br/> |
|[Table User](user-0.md) <br/> |Stocke les URI d’utilisateur, de conférence et de téléphone utilisés dans les sessions audio et vidéo.  <br/> |
|[Table Endpoint](endpoint.md) <br/> |Stocke les noms de domaine complets des points de terminaison participant aux sessions audio et vidéo.  <br/> |
|[Table Pool](pool.md) <br/> |Stocke les noms des pools auxquels les données de mesure appartiennent.  <br/> |
|[Table Device](device.md) <br/> |Stocker des périphériques de capture et des appareils de rendu qui sont utilisés dans un appel audio/vidéo.  <br/> |
|[Table DeviceDriver](devicedriver.md) <br/> |Stocke le pilote pour l’appareil de capture et l’appareil de rendu utilisé pour les appels audio/vidéo.  <br/> |
|[Table Conference](conference.md) <br/> |Stocke les URI de conférence pour les scénarios de conférence ou DialogID pour d’autres scénarios.  <br/> |
|[Table SessionCorrelation](sessioncorrelation.md) <br/> |Stocke l’CorrelationID pour les appels PSTN.  <br/> |
|[Table PayloadDescription](payloaddescription.md) <br/> |Stocke le codec utilisé pour les appels audio/vidéo.  <br/> |
|[Table AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Stocke la source de bande passante utilisée dans les appels audio/vidéo.  <br/> |
|[Table MacAddress](macaddress.md) <br/> |Stocke l’adresse MAC des points de terminaison qui participent à des sessions audio et vidéo.  <br/> |
|[Table Dialog](dialog.md) <br/> |Stocke l’ID de boîte de dialogue des sessions audio et vidéo.  <br/> |
|[Table Region](region.md) <br/> |Stocke la région réseau définie dans le paramètre NC.  <br/> |
|[Table UserSite](usersite.md) <br/> |Stocke le site réseau défini dans le paramètre NC.  <br/> |
|[Table Subnet](subnet.md) <br/> |Stocke le sous-réseau défini dans le paramètre NC.  <br/> |
|[Table MonitoredRegionLink](monitoredregionlink.md) <br/> |Stocke le lien région défini dans le paramètre NC.  <br/> |
|[Table MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Stocke les liens de site réseau définis dans le paramètre NC.  <br/> |
|[Table EndpointSubnet](endpointsubnet.md) <br/> |Stocke le sous-réseau du point de terminaison participant à une session audio et vidéo.  <br/> |
|[Table Server](server.md) <br/> |Stocke le nom complet ou l’adresse IP du serveur sur lequel le média est transmis.  <br/> |
   
**Tableaux pour les données de mesure**

|**Table**|**Description**|
|:-----|:-----|
|[Table AppSharingStream](appsharingstream.md) <br/> |Stocke les métriques de qualité de l’utilisation pour les flux réseau utilisés pour le partage d’application. Métrique de qualité de l’utilisation des flux réseau utilisés pour le partage d’application.  <br/> |
|[Table Session](session.md) <br/> |Stocke des informations globales sur une session audio ou vidéo. Une session est définie sous forme de boîte de dialogue SIP audio ou vidéo entre deux points de terminaison.  <br/> |
|[Table MediaLine](medialine-0.md) <br/> |Stocke les informations relatives à chaque ligne multimédia dans une session. Une ligne de média est une collection d’un ou de plusieurs flux audio et vidéo. En règle générale, une seule ligne multimédia comporte deux flux, audio ou vidéo.  <br/> |
|[Table AudioStream](audiostream.md) <br/> |Stocke les métriques de qualité de média audio de chaque flux audio dans la ligne multimédia.  <br/> |
|[Table AudioSignal](audiosignal.md) <br/> |Stocke les mesures de qualité de média audio dans la ligne multimédia. Cela inclut les métriques de suppression de l’écho acoustique et de contrôle de gain automatique.  <br/> |
|[Table VideoStream](videostream.md) <br/> |Stocke les métriques de qualité de média vidéo pour chaque flux audio dans la ligne multimédia.  <br/> |
|[Table AudioClientEvent](audioclientevent.md) <br/> |Stocke les métriques de qualité de média audio collectées à partir de l’événement client.  <br/> |
|[Table VideoClientEvent](videoclientevent.md) <br/> |Stocke les métriques de qualité de média vidéo collectées à partir de l’événement client.  <br/> |
|**Table DiagnosticData** <br/> |Stocke les données de diagnostic pour un usage interne uniquement.  <br/> |
   
**Tableaux pour les données récapitulatives**

|**Table**|**Description**|
|:-----|:-----|
|**Table ServerSummary** <br/> |Stocke les données de synthèse pour les serveurs, ces données sont utilisées pour le rapport qualité de l’utilisation (QoE) uniquement.  <br/> |
|**Table UserSummary** <br/> |Stocke les données de synthèse des utilisateurs, ces données sont utilisées uniquement pour le rapport QoE.  <br/> |
|**Table CallTypeSummary** <br/> |Données de synthèse du magasin pour les types d’appel, ces données sont utilisées uniquement pour le rapport QoE.  <br/> |
   
**Tables pour une utilisation interne par le serveur de surveillance**

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Pour un usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table frontale** <br/> |Pour un usage interne uniquement.  <br/> |
|**Tableau de tâches** <br/> |Pour un usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |Pour un usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |Pour un usage interne uniquement.  <br/> |
|**MetricsThreshold** <br/> |Pour un usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |Pour un usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |Pour un usage interne uniquement.  <br/> |
|**Fuseau** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table CallSummary** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table DeviceCallSumary** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table de locataire** <br/> |Pour un usage interne uniquement.  <br/> |
|**VideoCallSummaryTable** <br/> |Pour un usage interne uniquement.  <br/> |
|**ASCallSummaryTable** <br/> |Pour un usage interne uniquement.  <br/> |
   

