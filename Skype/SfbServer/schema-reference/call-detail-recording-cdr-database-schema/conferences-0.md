---
title: Affichage Des conférences
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: L’affichage des conférences fournit des informations relatives aux conférences. Cette vue a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 500a03e85a3339d28227a5b65d5a3c206fc34723
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828627"
---
# <a name="conferences-view"></a>Affichage Des conférences
 
L’affichage des conférences fournit des informations relatives aux conférences. Cette vue a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Détails**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI de la conférence.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Type de l’URI de la conférence. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Utilisé pour les conférences périodiques. Chaque instance d’une conférence périodique a la même valeur ConferenceUri, mais une valeur ConfInstance différente.  <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> |Heure de fin de la conférence.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI de l’utilisateur qui a organisé la conférence.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Type de l’URI de l’utilisateur qui a organisé la conférence. Pour plus [d’informations, voir la table UriTypes.](uritypes.md) <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Locataire de l’utilisateur qui a organisé la conférence. Pour plus [d’informations, voir la table Tenants.](tenants.md) <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Nom de domaine complet du pool ayant hébergé la conférence.  <br/> |
|**Indicateur** <br/> |smallint  <br/> |Masque de bits qui contient les attributs de la conférence. Les valeurs possibles sont les suivantes :  <br/> 0X01 - Transaction synthétique  <br/> |
   

