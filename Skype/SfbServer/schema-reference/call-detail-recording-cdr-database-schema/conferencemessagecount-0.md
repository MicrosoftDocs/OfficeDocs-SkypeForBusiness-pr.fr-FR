---
title: Affichage ConferenceMessageCount
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: f3ec657147967a783cbe27a7a78acd6dd0fbfbb9b260d3673bcda0bdf353e5fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322966"
---
# <a name="conferencemessagecount-view"></a>Affichage ConferenceMessageCount
 
L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> L’affichage ConferenceMessageCount contient toutes les colonnes de la vue [ConferenceSessionDetails](conferencesessiondetails.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a envoyé le message.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a envoyé les messages. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Locataire de l’utilisateur qui a envoyé les messages. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Nombre de messages envoyés par l’utilisateur pendant la session de conférence.  <br/> |
   

