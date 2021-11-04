---
title: Liste des tables d’Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Le schéma de base de données de l’enregistrement des détails des appels comprend les tables suivantes.
ms.openlocfilehash: 1e8c76080089005977154c3e23d924a4b98dc6b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746660"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste des tables d’Skype Entreprise Server 2015
 
Le schéma de base de données de l’enregistrement des détails des appels comprend les tables suivantes. 
  
## <a name="static-tables"></a>Tables statiques

|**Table**|**Description**|
|:-----|:-----|
|[Table CallPriorities dans Skype Entreprise Server 2015](callpriorities.md) <br/> |Stocke la liste des priorités d’appel possibles, telles que les appels très urgents, urgents, normaux, non urgents, etc.  <br/> |
|[Table ConferenceJoinTimeThresholds dans Skype Entreprise Server 2015](conferencejointimethresholds.md) <br/> |Stocke les limites de classification utilisées par le rapport du temps de connexion à la conférence.  <br/> |
|[Table DeRegisterType dans Skype Entreprise Server 2015](deregistertype.md) <br/> |Stocke la liste des raisons possibles de désinscription des utilisateurs, telles que « initiative du client », « expiration de l’inscription », « blocage du client », etc.  <br/> |
|[Table MediaList](medialist.md) <br/> |Stocke la liste des types de médias qui peuvent générer des entrées dans la base de données (par exemple, la messagerie instantanée, l’audio, la vidéo et le transfert de fichiers).  <br/> |
|[Table PurgeSettings](purgesettings.md) <br/> |Stocke les informations qui indiquent si (et quand) les enregistrements des détails des appels obsolètes seront automatiquement supprimés de la base de données d’enregistrement des détails des appels.  <br/> |
|[Table Roles](roles.md) <br/> |Stocke la liste possible des rôles de conférence (par exemple, participant et présentateur).  <br/> |
|[Table SIPResponseMetaData](sipresponsemetadata.md) <br/> |Stocke une liste des codes de réponse SIP ainsi que la classification et la définition de chacun de ces codes.  <br/> |
   
## <a name="supporting-tables"></a>Tables de prise en charge

|**Table**|**Description**|
|:-----|:-----|
|[Table ClientVersions dans Skype Entreprise Server 2015](clientversions.md) <br/> |Stocke les clients (à la fois le type de client et le numéro de version) de chaque client impliqué dans un appel comprenant des informations capturées dans cette base de données.  <br/> |
|[Table ConferenceUris dans Skype Entreprise Server 2015](conferenceuris.md) <br/> |Stocke une liste de ConferenceURI qui sont utilisés dans les appels relatifs à la conférence.  <br/> |
|[Table ContentTypes dans Skype Entreprise Server 2015](contenttypes.md) <br/> |Stocke une liste de types de contenus SIP (Session Initiation Protocol) qui sont utilisés à la fois dans les appels d’égal à égal et les appels de conférence.  <br/> |
|[Table Devices dans Skype Entreprise Server 2015](devices.md) <br/> |Stocke une liste d’appareils, notamment leur fabricant, la version du matériel et l’adresse MAC.  <br/> |
|[Table Dialogs dans Skype Entreprise Server 2015](dialogs.md) <br/> |Stocke des informations sur les ID de dialogue pour chaque session dans la base de données.  <br/> |
|[Table EdgeServers dans Skype Entreprise Server 2015](edgeservers.md) <br/> |Stocke une liste de serveurs Edge qui sont utilisés pour les appels externes.  <br/> |
|[Table Gateways dans Skype Entreprise Server 2015](gateways.md) <br/> |Stocke une liste de passerelles qui sont utilisées pour les appels VoIP (Voice over Internet Protocol).  <br/> |
|[Table HardwareVersions dans Skype Entreprise Server 2015](hardwareversions.md) <br/> |Stocke une liste de versions matérielles d’appareils (téléphone de bureau).  <br/> |
|[Table Manufacturers dans Skype Entreprise Server 2015](manufacturers.md) <br/> |Stocke une liste de fabricants et d’appareils (téléphone de bureau).  <br/> |
|[Table Mcus dans Skype Entreprise Server 2015](mcus.md) <br/> |Stocke des informations sur les différents serveurs de conférence A/V et leurs URI.  <br/> |
|[Table MediationServers](mediationservers.md) <br/> |Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.  <br/> |
|[Table Phones](phones.md) <br/> |Stocke tous les numéros de téléphone utilisés dans les appels VoIP qui ont été archivés ou dont les détails des appels ont été enregistrés.  <br/> |
|[Table Pools](pools.md) <br/> |Stocke les noms du pool sur lequel les messages instantanés ont été capturés.  <br/> |
|[Table Servers](servers.md) <br/> |Stocke le nom des serveurs impliqués dans les appels.  <br/> |
|[Table Tenants](tenants.md) <br/> |Stocke les clients pris en charge par le déploiement en cours. Il existe des clients intégrés pour les utilisateurs d’entreprise, les utilisateurs fédérés, les utilisateurs de connectivité de messagerie instantanée publique et les utilisateurs anonymes.  <br/> |
|[Table UserAgentDef](useragentdef.md) <br/> |Cartes identificateurs d’agent utilisateur aux noms descriptifs de l’agent.  <br/> |
|[Table Users](users.md) <br/> |Stocke les URI des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.  <br/> |
|[Table UserStatistics](userstatistics.md) <br/> |Stocke des informations sur l’utilisation du système par un utilisateur individuel.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tables spécifiques aux enregistrements des détails des appels de conférence

