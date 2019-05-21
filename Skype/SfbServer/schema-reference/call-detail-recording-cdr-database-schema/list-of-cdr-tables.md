---
title: Liste des tables CDR dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Le schéma de base de données d’enregistrement des détails des appels (CDR) se compose des tableaux suivants.
ms.openlocfilehash: a8d36d75f629b41c535de99c0b9aef42770ba573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296153"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Liste des tables CDR dans Skype entreprise Server 2015
 
Le schéma de base de données d’enregistrement des détails des appels (CDR) se compose des tableaux suivants. 
  
## <a name="static-tables"></a>Tableaux statiques

|**Table**|**Description**|
|:-----|:-----|
|[Table CallPriorities dans Skype entreprise Server 2015](callpriorities.md) <br/> |Cette liste contient les différentes priorités d’appels (par exemple, l’urgence, le standard, le standard, les non urgentes, etc.).  <br/> |
|[Table ConferenceJoinTimeThresholds dans Skype entreprise Server 2015](conferencejointimethresholds.md) <br/> |Stocke les limites de classification utilisées par le rapport de synthèse des heures de participation à la Conférence.  <br/> |
|[Table DeRegisterType dans Skype entreprise Server 2015](deregistertype.md) <br/> |Stocke la liste des raisons possibles de registre de l’utilisateur, telles que «initié par le client», «inscription expirée», «blocage du client» et plus encore.  <br/> |
|[Table MediaList](medialist.md) <br/> |Stocke la liste de types de médias qui peuvent générer des entrées dans la base de données (par exemple, messagerie instantanée, audio, vidéo et transfert de fichiers).  <br/> |
|[Table PurgeSettings](purgesettings.md) <br/> |Stocke les informations qui spécifient si les enregistrements de détails des appels obsolètes sont automatiquement supprimés de la base de données CDR.  <br/> |
|[Table Roles](roles.md) <br/> |Stocke la liste des rôles de conférences possibles (par exemple, participants et présentateur).  <br/> |
|[Table SIPResponseMetaData](sipresponsemetadata.md) <br/> |Stocke une liste des codes de réponse SIP et la classification et la définition de chacun de ces codes.  <br/> |
   
## <a name="supporting-tables"></a>Tableaux pris en charge

|**Table**|**Description**|
|:-----|:-----|
|[Table ClientVersions dans Skype entreprise Server 2015](clientversions.md) <br/> |Stocke les clients (le type de client et le numéro de version) de chaque client impliqué dans un appel et les informations capturées dans cette base de données.  <br/> |
|[Table ConferenceUris dans Skype entreprise Server 2015](conferenceuris.md) <br/> |Stocke une liste de ConferenceURIs utilisés dans les appels liés à la Conférence.  <br/> |
|[Table ContentTypes dans Skype entreprise Server 2015](contenttypes.md) <br/> |Stocke une liste de types de contenu SIP (Session Initiation Protocol) qui sont utilisés dans les appels d’égal à égal et les téléconférences.  <br/> |
|[Tableau des appareils dans Skype entreprise Server 2015](devices.md) <br/> |Stocke une liste d’appareils, dont le fabricant, la version matérielle et l’adresse MAC.  <br/> |
|[Tableau boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) <br/> |Stocke les informations sur l’ID de boîte de dialogue de chaque session dans la base de données.  <br/> |
|[Table EdgeServers dans Skype entreprise Server 2015](edgeservers.md) <br/> |Stocke une liste de serveurs Edge utilisés pour les appels externes.  <br/> |
|[Tableau passerelles dans Skype entreprise Server 2015](gateways.md) <br/> |Stocke une liste des passerelles utilisées pour les appels voix sur IP (VoIP).  <br/> |
|[Table HardwareVersions dans Skype entreprise Server 2015](hardwareversions.md) <br/> |Stocke une liste de versions matérielles d’appareils (téléphone de bureau).  <br/> |
|[Tableau constructeurs dans Skype entreprise Server 2015](manufacturers.md) <br/> |Stocke une liste de fabricants de périphériques (téléphone de bureau).  <br/> |
|[Table MCU dans Skype entreprise Server 2015](mcus.md) <br/> |Stocke des informations sur les divers serveurs de conférence A/V et leurs URI.  <br/> |
|[Table MediationServers](mediationservers.md) <br/> |Stocke une liste de serveurs de médiation qui sont utilisés pour les appels VoIP.  <br/> |
|[Table !Phones](phones.md) <br/> |Stocke tous les numéros de téléphone utilisés pour les appels VoIP archivés ou dont les détails des appels ont été enregistrés.  <br/> |
|[Table Pools](pools.md) <br/> |Stocke les noms de la liste des messages INSTANTANÉs capturés.  <br/> |
|[Table Servers](servers.md) <br/> |Stocke le nom des serveurs impliqué dans les appels.  <br/> |
|[Table Tenants](tenants.md) <br/> |Stocke les locataires pris en charge par le déploiement actuel. Il s’agit de clients intégrés d’entreprise, d’utilisateurs fédérés, d’utilisateurs de la connectivité de messagerie instantanée publique et d’utilisateurs anonymes.  <br/> |
|[Table UserAgentDef](useragentdef.md) <br/> |Mappe des identificateurs d’agent utilisateur aux noms descriptifs de l’agent.  <br/> |
|[Table Users](users.md) <br/> |Stocke les URI utilisateur des utilisateurs qui ont participé à des sessions enregistrées ou archivées dans cette base de données.  <br/> |
|[Table UserStatistics](userstatistics.md) <br/> |Stocke des informations sur l’utilisation individuelle du système par un utilisateur.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tableaux spécifiques aux enregistrements de la Conférence CDR

