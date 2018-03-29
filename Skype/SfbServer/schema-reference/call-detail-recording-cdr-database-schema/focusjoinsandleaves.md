---
title: Table FocusJoinsAndLeaves dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Chaque enregistrement de cette table contient les informations de CD-r sur la jointure d’un utilisateur et information sur le congé pour une conférence. Chaque conférence est représenté dans ce tableau par un enregistrement pour chaque fois qu’un utilisateur se joint et quitte la conférence.
ms.openlocfilehash: f07790af63de562672cefc8d8fbd09d75dff1eec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Table FocusJoinsAndLeaves dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient les informations de CD-r sur la jointure d’un utilisateur et information sur le congé pour une conférence. Chaque conférence est représenté dans ce tableau par un enregistrement pour chaque fois qu’un utilisateur se joint et quitte la conférence.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de l’instance de conférence. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**ID utilisateur** <br/> |int  <br/> |Étrangère  <br/> |Numéro unique identifiant cet utilisateur, référencé à partir de la [table des utilisateurs](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un utilisateur est connecté à plusieurs ordinateurs ou périphériques en même temps, **UserInstance** est utilisé pour identifier de manière unique la combinaison utilisateur/périphérique. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si l’utilisateur connecté à partir d’interne ou non.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Rôle de cet utilisateur à la conférence, tels que le présentateur ou participant.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur joint à la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur quitte la conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du logiciel de client de l’utilisateur, référencée dans la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificateur global unique (GUID) du point de terminaison utilisé dans la conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

