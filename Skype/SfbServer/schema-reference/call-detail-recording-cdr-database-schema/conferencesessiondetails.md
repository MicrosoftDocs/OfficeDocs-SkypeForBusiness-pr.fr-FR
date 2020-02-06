---
title: Affichage ConferenceSessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: Le mode ConferenceSessionDetails stocke les informations sur les sessions multiparties. Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815332"
---
# <a name="conferencesessiondetails-view"></a>Affichage ConferenceSessionDetails
 
Le mode ConferenceSessionDetails stocke les informations sur les sessions multiparties. Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**InviteTime** <br/> |DateHeure  <br/> |Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI du type de conférence. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |identificateur  <br/> |Identificateur qui différencie les instances des conférences périodiques. Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |URI du serveur de conférence.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |Type d’URI du serveur de conférence. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur impliqué dans la session.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui faisait partie de la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui faisait partie de la session. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**UserEndpointId** <br/> |identificateur  <br/> |Identificateur unique de l’utilisateur dont vous participez à la session.  <br/> |
|**EndTime** <br/> |DateHeure  <br/> |Heure de fin de la session.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |Version du serveur de conférence.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |Type du serveur de conférence. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |Catégorie de serveur de conférence.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur ayant participé à la session.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur ayant participé à la session. Pour plus d’informations, voir la [table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |Nom de la catégorie du client utilisée par l’utilisateur qui faisait partie de la session.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur au nom duquel la session a été démarrée.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur au nom duquel la session a démarré. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont le nom est démarré. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a expertisé la session.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a expertisé la session. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a fait appel à la session. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**DialogId** <br/> |varstring (LGA775)  <br/> |ID de boîte de dialogue SIP. Le format est  <br/> :d ialog ; from-tag ; to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec ReplaceDialogIdTime pour identifier de manière unique une session qui est remplacée par cette session. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |ID de boîte de dialogue SIP le remplacement de la session. Le format de :  <br/> boîte de dialogue ; à partir d’une balise  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |Indique si la session a été démarrée par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |Indique si la session a été terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |Indique si l’utilisateur s’est connecté à partir du réseau interne.  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> |Heure de la réponse au premier message d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ResponseCode** <br/> |int  <br/> |Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |ID de diagnostic capturé à partir d’en-têtes SIP de session.  <br/> |
|**Indiquez** <br/> |nvarchar(256)  <br/> |Type de contenu de la session.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du serveur frontal qui a capturé les données de la session.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |Serveur de médiation utilisé par l’utilisateur ayant participé à la session.  <br/> |
|**Passerelle** <br/> |nvarchar(256)  <br/> |Passerelle utilisée par l’utilisateur ayant participé à la session.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur ayant participé à la session.  <br/> |
|**UserFlag** <br/> |type  <br/> |Indique les attributs de l’utilisateur ayant participé à la session. Les définitions d’attribut suivantes sont autorisées :  <br/> 0x01-intégré sur le téléphone de bureau  <br/> |
|**CallFlag** <br/> |type  <br/> |Indique les attributs d’appel. Les définitions d’attribut suivantes sont autorisées :  <br/> 0x01-nouvelle tentative de Session0  <br/> x02 : appel passé par l’agent pour le compte d’un Response Group  <br/> |
   