|**Table**|**Description**|
|:-----|:-----|
|[Tableau conférences dans Skype entreprise Server 2015](conferences.md) <br/> |Stocke des informations sur toutes les conférences archivées ou dont les détails ont été enregistrés, y compris ConferenceURI et les heures de début et de fin.  <br/> |
|[Table ConferenceSessionDetails dans Skype entreprise Server 2015](conferencesessiondetails-0.md) <br/> |Stocke des informations sur chaque session de conférence SIP, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et l’ID de diagnostic de chaque session.  <br/> |
|[Table FocusJoinsAndLeaves dans Skype entreprise Server 2015](focusjoinsandleaves.md) <br/> |Stocke des informations sur les joints et les feuilles de conférence, y compris le rôle et la version du client.  <br/> |
|[Table McuJoinsAndLeaves dans Skype entreprise Server 2015](mcujoinsandleaves.md) <br/> |Stocke des informations sur les serveurs de téléconférence A/V qui participent à une conférence et l’utilisateur a rejoint et laisse des heures.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tableaux de messages dans les conférences de messagerie instantanée

|**Table**|**Description**|
|:-----|:-----|
|[Table ConferenceMessageCount dans Skype entreprise Server 2015](conferencemessagecount.md) <br/> |Pour chaque conférence par messagerie instantanée, stocke le nombre de messages envoyés par chaque utilisateur.  <br/> |
|[Table IMReportSummary dans Skype entreprise Server 2015](imreportsummary.md) <br/> |Fournit un rapport global sur les sessions de messagerie instantanée tenues au sein d’une organisation.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tables pour les sessions d’égal à égal

|**Table**|**Description**|
|:-----|:-----|
|[Table SessionDetails](sessiondetails.md) <br/> |Stocke des informations sur chaque session d’égal à égal, y compris l’heure de début et de fin, l’ID d’utilisateur, le code de réponse et le nombre de messages pour chaque utilisateur.  <br/> |
|[Table FileTransfers dans Skype entreprise Server 2015](filetransfers-0.md) <br/> |Stocke les informations sur les sessions de transfert de fichiers, y compris le nom de fichier et le résultat (accepté, rejeté ou annulé).  <br/> |
|[Table Media](media.md) <br/> |Stocke les informations sur les différents types de médias impliqués dans les sessions d’égal à égal.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tableau des détails des appels VoIP

