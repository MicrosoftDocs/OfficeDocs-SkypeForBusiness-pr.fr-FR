---
title: Vue focusjoinsandleaves
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 226460ef-766f-4d61-80cb-f332b65a210d
description: La vue FocusJoinsAndLeaves stocke des informations sur la jointure et laissez des informations pour une conférence. Chaque conférence est représenté dans cet affichage par un enregistrement écrit chaque fois qu’un utilisateur se joint et quitte la conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 3565a9bfbcfd735e4ba6b16facd8e0c88abd4a13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901179"
---
# <a name="focusjoinsandleaves-view"></a>Vue focusjoinsandleaves
 
La vue FocusJoinsAndLeaves stocke des informations sur la jointure et laissez des informations pour une conférence. Chaque conférence est représenté dans cet affichage par un enregistrement écrit chaque fois qu’un utilisateur se joint et quitte la conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de l’instance de la conférence. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier l’instance de la conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |Identificateur unique de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |Version du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**UserClientType** <br/> |int  <br/> |Client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Pour plus d’informations, voir [table UserAgentDef](useragentdef.md) . <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||
|**IsuserInternal** <br/> |bit  <br/> |Bit qui indique si l’utilisateur est un utilisateur interne ou non.  <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Si un utilisateur est connecté plusieurs ordinateurs ou périphériques en même temps, UserInstance sert à identifier de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |ID de boîte de dialogue SIP de la session. Le format est : boîte de dialogue de balise ; pour une balise.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> |Temps que l’utilisateur a rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> |Heure à laquelle l’utilisateur a quitté la conférence.  <br/> |
|**UserRole** <br/> |nvarchar(256)  <br/> |Rôle de l’utilisateur à la conférence, tel que présentateur ou participant.  <br/> |
   

