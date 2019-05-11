---
title: Table FocusJoinsAndLeaves dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Chaque enregistrement de cette table contient les informations de détails sur la participation d’un utilisateur et les informations de congé pour une conférence. Chaque conférence est représenté dans ce tableau par un enregistrement pour chaque fois qu’un utilisateur se joint et quitte la conférence.
ms.openlocfilehash: 8767b72163be4b90fb06950d3eca33bbe9d9974c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901121"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Table FocusJoinsAndLeaves dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient les informations de détails sur la participation d’un utilisateur et les informations de congé pour une conférence. Chaque conférence est représenté dans ce tableau par un enregistrement pour chaque fois qu’un utilisateur se joint et quitte la conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de la conférence. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier l’instance de la conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Étrangère  <br/> |Numéro unique identifiant cet utilisateur, référencé à partir de la [table des utilisateurs](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un utilisateur est connecté plusieurs ordinateurs ou périphériques en même temps, **UserInstance** sert à identifier de manière unique la combinaison utilisateur/périphérique. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si l’utilisateur connecté en interne ou non.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Rôle de cet utilisateur à la conférence, tel que présentateur ou participant.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur quitte la conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Version du logiciel client de l’utilisateur, référencée dans la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificateur global unique (GUID) du point de terminaison utilisé dans la conférence.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

