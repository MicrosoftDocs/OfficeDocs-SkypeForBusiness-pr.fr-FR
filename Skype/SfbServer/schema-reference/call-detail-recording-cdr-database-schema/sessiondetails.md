---
title: Table SessionDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: Chaque enregistrement représente une session d’égal à égal ; il peut s’agir d’un appel téléphonique VoIP-VoIP, d’une session de messagerie instantanée à deux participants ou de tout autre type de session. Vous pouvez effectuer une jointage de table avec la table Media pour rechercher les détails de chaque média impliqué dans cette session.
ms.openlocfilehash: 830e6e2266d77487848c4e49daeaa8462460c2dc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615510"
---
# <a name="sessiondetails-table"></a>Table SessionDetails
 
Chaque enregistrement représente une session d’égal à égal ; il peut s’agir d’un appel téléphonique VoIP-VoIP, d’une session de messagerie instantanée à deux participants ou de tout autre type de session. Vous pouvez effectuer une jointage de table avec la [table Media](media.md) pour rechercher les détails de chaque média impliqué dans cette session.
  
Notez que les champs IsUser1IntegratedWithDeskPhone et IsUser2IntegratedWithDeskPhone ont été supprimés de la table SessionDetails utilisée dans Skype Entreprise Server 2015.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session.* Pour plus d’informations, voir la table Dialogs Skype Entreprise Server [2015.](dialogs.md) <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||GUID permettant de corréler plusieurs sessions.  <br/> |
|**ReplaceDialogIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Numéro d’ID permettant d’identifier le dialogue remplacé par la session actuelle. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **ReplacesDialogIdTime** pour identifier de manière unique une session remplacée par cette session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**User1Id** <br/> |int  <br/> |Étranger  <br/> |ID d’un utilisateur dans la session. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**User2Id** <br/> |int  <br/> |Étranger  <br/> |ID de l’autre utilisateur dans la session. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le système d’extrémité utilisé par le premier utilisateur dans la session.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||GUID qui identifie le système d’extrémité utilisé par le deuxième utilisateur dans la session.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**TargetUserId** <br/> |int  <br/> |Étranger  <br/> |URI de l’utilisateur « À » d’origine dans la demande SIP. pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**SessionStartedById** <br/> |int  <br/> |Étranger  <br/> |ID de l’utilisateur ayant démarré la session. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |Étranger  <br/> |Indique l’ID de l’utilisateur pour le compte duquel l’appelant appelle. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**ReferredById** <br/> |int  <br/> |Étranger  <br/> |ID de l’utilisateur faisant référence à l’appel. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**ServerId** <br/> |int  <br/> |Étranger  <br/> |ID du serveur frontal utilisé pour cette session. Pour plus [d’informations, voir](servers.md) la table Servers. <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |ID du pool dans lequel la session a été capturée. Pour plus [d’informations, voir](pools.md) la table Pools. <br/> |
|**ContentTypeID** <br/> |int  <br/> |Étranger  <br/> |Type de contenu utilisé dans la session. Pour plus d’informations, voir la [table ContentTypes Skype Entreprise Server 2015.](contenttypes.md) <br/> |
|**User1ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Version de client utilisée par User1. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**User2ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Version de client utilisée par User2. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |Étranger  <br/> |Serveur Edge utilisé par User1. Pour plus d’informations, voir la [table EdgeServers Skype Entreprise Server 2015.](edgeservers.md) <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |Étranger  <br/> |Serveur Edge utilisé par User2. Pour plus d’informations, voir la [table EdgeServers Skype Entreprise Server 2015.](edgeservers.md) <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||Indique si User1 est connecté en interne.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||Indique si User2 est connecté en interne.  <br/> |
|**InviteTime** <br/> |DateHeure  <br/> ||Heure de la première demande INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO). Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseTime** <br/> |DateHeure  <br/> ||Heure de la réponse au premier message INVITE. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||ID de diagnostic capturé à partir de l’en-tête SIP.  <br/> |
|**CallPriority** <br/> |int  <br/> |Étranger  <br/> |Priorité de l’appel. Pour plus d’informations, voir la [table CallPriorities Skype Entreprise Server 2015.](callpriorities.md) <br/> |
|**User1MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par User1 durant la session.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||Nombre de messages envoyés par User2 durant la session.  <br/> |
|**SessionEndTime** <br/> |DateHeure  <br/> ||Heure de fin de la session.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||Jeu de bits qui indique le type de média de cette session. Voici les définitions des types :  <br/> 1 - Messagerie instantanée  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- AUDIO  <br/> 32- VIDEO  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||Jeu de bits qui indique les attributs de User1. Les définitions d’attributs suivantes sont répertoriées :  <br/> 0x01 - Intégré dans téléphone de bureau  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||Jeu de bits qui indique les attributs de User2. Les définitions d’attributs suivantes sont répertoriées :  <br/> 0x01 - Intégré dans téléphone de bureau  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||Jeu de bits qui indique les attributs de l’appel. Les définitions d’attributs suivantes sont répertoriées :  <br/> 0x01 - Nouvelle tentative de session  <br/> 0x02 - Appel effectué par un agent pour le compte d’un groupe de réponse  <br/> |
|**Traitée** <br/> |bit  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   
\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si plusieurs sessions démarrent exactement en même temps, le SessionIdSeq sera 1 pour l’une, 2 pour un autre, et ainsi de suite.
  

