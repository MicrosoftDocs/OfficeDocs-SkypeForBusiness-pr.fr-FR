---
title: Affichage de conférences
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: La vue de conférences stocke des informations sur les conférences. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 98fbf972badeb6cf3b179c8fa408626f2224f5b3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-view"></a>Affichage de conférences
 
La vue de conférences stocke des informations sur les conférences. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de la session. Utilisé en association avec SessionIdSeq pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec SessionIdTime pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de la conférence. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même ConferenceUri mais un ConfInstance différent.  <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> |Heure de fin de la conférence.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a organisé la conférence.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a organisé la conférence. Consultez le [tableau de UriTypes](uritypes.md) pour plus d’informations. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Clients de l’utilisateur qui a organisé la conférence. Consultez le [tableau des locataires](tenants.md) pour plus d’informations. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool qui a hébergé la conférence.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Masque de bits qui contient les attributs de la conférence. Valeurs possibles :  <br/> 0 x 01 - transactions synthétiques  <br/> |
   

