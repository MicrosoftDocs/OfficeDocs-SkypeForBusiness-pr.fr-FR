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
ms.localizationpriority: medium
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 5b4cadd741eae999a789a51c6adc0400cc8ce45f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593428"
---
# <a name="conferencemessagecount-view"></a>Affichage ConferenceMessageCount
 
L’affichage ConferenceMessageCount stocke les informations relatives au nombre de messages envoyés par un utilisateur à une conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
> [!NOTE]
> L’affichage ConferenceMessageCount contient toutes les colonnes de la vue [ConferenceSessionDetails](conferencesessiondetails.md) en plus des colonnes répertoriées ci-dessous.
  
|**Colonne**|**Type de données**|**Details**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a envoyé le message.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a envoyé les messages. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Locataire de l’utilisateur qui a envoyé les messages. Pour plus [d’informations, voir le tableau Tenants.](tenants.md) <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Nombre de messages envoyés par l’utilisateur pendant la session de conférence.  <br/> |
   

