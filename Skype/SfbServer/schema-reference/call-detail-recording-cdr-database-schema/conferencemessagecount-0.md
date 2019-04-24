---
title: Vue conferencemessagecount
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213710"
---
# <a name="conferencemessagecount-view"></a>Vue conferencemessagecount
 
L’affichage ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
> [!NOTE]
> L’affichage ConferenceMessageCount contient toutes les colonnes dans la [vue conferencesessiondetails](conferencesessiondetails.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a envoyé le message.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a envoyé les messages. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Client de l’utilisateur qui a envoyé les messages. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Nombre de messages envoyés par l’utilisateur pendant la session de conférence.  <br/> |
   

