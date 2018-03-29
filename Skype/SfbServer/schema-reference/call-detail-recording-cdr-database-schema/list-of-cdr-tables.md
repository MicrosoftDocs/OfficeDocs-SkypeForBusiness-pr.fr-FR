---
title: Liste des tables de CD-r dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Les détails de l’appel d’enregistrement du schéma de base de données (CDR) se compose des tables suivantes.
ms.openlocfilehash: 7e224b8170ec078cafaec2fe3cbf4cf9819eba41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste des tables de CD-r dans Skype pour Business Server 2015
 
Les détails de l’appel d’enregistrement du schéma de base de données (CDR) se compose des tables suivantes. 
  
## <a name="static-tables"></a>Tables statiques

|**Table**|**Description**|
|:-----|:-----|
|[Table CallPriorities dans Skype pour Business Server 2015](callpriorities.md) <br/> |Stocke la liste des priorités d’appel possibles, tels que de la situation d’urgence, urgente, normale, non urgent et bien plus encore.  <br/> |
|[Table ConferenceJoinTimeThresholds dans Skype pour Business Server 2015](conferencejointimethresholds.md) <br/> |Stocke les limites de classification utilisés par le rapport de résumé de conférence joindre le temps.  <br/> |
|[Table DeRegisterType dans Skype pour Business Server 2015](deregistertype.md) <br/> |Stocke la liste des utilisateurs possible annuler l’enregistrement des raisons, par exemple « client lancée, » « enregistrement expiré, » « blocage du client » et bien plus encore.  <br/> |
|[Table de mediaList](medialist.md) <br/> |Stocke la liste des types de médias qui peut générer des entrées de la base de données (par exemple, messagerie instantanée, audio, vidéo et transfert de fichiers).  <br/> |
|[Table de PurgeSettings](purgesettings.md) <br/> |Stocke des informations indiquant si (et quand) obsolète appel seront automatiquement supprimés les enregistrements de détail à partir de la base de données de CD-r.  <br/> |
|[Table de rôles](roles.md) <br/> |Stocke la liste des rôles de conférence possible (par exemple, présentateur ou participant).  <br/> |
|[Table de SIPResponseMetaData](sipresponsemetadata.md) <br/> |Stocke une liste de codes de réponse SIP et la classification et la définition de chacun de ces codes.  <br/> |
   
## <a name="supporting-tables"></a>Prise en charge des Tables

|**Table**|**Description**|
|:-----|:-----|
|[Table ClientVersions dans Skype pour Business Server 2015](clientversions.md) <br/> |Stocke les clients (les deux client type et numéro de version) de chaque client impliqué dans un appel avec les informations capturées dans cette base de données.  <br/> |
|[Table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) <br/> |Stocke une liste des ConferenceURIs qui sont utilisées dans une conférence des appels associés.  <br/> |
|[Tableau de types de contenus dans Skype pour Business Server 2015](contenttypes.md) <br/> |Stocke une liste des types de contenu de Session Initiation Protocol (SIP) qui sont utilisés dans les appels de peer-to-peer et de conférences téléphoniques.  <br/> |
|[Table de périphériques dans Skype pour Business Server 2015](devices.md) <br/> |Stocke une liste de périphériques, y compris leur fabricant, version du matériel et adresse MAC.  <br/> |
|[Table de boîtes de dialogue dans Skype pour Business Server 2015](dialogs.md) <br/> |Stocke des informations sur l’ID de la boîte de dialogue pour chaque session dans la base de données.  <br/> |
|[Table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) <br/> |Stocke une liste des serveurs de périphérie qui sont utilisés pour les appels externes.  <br/> |
|[Table de passerelles dans Skype pour Business Server 2015](gateways.md) <br/> |Stocke une liste de passerelles qui sont utilisés pour la voix sur IP (VoIP) appels.  <br/> |
|[Table HardwareVersions dans Skype pour Business Server 2015](hardwareversions.md) <br/> |Stocke une liste des versions de matériel des périphériques (téléphone de bureau).  <br/> |
|[Table de fabricants dans Skype pour Business Server 2015](manufacturers.md) <br/> |Stocke une liste de fabricants de périphériques (téléphone de bureau).  <br/> |
|[Table de MCU dans Skype pour Business Server 2015](mcus.md) <br/> |Stocke des informations sur les diverses A / V Conferencing serveurs et leurs URI.  <br/> |
|[Table de MediationServers](mediationservers.md) <br/> |Stocke une liste de serveurs de médiation sont utilisés pour des appels VoIP.  <br/> |
|[Table de téléphones](phones.md) <br/> |Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivées ou appel dont les détails ont été enregistrés.  <br/> |
|[Table de regroupements](pools.md) <br/> |Stocke le nom du pool sur la messagerie instantanée, les messages sont capturés.  <br/> |
|[Tableau des serveurs](servers.md) <br/> |Stocke le nom des serveurs impliqués dans les appels.  <br/> |
|[Table de locataires](tenants.md) <br/> |Stocke les locataires pris en charge par le déploiement actuel. Il certains locataires de génération d’entreprise utilisateur, fédérés utilisateur, utilisateur de connectivité de messagerie instantanée publique et les utilisateurs anonymes.  <br/> |
|[Table de UserAgentDef](useragentdef.md) <br/> |Mappe les identificateurs de l’agent utilisateur à noms descriptifs de l’agent.  <br/> |
|[Table des utilisateurs](users.md) <br/> |Stocke l’utilisateur URI d’utilisateurs qui ont participé aux sessions enregistrées ou archivé dans cette base de données.  <br/> |
|[Table de UserStatistics](userstatistics.md) <br/> |Stocke les informations relatives à l’utilisation d’un utilisateur individuel du système.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Spécifique de tables aux enregistrements de conférence CDR

