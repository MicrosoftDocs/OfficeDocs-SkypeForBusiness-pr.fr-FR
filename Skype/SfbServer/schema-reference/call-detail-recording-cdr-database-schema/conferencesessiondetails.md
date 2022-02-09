---
title: Affichage ConferenceSessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: L’affichage ConferenceSessionDetails stocke les informations relatives aux sessions entre plusieurs participants. Chaque enregistrement représente une session de conférence, laquelle peut être la session ayant le focus ou la session basée sur un serveur de conférence spécifique. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 902cf40a042d51d6765a0653da439b1bc1a86478
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400858"
---
# <a name="conferencesessiondetails-view"></a>Affichage ConferenceSessionDetails
 
L’affichage ConferenceSessionDetails stocke les informations relatives aux sessions entre plusieurs participants. Chaque enregistrement représente une session de conférence, laquelle peut être la session ayant le focus ou la session basée sur un serveur de conférence spécifique. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première requête INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de conférence. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI du serveur de conférence.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Type du serveur de conférence. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur impliqué dans la session.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur qui a participé à la session. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a participé à la session. Pour plus [d’informations, voir le tableau Tenants](tenants.md) . <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur qui a participé à la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version du serveur de conférence.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Type du serveur de conférence. Pour plus [d’informations, voir la table UserAgentDef](useragentdef.md) . <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Catégorie du serveur de conférence.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client dont s’est servi l’utilisateur qui a participé à la session.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client dont s’est servi l’utilisateur qui a participé à la session. Pour plus [d’informations, voir la table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client dont s’est servi l’utilisateur qui a participé à la session.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur pour le compte duquel la session a été démarrée.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus [d’informations, voir le tableau Tenants](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a référencé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur qui a référencé la session. Pour plus [d’informations, voir la table UriTypes](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a référencé la session. Pour plus [d’informations, voir le tableau Tenants](tenants.md) . <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de dialogue SIP. Le format est le suivant :  <br/> :d ialog;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Numéro d’identification permettant d’identifier le dialogue remplacé par la session actuelle. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec ReplacesDialogIdTime pour identifier de manière unique une session remplacée par cette session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP de la session. Le format est le suivant :  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indique si la session a été démarrée par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indique si la session a été terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir des en-têtes de session SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal qui a capturé les données de la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool qui a capturé les données de la session.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation dont s’est servi l’utilisateur qui a participé à la session.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> |Passerelle dont s’est servi l’utilisateur qui a participé à la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge dont s’est servi l’utilisateur qui a participé à la session.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attributs suivantes sont autorisées :  <br/> 0x01 - Intégré au téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :  <br/> 0x01 - Nouvelle tentative de session  <br/> 0x02 - Appel effectué par un agent pour le compte d’un groupe Response Group  <br/> |
   

