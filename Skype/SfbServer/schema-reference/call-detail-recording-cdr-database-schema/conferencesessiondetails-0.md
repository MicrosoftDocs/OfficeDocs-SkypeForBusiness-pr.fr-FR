---
title: Table ConferenceSessionDetails dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Chaque enregistrement représente une session de conférence, ce qui pourrait être la session qui a le Focus ou la session avec un serveur de conférence spécifique.
ms.openlocfilehash: 72f2eb11c79348ad72815be7acfd337a40d288af
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Table ConferenceSessionDetails dans Skype pour Business Server 2015
 
Chaque enregistrement représente une session de conférence, ce qui pourrait être la session qui a le Focus ou la session avec un serveur de conférence spécifique.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateTime  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session ; utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session de la conférence. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session de la conférence. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |Concentrer les URI relatifs à cette session de conférence. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. Cet URI est une URI de conférence basée sur le Focus. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificateur qui fait la distinction entre les instances de conférences périodiques. Chaque instance de conférence périodique a la même ConferenceURI mais une valeur différente de ConfInstance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |Conférence de serveur de conférence URI associé à cette session. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. Cet URI est la conférence basée sur le serveur de conférence URI. Pour les sessions de conférence Focus, cette colonne est null. <br/> |
|**ID utilisateur** <br/> |int  <br/> |Étrangère  <br/> |ID d’un utilisateur dans la session de la conférence. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||Un GUID pour identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur des ordinateurs différents avec le même compte, puis chaque ordinateur aura un ID de point de terminaison différent.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étrangère  <br/> |Indique l’ID de l’utilisateur qui a l’appelant est en nom. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ReferredById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur à qui l’appel est appelée. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par l’utilisateur de la conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par le serveur de conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la boîte de dialogue a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **ReplacesDialogIdTime** pour identifier de manière unique une session qui est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indique si la session est démarrée par la serveur de conférence.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indique si la session est fermée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Si utilisateur est connecté à partir d’interne ou non.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Session Initiation Protocol (SIP) code de réponse à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturée à partir de l’en-tête SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur frontal utilisé pour cette session. Consultez le [tableau des serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez la [table de regroupements](pools.md) pour plus d’informations. <br/> |
|**MediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation à l’aide de l’appel. Consultez le [tableau de MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**GatewayId** <br/> |int  <br/> |Étrangère  <br/> |À l’aide de la passerelle de l’appel. Consultez le [tableau des passerelles dans Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur Edge à l’aide de l’appel. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**ContentTypeId** <br/> |int  <br/> |Étrangère  <br/> |Type de contenu utilisé dans la session. Consultez le [tableau de types de contenus dans Skype pour Business Server 2015](contenttypes.md) pour plus d’informations. <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||L’heure de la première demande d’invitation. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la première réponse SIP. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de la fin de la session.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Étrangère  <br/> |Contient la valeur de type MCU URI à partir de la [table de UriTypes](uritypes.md). Ce champ est utilisé pour améliorer les performances de la requête.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Un ensemble de bits qui indique les attributs de l’utilisateur. Les définitions d’attribut suivants sont répertoriées : <br/>  Intégré à un téléphone de bureau - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivants sont répertoriées : <br/>  Session de nouvelle tentative : 1 <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si plusieurs sessions démarrent en même temps, la SessionIdSeq pour l’un est égal à 1, pour un autre est 2 et ainsi de suite.
  

