---
title: Vue de ConferenceMessageCount
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: La vue ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: f0206145217f63e4530d2eac39c7c6533dcf154e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-view"></a>Vue de ConferenceMessageCount
 
La vue ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> La vue ConferenceMessageCount contient toutes les colonnes dans la [vue de le ConferenceSessionDetails](conferencesessiondetails.md) en outre les colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a envoyé le message.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a envoyé les messages. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Clients de l’utilisateur qui a envoyé les messages. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Nombre de messages envoyés par l’utilisateur pendant la session de la conférence.  <br/> |
   

