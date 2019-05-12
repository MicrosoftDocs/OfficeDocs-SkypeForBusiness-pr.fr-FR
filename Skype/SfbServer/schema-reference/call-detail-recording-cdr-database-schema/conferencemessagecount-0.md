---
title: Vue conferencemessagecount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke des informations sur le nombre de messages envoyé par un utilisateur à une conférence. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901414"
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
   

