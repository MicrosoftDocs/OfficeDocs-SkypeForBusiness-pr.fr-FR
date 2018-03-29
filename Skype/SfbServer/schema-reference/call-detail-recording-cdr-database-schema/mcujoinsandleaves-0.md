---
title: Vue de McuJoinsAndLeaves
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vue McuJoinsAndLeaves stocke des informations sur la jointure des utilisateurs et conserver les informations d’un serveur de conférence. Chaque enregistrement dans cette vue contient les détails de l’appel sur une combinaison d’un serveur de conférence ou de congé et de jointure utilisateur. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 77045d852708cd7d8ceb0da473032485e130ea50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-view"></a>Vue de McuJoinsAndLeaves
 
La vue McuJoinsAndLeaves stocke des informations sur la jointure des utilisateurs et conserver les informations d’un serveur de conférence. Chaque enregistrement dans cette vue contient les détails de l’appel sur une combinaison d’un serveur de conférence ou de congé et de jointure utilisateur. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de conférence. Utilisé en association avec SessionIdSeq pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé en association avec SessionIdTime pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |L’URI du serveur de conférence que l’utilisateur connecté.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |L’URI du serveur de conférence que l’utilisateur connecté. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |L’URI de l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Le type de l’URI de l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La version du client utilisée par l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Le client utilisé par l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées. Consultez le [tableau de UserAgentDef](useragentdef.md) pour plus de détails. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Le nom de la catégorie du client utilisé par l’utilisateur dont les informations de jointure ou d’abandon de conferencing server a été capturées.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifie de manière unique la combinaison périphérique/utilisateur pour les utilisateurs connectés simultanément à plusieurs périphériques.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou pas.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de boîte de dialogue SIP de la session. Le format est : boîte de dialogue, à partir de balise ; de balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Heure à laquelle que l’utilisateur joint le serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur que le serveur de conférence à gauche.  <br/> |
   

