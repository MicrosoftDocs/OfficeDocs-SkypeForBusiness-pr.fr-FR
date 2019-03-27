---
title: Liste des tables des détails des appels dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Les détails des appels (CDR) le schéma de base de données comprend les tables suivantes.
ms.openlocfilehash: 977c48b58c5b1d1c0f21fbac07a28ec6efb0bfd6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881199"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste des tables des détails des appels dans Skype pour Business Server 2015
 
Les détails des appels (CDR) le schéma de base de données comprend les tables suivantes. 
  
## <a name="static-tables"></a>Tables statiques

|**Table**|**Description**|
|:-----|:-----|
|[Table CallPriorities dans Skype pour Business Server 2015](callpriorities.md) <br/> |Stocke la liste des priorités d’appel possibles, telles que les appels, urgents, normaux, non urgents et bien plus encore.  <br/> |
|[Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015](conferencejointimethresholds.md) <br/> |Stocke les limites de classification utilisés par le rapport de synthèse de conférence participer à temps.  <br/> |
|[Table DeRegisterType dans Skype pour Business Server 2015](deregistertype.md) <br/> |Stocke la liste des utilisateurs de désinscription des raisons, tel que « initiative, du client » l’inscription « à expiration », « blocage du client » et bien plus encore.  <br/> |
|[Table MediaList](medialist.md) <br/> |Stocke la liste des types de médias qui peuvent générer des entrées dans la base de données (par exemple, messagerie instantanée, audio, vidéo et transfert de fichiers).  <br/> |
|[Table PurgeSettings](purgesettings.md) <br/> |Stocke des informations qui indiquent si (et quand) les appels enregistrements des détails des seront automatiquement supprimés de la base de données des détails des appels obsolètes.  <br/> |
|[Table Roles](roles.md) <br/> |Stocke la liste des rôles possibles pour les conférences (par exemple, participant et présentateur).  <br/> |
|[Table SIPResponseMetaData](sipresponsemetadata.md) <br/> |Stocke une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes.  <br/> |
   
## <a name="supporting-tables"></a>Tables de prise en charge

|**Table**|**Description**|
|:-----|:-----|
|[Table ClientVersions dans Skype pour Business Server 2015](clientversions.md) <br/> |Stocke les clients (les deux clients type et numéro de version) de chaque client impliqué dans un appel comprenant des informations capturées dans cette base de données.  <br/> |
|[Table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) <br/> |Stocke une liste de Conferenceuri qui sont utilisés dans les conférences des appels associés.  <br/> |
|[Table ContentTypes dans Skype pour Business Server 2015](contenttypes.md) <br/> |Stocke une liste de types de contenu de protocole SIP (Session Initiation) qui sont utilisés dans les appels d’égal à égal et les téléconférences.  <br/> |
|[Table Devices dans Skype pour Business Server 2015](devices.md) <br/> |Stocke une liste de périphériques, notamment leur fabricant, version du matériel et adresse MAC.  <br/> |
|[Boîtes de dialogue tableau Skype pour Business Server 2015](dialogs.md) <br/> |Stocke des informations sur l’ID de la boîte de dialogue pour chaque session dans la base de données.  <br/> |
|[Table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) <br/> |Stocke une liste des serveurs de périphérie qui sont utilisés pour les appels externes.  <br/> |
|[Table Gateways dans Skype pour Business Server 2015](gateways.md) <br/> |Stocke une liste de passerelles qui sont utilisés pour la voix sur IP (VoIP) appels.  <br/> |
|[Table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) <br/> |Stocke une liste de versions matérielles d’appareils (téléphone de bureau).  <br/> |
|[Table Manufacturers dans Skype pour Business Server 2015](manufacturers.md) <br/> |Stocke une liste de fabricants et d’appareils (téléphone de bureau).  <br/> |
|[Table Mcus dans Skype pour Business Server 2015](mcus.md) <br/> |Stocke des informations sur les différents A / V Conferencing Servers et leurs URI.  <br/> |
|[Table MediationServers](mediationservers.md) <br/> |Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.  <br/> |
|[Table !Phones](phones.md) <br/> |Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivées ou appel dont les détails ont été enregistrés.  <br/> |
|[Table Pools](pools.md) <br/> |Stocke les noms du pool dans les messages instantanés sont capturés messages.  <br/> |
|[Table Servers](servers.md) <br/> |Stocke le nom des serveurs impliqués dans les appels.  <br/> |
|[Table Tenants](tenants.md) <br/> |Stocke les clients pris en charge par le déploiement actuel. Il certains clients intégrées pour utilisateur entreprise, utilisateur fédéré, utilisateurs de connectivité de messagerie instantanée publics et les utilisateurs anonymes.  <br/> |
|[Table UserAgentDef](useragentdef.md) <br/> |Mappe les identificateurs d’agents utilisateurs aux noms descriptifs des agents.  <br/> |
|[Table Users](users.md) <br/> |Stocke l’utilisateur URI des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.  <br/> |
|[Table UserStatistics](userstatistics.md) <br/> |Stocke des informations sur l’utilisation d’un utilisateur individuel du système.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tables spécifiques aux enregistrements des détails des appels de conférence