|**Table**|**Description**|
|:-----|:-----|
|[Table Conferences in Skype Entreprise Server 2015](conferences.md) <br/> |Stocke des informations sur toutes les conférences qui ont été archivées ou dont les détails ont été enregistrés, notamment le ConferenceURI, et l’heure de début et de fin.  <br/> |
|[Table ConferenceSessionDetails dans Skype Entreprise Server 2015](conferencesessiondetails-0.md) <br/> |Stocke des informations sur chaque session de conférence fondée sur le protocole SIP, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et l’ID de diagnostic pour chaque session.  <br/> |
|[Table FocusJoinsAndLeaves dans Skype Entreprise Server 2015](focusjoinsandleaves.md) <br/> |Stocke des informations sur les participants et les départs de conférence, y compris le rôle et la version du client des utilisateurs.  <br/> |
|[Table McuJoinsAndLeaves dans Skype Entreprise Server 2015](mcujoinsandleaves.md) <br/> |Stocke des informations sur les serveurs de conférence A/V qui sont impliqués dans une conférence et les heures de départ et d’arrivée de l’utilisateur.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tables des messages dans les conférences de messagerie instantanée

|**Table**|**Description**|
|:-----|:-----|
|[Table ConferenceMessageCount dans Skype Entreprise Server 2015](conferencemessagecount.md) <br/> |Pour chaque conférence de messagerie instantanée, stocke le nombre de messages qui ont été envoyés par chaque utilisateur.  <br/> |
|[Table IMReportSummary dans Skype Entreprise Server 2015](imreportsummary.md) <br/> |Fournit un rapport global sur les sessions de messagerie instantanée ouvertes dans une organisation.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tables des sessions d’égal à égal

|**Table**|**Description**|
|:-----|:-----|
|[Table SessionDetails](sessiondetails.md) <br/> |Stocke des informations sur chaque session d’égal à égal, notamment l’heure de début et de fin, l’ID utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.  <br/> |
|[Table FileTransfers dans Skype Entreprise Server 2015](filetransfers-0.md) <br/> |Stocke des informations sur les sessions de transfert de fichiers, notamment le nom de fichier et le résultat (accepté, rejeté ou annulé).  <br/> |
|[Table Media](media.md) <br/> |Stocke des informations sur les différents types de médias impliqués dans les sessions d’égal à égal.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Table des détails des appels VoIP

