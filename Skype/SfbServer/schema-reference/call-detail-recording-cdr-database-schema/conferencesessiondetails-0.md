---
title: Table ConferenceSessionDetails dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Chaque enregistrement représente une session de conférence, de la session ayant le Focus ou la session avec un serveur de conférence spécifique.
ms.openlocfilehash: ab51ff0c75ba5ea9c6164fdee00be65ff5538c73
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885711"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Table ConferenceSessionDetails dans Skype pour Business Server 2015
 
Chaque enregistrement représente une session de conférence, de la session ayant le Focus ou la session avec un serveur de conférence spécifique.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session ; utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session de conférence. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session de conférence. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |URI de conférence de focus associées à cette session. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. Cet URI est un URI de conférence basée sur le Focus. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificateur qui fait la distinction entre les instances de conférences périodique. Chaque instance de conférence périodique a le même ConferenceURI, mais une valeur ConfInstance différente.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |Conférence de serveur de conférence URI associées à cette session. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. Cet URI est la conférence sur le serveur de conférence URI. Pour les sessions de conférence de Focus, cette colonne est nulle. <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Étrangère  <br/> |ID d’un utilisateur dans la session de conférence. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID pour identifier l’instance du point de terminaison. Par exemple, si un utilisateur ouvre une session sur des ordinateurs différents avec le même compte, puis chaque ordinateur aura un ID de point de terminaison différent.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étrangère  <br/> |Indique l’ID de l’utilisateur qui est l’appelant part. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ReferredById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur à qui l’appel est appelé. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par l’utilisateur de la conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par le serveur de conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la boîte de dialogue qui a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indique si la session démarrée par le serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indique si la session est terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si utilisateur est connecté en interne ou non.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse Session Initiation Protocol (SIP) à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur frontal utilisé pour cette session. Consultez le [tableau de serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez le [tableau de Pools](pools.md) pour plus d’informations. <br/> |
|**MediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation à l’aide de l’appel. Consultez la [table MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**GatewayId** <br/> |int  <br/> |Étrangère  <br/> |À l’aide de la passerelle de l’appel. Consultez le [tableau passerelles Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur Edge à l’aide de l’appel. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type de contenu utilisé dans la session. Voir la [table ContentTypes dans Skype pour Business Server 2015](contenttypes.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la première réponse SIP. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Étrangère  <br/> |Contient la valeur de type de MCU URI à partir de la [table UriTypes](uritypes.md). Ce champ est utilisé pour améliorer les performances de requête.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Un ensemble de bits qui indique les attributs de l’utilisateur. Les définitions d’attribut suivants sont répertoriées : <br/>  Intégré à un téléphone de bureau - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Un ensemble de bits qui indique les attributs de l’appel. Les définitions d’attribut suivants sont répertoriées : <br/>  Nouvelle tentative de Session - 1 <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions SessionIdSeq aura la valeur 1. Si plusieurs sessions démarrent à la fois, le SessionIdSeq pour une est égal à 1, pour un autre est comprises entre 2 et ainsi de suite.
  