|**Table**|**Description**|
|:-----|:-----|
|[Table VoipDetails](voipdetails-0.md) <br/> |Pour chaque appel VoIP/PSTN à deux tiers, enregistre les informations relatives à l’appel, telles que l’ID de téléphone du téléphone VoIP, la passerelle utilisée et la partie déconnectée. Fait référence à la [table SessionDetails](sessiondetails.md) pour les heures de début et de fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> S’il s’agit d’un utilisateur VoIP ou d’un serveur de médiation qui intervient dans le cas d’un appel, un enregistrement est créé dans ce tableau. Les informations sur les appels VoIP/VoIP qui n’impliquent pas de téléphone commuté (RTC) (réseau téléphonique commuté) sont capturées dans la [table SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tableau pour l’audit d’appels E9-1-1

|**Table**|**Description**|
|:-----|:-----|
|[Tableau emplacements dans Skype entreprise Server 2015](locations.md) <br/> |Pour chaque appel d’urgence, par exemple un appel 9-1-1 amélioré (E9-1-1), stocke les informations d’emplacement relatives à l’appel. Fait référence à la [table SessionDetails](sessiondetails.md) pour les heures de début et de fin d’appel et le code de réponse. <br/> |
   
> [!NOTE]
> Ce tableau contient uniquement l’objet blob d’emplacement pour l’appel E9-1-1. Fait référence à la table SessionDetails pour obtenir d’autres informations détaillées sur l’appel. 
  
## <a name="tables-for-troubleshooting"></a>Tableaux pour la résolution des problèmes

|**Table**|**Description**|
|:-----|:-----|
|[Tableau d’application dans Skype entreprise Server 2015](application.md) <br/> |Stocke les informations relatives à divers processus dans Skype entreprise Server 2015 qui participent au routage et aux connexions.  <br/> |
|[CallType table dans Skype entreprise Server 2015](calltype.md) <br/> |Stocke des informations sur les types de l’appel (par exemple, «audio», «messages instantanés», «audio et vidéo» et «partage d’application»).  <br/> |
|[Table ErrorCategory dans Skype entreprise Server 2015](errorcategory.md) <br/> |Stocke le nom convivial de chaque classification de diagnostic 2015 de Skype entreprise Server.  <br/> |
|[Table ErrorDef dans Skype entreprise Server 2015](errordef.md) <br/> |Stocke des informations sur les types d’erreurs et leurs définitions.  <br/> |
|[Table ErrorReport dans Skype entreprise Server 2015](errorreport.md) <br/> |Stocke les informations sur les erreurs qui se sont produites.  <br/> |
|[Table ProgressReport](progressreport.md) <br/> |Stocke des informations sur les rapports de progression de diverses étapes associées aux processus de 2015 de Skype entreprise Server.  <br/> |
   
Les tables de la liste suivante sont utilisées en interne par Skype entreprise Server 2015. Leurs détails ne sont pas décrits dans ce document.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tables pour une utilisation interne par Lync Server

|**Table**|**Description**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Pour un usage interne uniquement.  <br/> |
|**DbConfigInt** <br/> |Pour un usage interne uniquement.  <br/> |
|**DbErrorMessage** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table frontale** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table MSMQProcessing** <br/> |Pour un usage interne uniquement.  <br/> |
|**SummaryTableConfiguration** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table syndicators** <br/> |Pour un usage interne uniquement.  <br/> |
|**Table SyndicatorsTenantMap** <br/> |Pour un usage interne uniquement.  <br/> |
|**Tableau de tâches** <br/> |Pour un usage interne uniquement.  <br/> |
|**UserStatistics** <br/> |Pour un usage interne uniquement.  <br/> |
|**UsageSummary_UQ** <br/> |Pour un usage interne uniquement.  <br/> |
|**UsageSummary** <br/> |Pour un usage interne uniquement.  <br/> |
|**DaylightSavingYears** <br/> |Pour un usage interne uniquement.  <br/> |
|**TimeZoneConfiguration** <br/> |Pour un usage interne uniquement.  <br/> |
|**Fuseau** <br/> |Pour un usage interne uniquement.  <br/> |
|**FailureSummary_UQ** <br/> |Pour un usage interne uniquement.  <br/> |
|**FailureSummary** <br/> |Pour un usage interne uniquement.  <br/> |
|**ServerSummary** <br/> |Pour un usage interne uniquement.  <br/> |
|**MsDiagMetaData** <br/> |Pour un usage interne uniquement.  <br/> |
   

