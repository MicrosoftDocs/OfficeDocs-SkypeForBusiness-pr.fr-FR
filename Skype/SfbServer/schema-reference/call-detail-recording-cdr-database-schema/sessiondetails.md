---
title: Table SessionDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Chaque enregistrement représente une session d’égal à égal, qui peut être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux parties ou tout autre type de session. Vous pouvez effectuer une jointure de tableau avec le tableau multimédia pour trouver les détails de chaque média impliqué dans cette session.
ms.openlocfilehash: 1a211598e7771c5637af191f19ad2926e3cc803e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814902"
---
# <a name="sessiondetails-table"></a>Table SessionDetails
 
Chaque enregistrement représente une session d’égal à égal, qui peut être un appel téléphonique VoIP-VoIP, une session de messagerie instantanée à deux parties ou tout autre type de session. Vous pouvez effectuer une jointure de tableau avec le [tableau multimédia](media.md) pour trouver les détails de chaque média impliqué dans cette session.
  
Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été déplacés de la table SessionDetails utilisée dans Skype entreprise Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. * pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**Corrélation** <br/> |identificateur  <br/> ||Un GUID pour corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Externes  <br/> |Numéro d’identification identifiant la boîte de dialogue qui a été remplacée par la session actuelle. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Externes  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session qui est remplacée par cette session. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**User1Id** <br/> |int  <br/> |Externes  <br/> |ID d’un utilisateur dans la session. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**User2Id** <br/> |int  <br/> |Externes  <br/> |ID de l’autre utilisateur de la session. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**User1EndpointId** <br/> |Identificateur  <br/> ||GUID identifiant le point de terminaison utilisé par le premier utilisateur de la session.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |Identificateur  <br/> ||GUID identifiant le point de terminaison utilisé par le second utilisateur de la session.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Externes  <br/> |URI de l’utilisateur à l’origine de la demande SIP. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**SessionStartedById** <br/> |int  <br/> |Externes  <br/> |ID de l’utilisateur qui a démarré la session. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Externes  <br/> |Indique l’IDENTIFIant de l’utilisateur pour lequel l’appelant a son nom. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**ReferredById** <br/> |int  <br/> |Externes  <br/> |ID de l’utilisateur avec lequel l’appel est soumis. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**ServerId** <br/> |int  <br/> |Externes  <br/> |ID du serveur frontal utilisé pour cette session. Pour plus d’informations, voir la [table serveurs](servers.md) . <br/> |
|**PoolId** <br/> |int  <br/> |Externes  <br/> |ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la [table pools](pools.md) . <br/> |
|**ContentTypeID** <br/> |int  <br/> |Externes  <br/> |Type de contenu utilisé dans la session. Pour plus d’informations, reportez-vous [à la table ContentTypes dans Skype entreprise Server 2015](contenttypes.md) . <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Externes  <br/> |Version du client utilisée par user1. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Externes  <br/> |Version du client utilisée par utilisateur2. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Externes  <br/> |Serveur Edge utilisé par user1. Pour plus d’informations, reportez-vous [à la table EdgeServers dans Skype entreprise Server 2015](edgeservers.md) . <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Externes  <br/> |Serveur Edge utilisé par utilisateur2. Pour plus d’informations, reportez-vous [à la table EdgeServers dans Skype entreprise Server 2015](edgeservers.md) . <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Si User1 est connecté à partir d’une connexion interne ou non.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||L’état d’une connexion interne ou non.  <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations). Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la réponse au premier message d’invitation. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Externes  <br/> |Priorité de l’appel. Pour plus d’informations, reportez-vous [à la table CallPriorities dans Skype entreprise Server 2015](callpriorities.md) . <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par user1 lors de la session.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par utilisateur2 lors de la session.  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure à la fin de la session.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Un ensemble de bits qui indique le type de média de cette session. Voici les définitions des types :  <br/> 1-MESSAGE INSTANTANÉ  <br/> 2-FILE_TRANSFER  <br/> 4 REMOTE_ASSISTANCE  <br/> 8 APP_SHARING  <br/> 16-AUDIO  <br/> 32-VIDÉO  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |type  <br/> ||Un ensemble de bits qui indique les attributs User1. Les définitions d’attribut suivantes apparaissent :  <br/> 0x01-intégré sur le téléphone de bureau  <br/> |
|**User2Flag** <br/> |type  <br/> ||Un ensemble de bits qui indique les attributs utilisateur2. Les définitions d’attribut suivantes apparaissent :  <br/> 0x01-intégré sur le téléphone de bureau  <br/> |
|**CallFlag** <br/> |type  <br/> ||Un ensemble de bits qui indique les attributs d’appel. Les définitions d’attribut suivantes apparaissent :  <br/> 0x01-nouvelle tentative de session  <br/> 0x02-appel émis par l’agent pour le compte d’un groupe de réponse  <br/> |
|**Formé** <br/> |bit  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq de l’une sera 1, et ainsi de suite.
  

