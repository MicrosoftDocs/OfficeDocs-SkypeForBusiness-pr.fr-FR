---
title: Vue SessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peut être un appel VoIP-VoIP, par messagerie instantanée deux ou tout autre type de session. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: c62f6e2c1bb505bf00d56898a562db2c00d298d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212816"
---
# <a name="sessiondetails-view"></a>Vue SessionDetails
 
La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peut être un appel VoIP-VoIP, par messagerie instantanée deux ou tout autre type de session. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Voir le tableau des [boîtes de dialogue tableau Skype pour Business Server 2015](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO). Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur ayant démarré la session.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur ayant participé à la session.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur ayant démarré la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur ayant participé à la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Client de l’utilisateur ayant démarré la session. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur ayant participé à la session. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur ayant démarré la session.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur ayant participé à la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur ayant démarré la session.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur ayant participé à la session.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur ayant démarré la session.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur ayant démarré la session. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur ayant démarré la session.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur ayant participé à la session  <br/> |
|**ToClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur ayant participé à la session. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur ayant participé à la session.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur cible de la session.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Type d’URI de l’utilisateur cible pour la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a été démarrée. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont la part de la session a été démarrée. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur ayant référencé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur ayant référencé la session. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur ayant référencé la session. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID du dialogue SIP. Le format est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> |
|**ID de corrélation** <br/> |uniqueidentifier  <br/> |GUID qui sert à corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Heure de la boîte de dialogue qui a été remplacée par la session. Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de manière unique une boîte de dialogue qui est remplacée par la session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une boîte de dialogue qui est remplacée par la session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP ID de boîte de dialogue remplace la session. Le format est :  <br/> boîte de dialogue de balise ; pour une balise  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse pour le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir des en-têtes SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal ayant capturé les données pour la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur ayant démarré la session.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a initié la session  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a initié la session connecté à partir du réseau interne.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a rejoint la session connecté à partir du réseau interne.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Priorité d’appel de la session.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur ayant démarré la session. Les définitions d’attribut suivants sont autorisées :  <br/> 0 x 01 - intégré avec le téléphone de bureau  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur ayant démarré la session. Les définitions d’attribut suivants sont autorisées :  <br/> 0 x 01 - intégré avec le téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attribut suivants sont autorisées :  <br/> 0 x 01 - nouvelle tentative de Session  <br/> 0 x 02 - appel effectué par un agent au nom d’un groupe de réponses  <br/> |
|**Emplacement** <br/> |varchar (max)  <br/> |Emplacement de l’appel d’urgence.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> |Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

