---
title: Table SessionDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Chaque enregistrement représente une session peer-to-peer, qui peut être un appel VoIP-VoIP, session de messagerie instantanée de deux tiers ou tout autre type de session. Vous pouvez effectuer une jointure de tables avec la table de supports pour rechercher les détails de chaque support impliqué dans cette session.
ms.openlocfilehash: 9c6cbe0b69871aa4876777b235d14f8a7ced0e15
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="sessiondetails-table"></a>Table SessionDetails
 
Chaque enregistrement représente une session peer-to-peer, qui peut être un appel VoIP-VoIP, session de messagerie instantanée de deux tiers ou tout autre type de session. Vous pouvez effectuer une jointure de tables avec la [table de supports](media.md) pour rechercher les détails de chaque support impliqué dans cette session.
  
Notez que les IsUser1IntegratedWithDeskPhone et les champs de IsUser2IntegratedWithDeskPhone ont été supprimées de la table SessionDetails utilisée dans Skype pour Business Server 2015.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de façon unique un session.* de voir les [boîtes de dialogue de table dans Skype pour Business Server 2015](dialogs.md) pour plus d’informations. <br/> |
|**ID de corrélation** <br/> |uniqueidentifier  <br/> ||Un GUID pour corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la boîte de dialogue a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **ReplacesDialogIdTime** pour identifier de manière unique une session qui est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**User1Id** <br/> |int  <br/> |Étrangère  <br/> |ID d’un utilisateur dans la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**User2Id** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur dans la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le point de terminaison utilisé par le premier utilisateur dans la session.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le point de terminaison utilisé par le second utilisateur dans la session.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Étrangère  <br/> |L’original à l’utilisateur URI dans la demande SIP. reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur qui a démarré la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étrangère  <br/> |Indique l’ID de l’utilisateur qui a l’appelant est en nom. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ReferredById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur à qui l’appel est appelée. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur frontal utilisé pour cette session. Consultez le [tableau des serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez la [table de regroupements](pools.md) pour plus d’informations. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Étrangère  <br/> |Type de contenu utilisé dans la session. Consultez le [tableau de types de contenus dans Skype pour Business Server 2015](contenttypes.md) pour plus d’informations. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par User1. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par l’utilisateur 2. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Étrangère  <br/> |Serveur de transport Edge utilisé par User1. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Étrangère  <br/> |Serveur de transport Edge utilisé par l’utilisateur 2. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Si User1 est connecté depuis interne ou non.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Si l’utilisateur2 est connecté depuis interne ou non.  <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||L’heure de la première demande d’invitation. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO). Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||L’heure de la réponse vers le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. Si aucun message d’INVITE le champ est renseigné avec la date et l’heure du premier pertinentes SIP message (BYE, Annuler, un MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturée à partir de l’en-tête SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Étrangère  <br/> |Appelez la priorité. Consultez la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md) pour plus d’informations. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par User1 au cours de la session.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par l’utilisateur 2 au cours de la session.  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Temps à la fin de la session.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un ensemble de bits qui indique le type de média de cette session. Vous trouverez les définitions des types :  <br/> 1 - MESSAGERIE INSTANTANÉE  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - AUDIO  <br/> 32 - VIDÉO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs de l’utilisateur1. Les définitions d’attribut suivants sont répertoriées :  <br/> 0 x 01 - intégré à un téléphone de bureau  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs de l’utilisateur2. Les définitions d’attribut suivants sont répertoriées :  <br/> 0 x 01 - intégré à un téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivants sont répertoriées :  <br/> une nouvelle tentative de 0 x 01 - Session  <br/> 0 x 02 - un appel effectué par l’agent pour un groupe de réponse  <br/> |
|**Traitement** <br/> |bit  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si plusieurs sessions démarrent en même temps, la SessionIdSeq pour l’un est égal à 1, pour un autre est 2 et ainsi de suite.
  

