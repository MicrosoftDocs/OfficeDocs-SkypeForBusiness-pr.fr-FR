---
title: Vue de SessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vue SessionDetails stocke des informations sur les sessions de peer-to-peer, qui peut être un appel VoIP-VoIP, session de messagerie instantanée de deux tiers ou tout autre type de session. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: b13b0b184d13273c339f1ca3fa09a68687d26889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-view"></a>Vue de SessionDetails
 
La vue SessionDetails stocke des informations sur les sessions de peer-to-peer, qui peut être un appel VoIP-VoIP, session de messagerie instantanée de deux tiers ou tout autre type de session. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez la Table [table dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande d’invitation. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO). Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a démarré la session.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a rejoint la session.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a démarré la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a rejoint la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Clients de l’utilisateur qui a démarré la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur qui a rejoint la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.  <br/> |
|**Heure de fin** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur qui a démarré la session.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur qui a rejoint la session.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a démarré la session. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a rejoint la session  <br/> |
|**ToClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a rejoint la session. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur qui a rejoint la session.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur cible de la session.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Type d’URI de l’utilisateur cible pour la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a été démarrée. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Les clients de l’utilisateur dont sur le compte de démarrage de la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui l’a appelée la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui l’a appelée la session. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur qui l’a appelée la session. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de boîte de dialogue SIP. Le format est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> |
|**ID de corrélation** <br/> |uniqueidentifier  <br/> |Identificateur unique utilisé pour corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Heure de la boîte de dialogue qui a été remplacé par la session. Utilisé en association avec ReplaceDialogIdSeq pour identifier de manière unique une boîte de dialogue qui est remplacée par la session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec ReplaceDialogIdTime pour identifier de manière unique une boîte de dialogue qui est remplacée par la session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |SIP ID de boîte de dialogue remplace par la session. Le format est :  <br/> boîte de dialogue, à partir de balise ; de balise  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse vers le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturée à partir des en-têtes SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**Site Web frontal** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal ayant capturé les données pour la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant capturé les données pour la session.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a démarré la session ouvert une session sur le réseau interne.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a rejoint la session ouvert une session sur le réseau interne.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Appelez la priorité de la session.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attribut suivantes sont autorisées :  <br/> 0 x 01 - intégré à un téléphone de bureau  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attribut suivantes sont autorisées :  <br/> 0 x 01 - intégré à un téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attribut suivantes sont autorisées :  <br/> une nouvelle tentative de 0 x 01 - Session  <br/> 0 x 02 - un appel effectué par l’agent pour un groupe de réponse  <br/> |
|**Emplacement** <br/> |varchar (max)  <br/> |Emplacement d’appel d’urgence.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> |Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

