---
title: Vue conferencesessiondetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: La vue ConferenceSessionDetails stocke des informations sur les sessions à plusieurs. Chaque enregistrement représente une session de conférence, de la session ayant le Focus ou la session avec un serveur de conférence spécifique. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 448b73326f7caf7657d146939eb01729e97628f9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213227"
---
# <a name="conferencesessiondetails-view"></a>Vue conferencesessiondetails
 
La vue ConferenceSessionDetails stocke des informations sur les sessions à plusieurs. Chaque enregistrement représente une session de conférence, de la session ayant le Focus ou la session avec un serveur de conférence spécifique. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI du type de conférence. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Identificateur qui fait la distinction entre les instances de conférences périodique. Chaque instance de conférence périodique a le même ConferenceURI, mais une valeur ConfInstance différente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |URI du serveur de conférence.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI du serveur de conférence. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur impliqué dans la session.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a participé à la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a participé à la session. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur qui a participé à la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version du serveur de conférence.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Type de serveur de conférence. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |Catégorie du serveur de conférence.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a participé à la session. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a été démarrée. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont la part de la session a été démarrée. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur ayant référencé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur ayant référencé la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur ayant référencé la session. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |ID du dialogue SIP. Le format est  <br/> : boîte de dialogue de balise ; pour une balise  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Numéro d’identification pour identifier la boîte de dialogue qui a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une session est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP ID de boîte de dialogue remplace la session. Le format de l’est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indique si la session a été démarrée par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indique si la session a été terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indique si l’utilisateur connecté à partir du réseau interne.  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse pour le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir des en-têtes de session SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu pour la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal ayant capturé les données pour la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur qui a participé à la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a participé à la session.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a participé à la session. Les définitions d’attribut suivants autorisées :  <br/> 0 x 01 - intégré avec le téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attribut suivants sont autorisées :  <br/> 0 x 01 - nouvelle tentative Session0  <br/> x02-appel effectué par un agent au nom d’un groupe de réponses  <br/> |
   