|**Table**|**Description**|
|:-----|:-----|
|[Tableau des conférences dans Skype pour Business Server 2015](conferences.md) <br/> |Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment le ConferenceURI et l’heure de début et de fin.  <br/> |
|[Table ConferenceSessionDetails dans Skype pour Business Server 2015](conferencesessiondetails-0.md) <br/> |Stocke des informations sur chaque session de conférence basée sur SIP, y compris de début et heure de fin, ID de l’utilisateur, code de réponse et ID de diagnostic pour chaque session.  <br/> |
|[Table FocusJoinsAndLeaves dans Skype pour Business Server 2015](focusjoinsandleaves.md) <br/> |Stocke des informations sur la conférence arrivée et de départ, y compris le rôle des utilisateurs et la version du client.  <br/> |
|[Table McuJoinsAndLeaves dans Skype pour Business Server 2015](mcujoinsandleaves.md) <br/> |Stocke des informations sur A / V Conferencing Servers qui participent à une conférence et l’utilisateur les heures de départ et joindre.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tables des Messages dans les conférences par messagerie instantanée

|**Table**|**Description**|
|:-----|:-----|
|[Table ConferenceMessageCount dans Skype pour Business Server 2015](conferencemessagecount.md) <br/> |Pour chaque conférence par messagerie instantanée, stocke le nombre de messages qui ont été envoyés par chaque utilisateur.  <br/> |
|[Table IMReportSummary dans Skype pour Business Server 2015](imreportsummary.md) <br/> |Fournit un rapport global sur les sessions ouvertes dans une organisation de messagerie instantanée.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tables des Sessions d’égal à égal

|**Table**|**Description**|
|:-----|:-----|
|[Table SessionDetails](sessiondetails.md) <br/> |Stocke des informations sur toutes les sessions d’égal à égal, notamment le début et heure de fin, ID de l’utilisateur, code de réponse et nombre de messages pour chaque utilisateur.  <br/> |
|[Table FileTransfers dans Skype pour Business Server 2015](filetransfers-0.md) <br/> |Stocke des informations sur le transfert de fichiers sessions, y compris les fichiers de nom et de résultat (accepté, rejeté ou annulé).  <br/> |
|[Table Media](media.md) <br/> |Stocke des informations sur les différents types de médias impliqués dans les sessions d’égal à égal.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Table des détails des appels VoIP

|**Table**|**Description**|
|:-----|:-----|
|[Table VoipDetails](voipdetails-0.md) <br/> |Pour chaque appel VoIP/RTC deux, stocke les informations relatives à l’appel, telles que le téléphone de l’ID de VoIP, passerelle utilisée et les tiers déconnecté. Fait référence à la [table SessionDetails](sessiondetails.md) pour les heures de début/fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> Si une partie sur un appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans l’appel, un enregistrement sera créé dans ce tableau. Informations sur les appels VoIP/VoIP ne pas impliquant un téléphone de réseau téléphonique commuté est capturé dans la [table SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Table d’audit d’appel E9-1-1

|**Table**|**Description**|
|:-----|:-----|
|[Table Locations dans Skype pour Business Server 2015](locations.md) <br/> |Pour chaque appel d’urgence, par exemple un appel Enhanced 9-1-1 (E9-1-1), stocke des informations d’emplacement sur l’appel. Fait référence à la [table SessionDetails](sessiondetails.md) pour les heures de début/fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> Cette table contient uniquement le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour d’autres informations détaillées sur l’appel. 
  
## <a name="tables-for-troubleshooting"></a>Tables de dépannage

|**Table**|**Description**|
|:-----|:-----|
|[Table de l’application dans Skype pour Business Server 2015](application.md) <br/> |Stocke des informations sur les divers processus Skype pour Business Server 2015 qui sont impliqués dans le routage et les connexions.  <br/> |
|[Table CallType dans Skype pour Business Server 2015](calltype.md) <br/> |Stocke des informations sur les types de l’appel, par exemple, « audio », « Messagerie instantanée », « audio et vidéo » et « partage d’application ».  <br/> |
|[Table ErrorCategory dans Skype pour Business Server 2015](errorcategory.md) <br/> |Stocke le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015.  <br/> |
|[Table ErrorDef dans Skype pour Business Server 2015](errordef.md) <br/> |Stocke des informations sur les types d’erreurs et leurs définitions.  <br/> |
|[Table ErrorReport dans Skype pour Business Server 2015](errorreport.md) <br/> |Stocke des informations sur les erreurs qui se sont produites.  <br/> |
|[Table ProgressReport](progressreport.md) <br/> |Stocke des informations sur les rapports de progression des différentes étapes impliquées dans Skype pour les processus métiers Server 2015.  <br/> |
   
Les tableaux dans la liste suivante sont utilisés en interne par Skype pour Business Server 2015. Les détails ne sont pas décrites dans ce document.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tables pour une utilisation interne par Lync Server

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**Table FrontEnd** <br/> |À usage interne uniquement.  <br/> |
|**Table MSMQProcessing** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Table syndicators** <br/> |À usage interne uniquement.  <br/> |
|**Table SyndicatorsTenantMap** <br/> |À usage interne uniquement.  <br/> |
|**Table des tâches** <br/> |À usage interne uniquement.  <br/> |
|**UserStatistics** <br/> |À usage interne uniquement.  <br/> |
|**UsageSummary_UQ** <br/> |À usage interne uniquement.  <br/> |
|**UsageSummary** <br/> |À usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |À usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Fuseaux horaires** <br/> |À usage interne uniquement.  <br/> |
|**FailureSummary_UQ** <br/> |À usage interne uniquement.  <br/> |
|**FailureSummary** <br/> |À usage interne uniquement.  <br/> |
|**ServerSummary** <br/> |À usage interne uniquement.  <br/> |
|**MsDiagMetaData** <br/> |À usage interne uniquement.  <br/> |
   

