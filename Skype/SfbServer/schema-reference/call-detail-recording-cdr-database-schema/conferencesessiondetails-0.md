---
title: Table ConferenceSessionDetails dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.
ms.openlocfilehash: 087dd056dae0041ab63934b25038672a74410343
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759446"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>Table ConferenceSessionDetails dans Skype Entreprise Server 2015
 
Chaque enregistrement représente une session de conférence. Il peut s’agir de la session avec le service Focus ou de celle avec un serveur de conférence spécifique.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session ; utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session de conférence. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une session de conférence. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de conférence Focus associée à cette session. Pour plus d’informations, voir la [table ConferenceUris Skype Entreprise Server 2015.](conferenceuris.md) Il s’agit d’une URI de conférence Focus. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||Identificateur permettant de différencier les instances des conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceURI, mais une valeur ConfInstance différente.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de conférence de serveur de conférence associée à cette session. Pour plus d’informations, voir la [table ConferenceUris Skype Entreprise Server 2015.](conferenceuris.md) Il s’agit de l’URI de conférence basée sur le serveur de conférence. Pour les sessions de conférence Focus, cette colonne sera nulle. <br/> |
|**UserId** <br/> |int  <br/> |Étranger  <br/> |ID d’un utilisateur dans la session de conférence. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||GUID permettant d’identifier l’instance de point de terminaison. Par exemple, si un utilisateur ouvre une session sur différents ordinateurs avec le même compte, chaque ordinateur aura un ID de point de terminaison différent.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étranger  <br/> |Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**ReferredById** <br/> |int  <br/> |Étranger  <br/> |ID de l’utilisateur faisant référence à l’appel. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |Étranger  <br/> |Version de client utilisée par l’utilisateur de conférence. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |Étranger  <br/> |Version de client utilisée par le serveur de conférence. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session remplacée par cette session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||Indique si la session est démarrée par le serveur de conférence ?  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||Indique si la session est terminée par le serveur de conférence.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||Indique si l’utilisateur est connecté en interne.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP (Session Initiation Protocol) à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**ServerId** <br/> |int  <br/> |Étranger  <br/> |ID du serveur frontal utilisé pour cette session. Pour plus [d’informations, voir](servers.md) la table Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |ID du pool dans lequel la session a été capturée. Pour plus [d’informations, voir](pools.md) la table Pools. <br/> |
|**MediationServerId** <br/> |int  <br/> |Étranger  <br/> |Serveur de médiation utilisé par l’appel. Pour plus [d’informations, voir la table MediationServers.](mediationservers.md) <br/> |
|**GatewayId** <br/> |int  <br/> |Étranger  <br/> |Passerelle utilisée par l’appel. Pour plus [d’informations, voir le tableau Gateways Skype Entreprise Server 2015.](gateways.md) <br/> |
|**EdgeServerId** <br/> |int  <br/> |Étranger  <br/> |Serveur Edge utilisé par l’appel. Pour plus d’informations, voir la [table EdgeServers Skype Entreprise Server 2015.](edgeservers.md) <br/> |
|**ContentTypeId** <br/> |int  <br/> |Étranger  <br/> |Type de contenu utilisé dans la session. Pour plus d’informations, voir la [table ContentTypes Skype Entreprise Server 2015.](contenttypes.md) <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure du premier message SIP RESPONSE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |Étranger  <br/> |Contient la valeur de type d’URI MCU de la [table UriTypes.](uritypes.md) Ce champ sert à améliorer les performances des requêtes.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || Jeu de bits qui indique les attributs de l’utilisateur. Les définitions d’attributs suivantes sont répertoriées : <br/>  Intégré avec téléphone de bureau - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées : <br/>  Nouvelle tentative de session - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   
\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.
  

