---
title: Vue conferences
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: L’affichage de conférences stocke des informations sur les conférences. Cet affichage a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 008895e43fb62377f256cb64fdd5f1b24ed0768e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901344"
---
# <a name="conferences-view"></a>Vue conferences
 
L’affichage de conférences stocke des informations sur les conférences. Cet affichage a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé en conjonction avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de conférence. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a le même ConferenceUri, mais une ConfInstance différente.  <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> |Heure de fin de la conférence.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a organisé la conférence.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a organisé la conférence. Consultez la [table UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a organisé la conférence. Consultez le [tableau des clients](tenants.md) pour plus d’informations. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant hébergé la conférence.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Masque de bits qui contient les attributs de la conférence. Valeurs possibles :  <br/> 0 x 01 - Transaction synthétique  <br/> |
   