|**Table**|**Description**|
|:-----|:-----|
|[Table VoipDetails](voipdetails-0.md) <br/> |Pour chaque appel VoIP/PSTN à deux utilisateurs, stocke des informations sur l’appel, telles que l’ID téléphonique du téléphone VoIP, la passerelle utilisée, et quel participant a été déconnecté. Fait référence à la [table SessionDetails pour les](sessiondetails.md) heures de début/fin des appels et le code de réponse. <br/> |
   
> [!NOTE]
> Si l’un des participants à l’appel est un utilisateur VoIP ou si un serveur de médiation a été impliqué dans cet appel, un enregistrement sera créé dans cette table. Les informations sur les appels VoIP/VoIP n’impliquant pas de téléphone PSTN (réseau téléphonique commuté) sont capturées dans la [table SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Table pour l’audit d’appel E9-1-1

|**Table**|**Description**|
|:-----|:-----|
|[Table Locations dans Skype Entreprise Server 2015](locations.md) <br/> |Pour chaque appel très urgents, tel que l’appel Enhanced 9-1-1 (E9-1-1), stocke les informations d’emplacement concernant l’appel. Fait référence à la [table SessionDetails pour les](sessiondetails.md) heures de début/fin des appels et le code de réponse. <br/> |
   
> [!NOTE]
> Cette table ne contient que le blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour d’autres informations détaillées concernant l’appel. 
  
## <a name="tables-for-troubleshooting"></a>Tables de dépannage

|**Table**|**Description**|
|:-----|:-----|
|[Table Application dans Skype Entreprise Server 2015](application.md) <br/> |Stocke des informations sur différents processus Skype Entreprise Server 2015 impliqués dans le routage et les connexions.  <br/> |
|[Table CallType dans Skype Entreprise Server 2015](calltype.md) <br/> |Stocke des informations sur les types d’appel, tels que « audio », « Messagerie instantanée », « audio et vidéo » et « partage d’application ».  <br/> |
|[Table ErrorCategory dans Skype Entreprise Server 2015](errorcategory.md) <br/> |Stocke le nom convivial de chaque classification Skype Entreprise Server diagnostic 2015.  <br/> |
|[Table ErrorDef dans Skype Entreprise Server 2015](errordef.md) <br/> |Stocke des informations sur les types d’erreurs et leurs définitions.  <br/> |
|[Table ErrorReport dans Skype Entreprise Server 2015](errorreport.md) <br/> |Stocke des informations sur les erreurs qui se sont produites.  <br/> |
|[Table ProgressReport](progressreport.md) <br/> |Stocke des informations sur les rapports d’avancement des différentes étapes Skype Entreprise Server processus 2015.  <br/> |
   
Les tableaux de la liste suivante sont utilisés en interne Skype Entreprise Server 2015. Elles ne sont pas détaillées dans ce document.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tables destinées à une utilisation interne par Lync Server

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |À usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |À usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |À usage interne uniquement.  <br/> |
|**Table FrontEnd** <br/> |À usage interne uniquement.  <br/> |
|**Table MSMQProcessing** <br/> |À usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**Table Syndicators** <br/> |À usage interne uniquement.  <br/> |
|**Table SyndicatorsTenantMap** <br/> |À usage interne uniquement.  <br/> |
|**Table Task** <br/> |À usage interne uniquement.  <br/> |
|**UserStatistics** <br/> |À usage interne uniquement.  <br/> |
|**UsageSummary_UQ** <br/> |À usage interne uniquement.  <br/> |
|**UsageSummary** <br/> |À usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |À usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |À usage interne uniquement.  <br/> |
|**TimeZones** <br/> |À usage interne uniquement.  <br/> |
|**FailureSummary_UQ** <br/> |À usage interne uniquement.  <br/> |
|**FailureSummary** <br/> |À usage interne uniquement.  <br/> |
|**ServerSummary** <br/> |À usage interne uniquement.  <br/> |
|**MsDiagMetaData** <br/> |À usage interne uniquement.  <br/> |
   

