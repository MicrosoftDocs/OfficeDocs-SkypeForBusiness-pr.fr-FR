---
title: Table SessionDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Chaque enregistrement représente une session d’égal à égal, qui peut être un appel VoIP-VoIP, par messagerie instantanée deux ou tout autre type de session. Vous pouvez effectuer une jointure de tables avec la table Media pour rechercher les détails de chaque support impliqué dans cette session.
ms.openlocfilehash: e499c8d443742bacfcdbe9c129e884cae4dd96a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889923"
---
# <a name="sessiondetails-table"></a>Table SessionDetails
 
Chaque enregistrement représente une session d’égal à égal, qui peut être un appel VoIP-VoIP, par messagerie instantanée deux ou tout autre type de session. Vous pouvez effectuer une jointure de tables avec la [table Media](media.md) pour rechercher les détails de chaque support impliqué dans cette session.
  
Notez que le IsUser1IntegratedWithDeskPhone et les champs IsUser2IntegratedWithDeskPhone ont été supprimés de la table SessionDetails utilisée dans Skype pour Business Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique un session.*, voir le [tableau Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ID de corrélation** <br/> |uniqueidentifier  <br/> ||GUID permettant de corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la boîte de dialogue qui a été remplacée par la session en cours. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session est remplacée par cette session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**User1Id** <br/> |int  <br/> |Étrangère  <br/> |ID d’un utilisateur dans la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**User2Id** <br/> |int  <br/> |Étrangère  <br/> |ID de l’autre utilisateur dans la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le point de terminaison utilisé par le premier utilisateur dans la session.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le point de terminaison utilisé par le deuxième utilisateur dans la session.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Étrangère  <br/> |L’original à l’URI de l’utilisateur dans la demande SIP. reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur ayant démarré la session. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étrangère  <br/> |Indique l’ID de l’utilisateur qui est l’appelant part. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ReferredById** <br/> |int  <br/> |Étrangère  <br/> |ID de l’utilisateur à qui l’appel est appelé. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**ServerId** <br/> |int  <br/> |Étrangère  <br/> |ID du serveur frontal utilisé pour cette session. Consultez le [tableau de serveurs](servers.md) pour plus d’informations. <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |ID du pool dans lequel la session a été capturée. Consultez le [tableau de Pools](pools.md) pour plus d’informations. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Étrangère  <br/> |Type de contenu utilisé dans la session. Voir la [table ContentTypes dans Skype pour Business Server 2015](contenttypes.md) pour plus d’informations. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par User1. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du client utilisée par l’utilisateur 2. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Étrangère  <br/> |Serveur Edge utilisé par User1. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Étrangère  <br/> |Serveur Edge utilisé par l’utilisateur 2. Consultez la [table EdgeServers dans Skype pour Business Server 2015](edgeservers.md) pour plus d’informations. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Indique si User1 est connecté en interne ou non.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Indique si User2 est connecté en interne ou non.  <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO). Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la réponse pour le premier message d’INVITE. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP à l’invitation de session. Ce champ est généralement rempli avec des données générées à partir du message d’invitation initial dans la session. S’il n’existe aucun message INVITE le champ est renseigné avec la date et l’heure du premier pertinent message SIP (BYE, Annuler, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Étrangère  <br/> |Priorité d’appel. Consultez la [table CallPriorities dans Skype pour Business Server 2015](callpriorities.md) pour plus d’informations. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par User1 durant la session.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par User2 durant la session.  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un ensemble de bits qui indique le type de média de cette session. Vous trouverez les définitions des types :  <br/> 1 - MESSAGERIE INSTANTANÉE  <br/> 2 - FILE_TRANSFER  <br/> 4 - REMOTE_ASSISTANCE  <br/> 8 - APP_SHARING  <br/> 16 - AUDIO  <br/> 32 - VIDÉO  <br/> 64 - APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs User1. Les définitions d’attribut suivants sont répertoriées :  <br/> 0 x 01 - intégré avec le téléphone de bureau  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs de l’utilisateur 2. Les définitions d’attribut suivants sont répertoriées :  <br/> 0 x 01 - intégré avec le téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Un ensemble de bits qui indique les attributs de l’appel. Les définitions d’attribut suivants sont répertoriées :  <br/> 0 x 01 - nouvelle tentative de Session  <br/> 0 x 02 - appel effectué par un agent au nom d’un groupe de réponses  <br/> |
|**Traités** <br/> |bit  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions SessionIdSeq aura la valeur 1. Si plusieurs sessions démarrent à la fois, le SessionIdSeq pour une est égal à 1, pour un autre est comprises entre 2 et ainsi de suite.
  

