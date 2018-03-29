---
title: Vue de FocusJoinsAndLeaves
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vue FocusJoinsAndLeaves stocke des informations sur la jointure et laissez les informations pour une conférence. Chaque conférence est représenté dans ce mode d’affichage par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3ae234977ef541ca523178f41b40f12135b16bfd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-view"></a>Vue de FocusJoinsAndLeaves
 
La vue FocusJoinsAndLeaves stocke des informations sur la jointure et laissez les informations pour une conférence. Chaque conférence est représenté dans ce mode d’affichage par un enregistrement écrit chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de conférence. Utilisé en association avec SessionIdSeq pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé en association avec SessionIdTime pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisée par l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées. Pour plus d’informations, consultez [UserAgentDef table](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur dont les informations de conférence ou d’abandon de jointure a été capturées.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou pas.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un utilisateur est connecté à plusieurs ordinateurs ou périphériques en même temps, UserInstance est utilisé pour identifier de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de boîte de dialogue SIP de la session. Le format est : boîte de dialogue, à partir de balise ; de balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Temps que l’utilisateur rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur quitté la conférence.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rôle de l’utilisateur à la conférence, tels que le présentateur ou participant.  <br/> |
   

