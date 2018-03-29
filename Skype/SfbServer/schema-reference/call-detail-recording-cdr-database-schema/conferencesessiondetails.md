---
title: Vue de ConferenceSessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vue ConferenceSessionDetails stocke des informations sur les sessions multi-utilisateurs. Chaque enregistrement représente une session de conférence, ce qui pourrait être la session qui a le Focus ou la session avec un serveur de conférence spécifique. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 8e81f33a68fc90a589f4d3574f9ca3070076c479
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-view"></a>Vue de ConferenceSessionDetails
 
La vue ConferenceSessionDetails stocke des informations sur les sessions multi-utilisateurs. Chaque enregistrement représente une session de conférence, ce qui pourrait être la session qui a le Focus ou la session avec un serveur de conférence spécifique. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande d’invitation. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI du type de conférence. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificateur qui fait la distinction entre les instances de conférences périodiques. Chaque instance de conférence périodique a la même ConferenceURI mais une valeur différente de ConfInstance.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI du serveur de conférence.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI du serveur de conférence. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur impliqué dans la session.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont a été partie de la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur ne dont faisait partie de la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur ne dont faisait partie de la session.  <br/> |
|**Heure de fin** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version du serveur de conférence.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Type de serveur de conférence. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Catégorie du serveur de conférence.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui ont participé à la session.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui ont participé à la session. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur qui fait partie de la session.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a été démarrée. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Les clients de l’utilisateur dont sur le compte de démarrage de la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui l’a appelée la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui l’a appelée la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur qui l’a appelée la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID de boîte de dialogue SIP. Le format est  <br/> : boîte de dialogue, à partir de balise ; de balise  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Numéro d’ID pour identifier la boîte de dialogue a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec ReplaceDialogIdTime pour identifier de manière unique une session qui est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP ID de boîte de dialogue remplace par la session. Le format de l’est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indique si la session a été démarrée par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indique si la session a été interrompue par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indique si l’utilisateur connecté à partir du réseau interne.  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse vers le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturée à partir des en-têtes de session SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**Site Web frontal** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal ayant capturé les données pour la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a participé à la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attribut suivant autorisées :  <br/> 0 x 01 - intégré à un téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attribut suivantes sont autorisées :  <br/> une nouvelle tentative de 0 x 01 - Session0  <br/> x02-un appel effectué par l’agent pour un groupe de réponse  <br/> |
   

