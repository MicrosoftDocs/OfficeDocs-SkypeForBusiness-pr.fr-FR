---
title: Liste des tables QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Le schéma de base de données se compose des tables suivantes.
ms.openlocfilehash: 5f8957bfa4bbe2da75073082132468bff748c712
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-qoe-tables"></a>Liste des tables QoE
 
Le schéma de base de données se compose des tables suivantes. 
  
**Prise en charge des Tables**

|**Table**|**Description**|
|:-----|:-----|
|[Table de AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les métriques de qualité utilisés avec le partage de l’application.  <br/> |
|[Table de CodecDescription](codecdescription.md) <br/> |Mappe les identificateurs uniques de codec à leur codec correspondant.  <br/> |
|[Table d’adresse IP](ipaddress.md) <br/> |Mappe les adresses IP pour les identificateurs uniques d’adresse IP utilisées ailleurs dans la base de données de qualité.  <br/> |
|[Table de NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappe les types de connexion réseau pour les identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité.  <br/> |
|[Table de PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Stocke des informations indiquant si (et quand) obsolète de bonne qualité enregistrements seront automatiquement supprimés de la base de données QoE.  <br/> |
|[Table de détermination d’itinéraire](traceroute.md) <br/> |Stocke les informations pour les appels de routage.  <br/> |
|[Table de UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mappe les identificateurs de l’agent utilisateur à noms descriptifs de l’agent.  <br/> |
|[Table de VideoMetricsThreshold](videometricsthreshold.md) <br/> |Stocke les valeurs optimales et acceptables pour les métriques de qualité utilisées avec les appels vidéo.  <br/> |
|[Table de UserAgent](useragent.md) <br/> |Stocke les chaînes de l’Agent d’utilisateur Session Initiation Protocol (SIP) (UA) et les types UA utilisées dans les sessions audio et vidéo.  <br/> |
|[Table utilisateur](user-0.md) <br/> |Utilisateur de banques, de conférence et URI de téléphone utilisées dans les sessions audio et vidéo.  <br/> |
|[Table de point de terminaison](endpoint.md) <br/> |Stocke des noms d’ordinateur de nom de domaine complet de points de terminaison impliqués dans les sessions audio et vidéo.  <br/> |
|[Table de pool](pool.md) <br/> |Stocke les noms des pools pour les mesures de données appartient.  <br/> |
|[Table de périphériques](device.md) <br/> |Banques de périphériques de capture et afficher les périphériques qui sont utilisés dans des appels audio/vidéo.  <br/> |
|[Table de DeviceDriver](devicedriver.md) <br/> |Stocke le pilote pour le périphérique de capture et le périphérique de rendu qui sont utilisés dans les appels audio et vidéo.  <br/> |
|[Table de conférence](conference.md) <br/> |Stocke les URI de conférence pour les scénarios de conférence ou DialogID pour d’autres scénarios.  <br/> |
|[Table de SessionCorrelation](sessioncorrelation.md) <br/> |Stocke les ID de corrélation pour les appels RTPC.  <br/> |
|[Table de PayloadDescription](payloaddescription.md) <br/> |Stocke le Codec utilisé dans les appels audio et vidéo.  <br/> |
|[Table de AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Stocke la source de la bande passante utilisée dans les appels audio et vidéo.  <br/> |
|[Table d’adresse MAC](macaddress.md) <br/> |Stocke l’adresse MAC des points de terminaison impliqués dans les sessions audio et vidéo.  <br/> |
|[Table de la boîte de dialogue](dialog.md) <br/> |Enregistre l’ID de la boîte de dialogue des sessions audio et vidéo.  <br/> |
|[Table de région](region.md) <br/> |Stocke la région réseau définie dans le paramètre de contextes de nommage.  <br/> |
|[Table de UserSite](usersite.md) <br/> |Stocke le site réseau défini dans le paramètre de contextes de nommage.  <br/> |
|[Table de sous-réseau](subnet.md) <br/> |Stocke le sous-réseau défini dans le paramètre de contextes de nommage.  <br/> |
|[Table de MonitoredRegionLink](monitoredregionlink.md) <br/> |Stocke le lien de la région défini dans le paramètre de contextes de nommage.  <br/> |
|[Table de MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Stocke les liens de site de réseau définis dans le paramètre de contextes de nommage.  <br/> |
|[Table de EndpointSubnet](endpointsubnet.md) <br/> |Stocke le sous-réseau du point de terminaison participant à une session audio et vidéo.  <br/> |
|[Table de serveur](server.md) <br/> |Stocke le nom de domaine complet ou l’adresse IP du serveur que média traverse.  <br/> |
   
**Tables pour les données de métrique**

|**Table**|**Description**|
|:-----|:-----|
|[Table de AppSharingStream](appsharingstream.md) <br/> |Stocke les mesures de qualité pour les flux de réseau utilisés pour le partage d’application. Qualité des métriques d’expérience pour les flux de réseau utilisés pour le partage d’application.  <br/> |
|[Table de la session](session.md) <br/> |Stocke des informations générales sur une session audio ou audio/vidéo. Une session est définie comme une boîte de dialogue SIP audio ou vidéo entre deux points de terminaison.  <br/> |
|[Table de MediaLine](medialine-0.md) <br/> |Stocke des informations sur chaque ligne de media dans une session. Une ligne de support est une collection d’un ou plusieurs flux audio et vidéo. En général, une ligne de support unique possède deux flux, audio ou vidéo.  <br/> |
|[Table de AudioStream](audiostream.md) <br/> |Stocke les mesures de la qualité audio de média pour chaque flux de données audio dans la ligne de media.  <br/> |
|[Table de AudioSignal](audiosignal.md) <br/> |Stocke les mesures de la qualité audio media dans la ligne de media. Cela inclut l’annulation de l’écho acoustique (AEC) et les mesures de contrôle automatique de gain.  <br/> |
|[Table de VideoStream](videostream.md) <br/> |Stocke les mesures de la qualité vidéo pour chaque flux de données audio dans la ligne de media.  <br/> |
|[Table de AudioClientEvent](audioclientevent.md) <br/> |Mesures de qualité du média audio magasins collectées à partir de l’événement client.  <br/> |
|[Table de VideoClientEvent](videoclientevent.md) <br/> |Mesures de la qualité vidéo magasins collectées à partir de l’événement client.  <br/> |
|**Table de DiagnosticData** <br/> |Stocke les données de diagnostic qui est à usage interne uniquement.  <br/> |
   
**Tables pour les données de synthèse**

|**Table**|**Description**|
|:-----|:-----|
|**Table de ServerSummary** <br/> |Stocke les données de synthèse pour les serveurs, ces données sont utilisées pour la qualité d’expérience (QoE) reporting uniquement.  <br/> |
|**Table de UserSummary** <br/> |Stocke les données de synthèse pour les utilisateurs, ces données sont utilisées pour QoE reporting uniquement.  <br/> |
|**Table de CallTypeSummary** <br/> |Magasin des données de synthèse pour les types d’appel, ces données sont utilisées pour QoE reporting uniquement.  <br/> |
   
**Tables pour une utilisation interne par le contrôle serveur**

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**Tableau de la partie frontale** <br/> |À usage interne uniquement.  <br/> |
|**Table des tâches** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**MetricsThreshold** <br/> |À usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |À usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Fuseaux horaires** <br/> |À usage interne uniquement.  <br/> |
|**Table de CallSummary** <br/> |À usage interne uniquement.  <br/> |
|**Table de DeviceCallSumary** <br/> |À usage interne uniquement.  <br/> |
|**Table des clients** <br/> |À usage interne uniquement.  <br/> |
|**VideoCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
|**ASCallSummaryTable** <br/> |À usage interne uniquement.  <br/> |
   