|**Table**|**Description**|
|:-----|:-----|
|[Table des conférences dans Skype pour Business Server 2015](conferences.md) <br/> |Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment ConferenceURI et l’heure de début et de fin.  <br/> |
|[Table ConferenceSessionDetails dans Skype pour Business Server 2015](conferencesessiondetails-0.md) <br/> |Stocke des informations sur chaque session de la conférence de basée sur SIP, y compris début et heure de fin, ID utilisateur, code de réponse et code de diagnostic pour chaque session.  <br/> |
|[Table FocusJoinsAndLeaves dans Skype pour Business Server 2015](focusjoinsandleaves.md) <br/> |Stocke des informations sur la conférence joint et quitte, y compris le rôle des utilisateurs et la version du client.  <br/> |
|[Table McuJoinsAndLeaves dans Skype pour Business Server 2015](mcujoinsandleaves.md) <br/> |Stocke des informations sur le A / V Conferencing serveurs qui participent à une conférence et l’utilisateur joindre et laissez du temps.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tables des Messages dans les conférences par messagerie instantanée

|**Table**|**Description**|
|:-----|:-----|
|[Table ConferenceMessageCount dans Skype pour Business Server 2015](conferencemessagecount.md) <br/> |Pour chaque conférence par messagerie instantanée, enregistre le nombre de messages qui ont été envoyés par chaque utilisateur.  <br/> |
|[Table IMReportSummary dans Skype pour Business Server 2015](imreportsummary.md) <br/> |Fournit un rapport global sur les sessions dans une organisation de messagerie instantanée.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tables pour les Sessions d’homologue à homologue

|**Table**|**Description**|
|:-----|:-----|
|[Table de SessionDetails](sessiondetails.md) <br/> |Stocke les informations relatives à chaque session peer-to-peer, y compris début et heure de fin, ID utilisateur, code de réponse et nombre de messages pour chaque utilisateur.  <br/> |
|[Table FileTransfers dans Skype pour Business Server 2015](filetransfers-0.md) <br/> |Stocke des informations sur le transfert de fichier sessions, y compris les fichiers nom et entraînent (accepté, rejeté ou annulé).  <br/> |
|[Table de supports](media.md) <br/> |Stocke des informations sur les différents types de supports impliqués dans les sessions de peer-to-peer.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tableau de détails d’appel VoIP

|**Table**|**Description**|
|:-----|:-----|
|[Table de VoipDetails](voipdetails-0.md) <br/> |Pour chaque appel VoIP/RTC de deux tiers, stocke les informations relatives à l’appel, par exemple l’ID de VoIP téléphone, passerelle utilisée et quelle partie est déconnecté. Fait référence à la [table de SessionDetails](sessiondetails.md) pour les heures de début/fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> Si une partie sur un appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans l’appel, un enregistrement sera créé dans cette table. Informations sur les appels VoIP/VoIP n’impliquant ne pas un téléphone de réseau téléphonique public commuté est capturée dans la [table de SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Table d’audit E9-1-1 appel

|**Table**|**Description**|
|:-----|:-----|
|[Tableau des emplacements dans Skype pour Business Server 2015](locations.md) <br/> |Pour chaque appel d’urgence, par exemple un appel Enhanced 9-1-1 (E9-1-1), stocke les informations d’emplacement concernant l’appel. Fait référence à la [table de SessionDetails](sessiondetails.md) pour les heures de début/fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> Ce tableau contient uniquement le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table de SessionDetails d’autres informations détaillées concernant l’appel. 
  
## <a name="tables-for-troubleshooting"></a>Tables pour le dépannage

|**Table**|**Description**|
|:-----|:-----|
|[Table d’application dans Skype pour Business Server 2015](application.md) <br/> |Stocke des informations sur les divers processus dans Skype pour Business Server 2015 qui sont impliqués dans le routage et les connexions.  <br/> |
|[Table CallType dans Skype pour Business Server 2015](calltype.md) <br/> |Stocke des informations sur les types de l’appel, par exemple, « audio », « Messagerie instantanée », « audio et vidéo » et « partage d’application ».  <br/> |
|[Table ErrorCategory dans Skype pour Business Server 2015](errorcategory.md) <br/> |Stocke le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015.  <br/> |
|[Table ErrorDef dans Skype pour Business Server 2015](errordef.md) <br/> |Stocke des informations sur les types d’erreurs et leurs définitions.  <br/> |
|[Table /errorreport dans Skype pour Business Server 2015](errorreport.md) <br/> |Stocke des informations sur les erreurs qui se sont produites.  <br/> |
|[Table de ProgressReport](progressreport.md) <br/> |Stocke des informations sur les rapports d’avancement des différentes étapes impliquées dans Skype pour les processus d’entreprise serveur 2015.  <br/> |
   
Les tables de la liste suivante sont utilisés en interne par Skype pour Business Server 2015. Les détails ne sont pas décrites dans ce document.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tables pour une utilisation interne par Lync Server

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**Tableau de la partie frontale** <br/> |À usage interne uniquement.  <br/> |
|**Table de MSMQProcessing** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Table de syndicators** <br/> |À usage interne uniquement.  <br/> |
|**Table de SyndicatorsTenantMap** <br/> |À usage interne uniquement.  <br/> |
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
   

