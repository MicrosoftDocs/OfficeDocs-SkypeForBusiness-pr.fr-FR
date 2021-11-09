---
title: Affichage SessionDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou tout autre type de session. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6a100fcd2143244bda5ad7273b5a681468ad5713
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852918"
---
# <a name="sessiondetails-view"></a>Affichage SessionDetails
 
La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou tout autre type de session. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première requête INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO). Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a démarré la session.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a rejoint la session.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a démarré la session. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a rejoint la session. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |Client de l’utilisateur qui a démarré la session. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a rejoint la session. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur qui a démarré la session.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur qui a rejoint la session.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a démarré la session. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a rejoint la session  <br/> |
|**ToClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a rejoint la session. Pour plus d’informations, voir la [table UserAgentDef.](useragentdef.md) <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur qui a rejoint la session.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur cible de la session.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |Type d’URI de l’utilisateur cible pour la session. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur pour le compte duquel la session a été démarrée.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur pour le compte duquel la session a été démarrée. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a référencé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur qui a référencé la session. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a référencé la session. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP. Le format est :  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |GUID utilisé pour corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Heure de la boîte de dialogue qui a été remplacée par la session. Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de manière unique une boîte de dialogue remplacée par la session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une boîte de dialogue remplacée par la session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |ID de dialogue SIP de la session. Le format est :  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir des en-têtes SIP.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |Type de contenu pour la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur frontal qui a capturé les données de la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool qui a capturé les données de la session.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN du serveur Edge utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |FQDN du serveur Edge utilisé par l’utilisateur qui a démarré la session  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a démarré la session s’est connecté à partir du réseau interne.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a rejoint la session s’est connecté à partir du réseau interne.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Priorité d’appel de la session.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attributs suivantes sont autorisées :  <br/> 0x01 - Intégré dans téléphone de bureau  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attributs suivantes sont autorisées :  <br/> 0x01 - Intégré dans téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> |Indique les attributs de l’appel. Les définitions d’attributs suivantes sont autorisées :  <br/> 0x01 - Nouvelle tentative de session  <br/> 0x02 : appel effectué par un agent au nom d’un groupe Response Group  <br/> |
|**Location** <br/> |varchar(max)  <br/> |Emplacement de l’appel d’urgence.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

