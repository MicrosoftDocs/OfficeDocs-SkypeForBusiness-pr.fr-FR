---
title: Affichage ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815382"
---
# <a name="conferencemessagecount-view"></a>Affichage ConferenceMessageCount
 
Le mode ConferenceMessageCount stocke les informations sur le nombre de messages envoyés par un utilisateur à une conférence. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
> [!NOTE]
> Le mode ConferenceMessageCount contient toutes les colonnes de la [vue ConferenceSessionDetails](conferencesessiondetails.md) , en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a envoyé le message.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |identificateur  <br/> |Client de l’utilisateur qui a envoyé les messages. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**UserMessageCount** <br/> |type  <br/> |Nombre de messages envoyés par l’utilisateur au cours de la session de conférence.  <br/> |
   

