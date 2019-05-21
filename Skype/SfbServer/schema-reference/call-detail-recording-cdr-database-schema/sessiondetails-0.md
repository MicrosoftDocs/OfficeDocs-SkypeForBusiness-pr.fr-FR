---
title: Affichage SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou un autre type de session. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 627d038389098583b5e42f73e8dd0a1cc339d014
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295845"
---
# <a name="sessiondetails-view"></a>Affichage SessionDetails
 
La vue SessionDetails stocke des informations sur les sessions d’égal à égal, qui peuvent être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux ou un autre type de session. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans la table 2015 de Skype entreprise Server](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations). Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a démarré la session.  <br/> |
|**Visite guidée** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a rejoint la session.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a démarré la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a rejoint la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |Client de l’utilisateur qui a démarré la session. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur qui a rejoint la session. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**FromEndpointId** <br/> |identificateur  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a démarré la session.  <br/> |
|**ToEndpointId** <br/> |identificateur  <br/> |Identificateur unique du point de terminaison de l’utilisateur qui a rejoint la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur qui a démarré la session.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |Nombre de messages envoyés par l’utilisateur ayant rejoint la session.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**FromClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur qui a démarré la session. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur qui a démarré la session.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur ayant rejoint la session  <br/> |
|**ToClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur ayant rejoint la session. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur ayant rejoint la session.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur cible de la session.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |Type d’URI de l’utilisateur cible pour la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a démarré. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont le nom est démarré. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a expertisé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a expertisé la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a fait appel à la session. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |ID de boîte de dialogue SIP. Le format est le suivant:  <br/> boîte de dialogue; à partir d’une balise  <br/> |
|**Corrélation** <br/> |identificateur  <br/> |GUID utilisé pour mettre en corrélation plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Heure de la boîte de dialogue qui a été remplacée par la session. Utilisé conjointement avec ReplaceDialogIdSeq pour identifier de façon unique une boîte de dialogue qui est remplacée par la session. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec ReplaceDialogIdTime pour identifier de façon unique une boîte de dialogue qui est remplacée par la session. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID de boîte de dialogue SIP le remplacement de la session. Le format est le suivant:  <br/> boîte de dialogue; à partir d’une balise  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse au premier message d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir d’en-têtes SIP.  <br/> |
|**Indiquez** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du serveur Edge utilisé par l’utilisateur qui a démarré la session.  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |Indique si l’utilisateur qui a démarré la session s’est connecté à partir du réseau interne.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |Indique si l’utilisateur ayant rejoint la session à partir du réseau interne.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |Priorité de la session.  <br/> |
|**FromUserFlag** <br/> |type  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attribut suivantes sont autorisées:  <br/> 0x01-intégré sur le téléphone de bureau  <br/> |
|**ToUserFlag** <br/> |type  <br/> |Indique les attributs de l’utilisateur qui a démarré la session. Les définitions d’attribut suivantes sont autorisées:  <br/> 0x01-intégré sur le téléphone de bureau  <br/> |
|**CallFlag** <br/> |type  <br/> |Indique les attributs d’appel. Les définitions d’attribut suivantes sont autorisées:  <br/> 0x01-nouvelle tentative de session  <br/> 0x02-appel émis par l’agent pour le compte d’un groupe de réponse  <br/> |
|**Emplacement** <br/> |varchar (max)  <br/> |Emplacement de l’appel d’urgence.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> |Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

