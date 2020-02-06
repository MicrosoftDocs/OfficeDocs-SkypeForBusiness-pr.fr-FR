---
title: Affichage conférences
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: L’affichage conférences stocke les informations relatives aux conférences. Cet affichage a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815362"
---
# <a name="conferences-view"></a>Affichage conférences
 
L’affichage conférences stocke les informations relatives aux conférences. Cet affichage a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI de la Conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de la Conférence. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**ConfInstance** <br/> |identificateur  <br/> |Utilisé pour les conférences récurrentes. Chaque instance d’une conférence périodique a le même ConferenceUri qu’une autre ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> |Heure de début de la Conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> |Heure de fin de la Conférence.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |URI de l’utilisateur qui a organisé la Conférence.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Type d’URI de l’utilisateur qui a organisé la Conférence. Pour plus d’informations, voir la [table UriTypes](uritypes.md) . <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Client de l’utilisateur qui a organisé la Conférence. Pour plus d’informations, voir la [table locataires](tenants.md) . <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant hébergé la Conférence.  <br/> |
|**Indication** <br/> |type  <br/> |Masque binaire qui contient les attributs de la Conférence. Valeurs possibles :  <br/> 0X01-transaction synthétique  <br/> |
   

