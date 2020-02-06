---
title: Table ConferenceSessionDetails dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.
ms.openlocfilehash: 95cf64589cdcd0fd38b4e29cd4e863c870f2a7a6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815342"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Table ConferenceSessionDetails dans Skype entreprise Server 2015
 
Chaque enregistrement représente une seule session de conférence, qui peut correspondre soit à la session ayant le focus, soit à la session associée à un serveur de conférence particulier.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Valeur  <br/> |Etranger principal  <br/> |Durée de la demande de session ; utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une session de conférence. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session de conférence. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externes  <br/> |URI de conférence Focus liée à cette session. Pour plus d’informations, reportez-vous [à la table ConferenceUris dans Skype entreprise Server 2015](conferenceuris.md) . Cet URI est un URI de conférence en fonction du focus. <br/> |
|**ConfInstance** <br/> |Identificateur  <br/> ||Identificateur qui différencie les instances des conférences périodiques. Chaque instance de conférence périodique a le même ConferenceURI mais une valeur ConfInstance différente.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Externes  <br/> |URI de la Conférence Server Conferencing liée à cette session. Pour plus d’informations, reportez-vous [à la table ConferenceUris dans Skype entreprise Server 2015](conferenceuris.md) . Cet URI est l’URI de conférence basée sur le serveur de conférence. Pour les sessions de conférence au focus, cette colonne a la valeur null. <br/> |
|**UserId** <br/> |int  <br/> |Externes  <br/> |ID d’un utilisateur dans la session de conférence. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**UserEndpointId** <br/> |identificateur  <br/> ||GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur d’autres ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externes  <br/> |Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Externes  <br/> |ID de l’utilisateur avec lequel l’appel est soumis. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Externes  <br/> |Version du client utilisée par l’utilisateur de la Conférence. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Externes  <br/> |Version du client utilisée par le serveur de conférence. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Externes  <br/> |Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externes  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session qui est remplacée par cette session. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indique si la session a démarré par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indique si la session a été terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si l’utilisateur est connecté à partir d’un emplacement interne ou non.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP (Session Initiation Protocol) à l’invitation à la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Externes  <br/> |ID du serveur frontal utilisé pour cette session. Pour plus d’informations, voir la [table serveurs](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Externes  <br/> |ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la [table pools](pools.md) . <br/> |
|**MediationServerId** <br/> |int  <br/> |Externes  <br/> |Serveur de médiation utilisé par l’appel. Pour plus d’informations, voir la [table MediationServers](mediationservers.md) . <br/> |
|**GatewayId** <br/> |int  <br/> |Externes  <br/> |Passerelle utilisée par l’appel. Pour plus d’informations, voir le [tableau des passerelles dans Skype entreprise Server 2015](gateways.md) . <br/> |
|**EdgeServerId** <br/> |int  <br/> |Externes  <br/> |Serveur Edge utilisé par l’appel. Pour plus d’informations, reportez-vous [à la table EdgeServers dans Skype entreprise Server 2015](edgeservers.md) . <br/> |
|**ContentTypeId** <br/> |int  <br/> |Externes  <br/> |Type de contenu utilisé dans la session. Pour plus d’informations, reportez-vous [à la table ContentTypes dans Skype entreprise Server 2015](contenttypes.md) . <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la première réponse SIP. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Externes  <br/> |Contient la valeur du type d’URI MCU de la [table UriTypes](uritypes.md). Ce champ permet d’améliorer les performances de requête.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |type  <br/> || Un ensemble de bits indiquant les attributs de l’utilisateur. Les définitions d’attribut suivantes apparaissent : <br/>  Intégré au téléphone de bureau-1 <br/> |
|**CallFlag** <br/> |type  <br/> || Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivantes apparaissent : <br/>  Nouvelle tentative de session-1 <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.
  

