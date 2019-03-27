---
title: Vue mcujoinsandleaves
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: La vue McuJoinsAndLeaves stocke des informations sur la participation des utilisateurs et conserver des informations pour un serveur de conférence. Chaque enregistrement dans cet affichage contient des détails des appels sur une combinaison d’un serveur de participation ou laissez et de conférence utilisateur. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: db759e324689cfbad92389f30c8fd632c24ebd5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892807"
---
# <a name="mcujoinsandleaves-view"></a>Vue mcujoinsandleaves
 
La vue McuJoinsAndLeaves stocke des informations sur la participation des utilisateurs et conserver des informations pour un serveur de conférence. Chaque enregistrement dans cet affichage contient des détails des appels sur une combinaison d’un serveur de participation ou laissez et de conférence utilisateur. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de la conférence. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de la conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |L’URI du serveur de conférence qui l’utilisateur connecté.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |L’URI du serveur de conférence qui l’utilisateur connecté. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |L’URI de l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Le type d’URI de l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Le client de l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |La version du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Le client utilisé par l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées. Consultez la [table UserAgentDef](useragentdef.md) pour plus d’informations. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Le nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence server ont été capturées.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |Identifie de manière unique la combinaison utilisateur/périphérique pour les utilisateurs connectés simultanément à plusieurs périphériques.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou non.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de boîte de dialogue SIP de la session. Le format est : boîte de dialogue de balise ; pour une balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Heure à laquelle que l’utilisateur a joint le serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur a quitté le serveur de conférence.  <br/> |
   

