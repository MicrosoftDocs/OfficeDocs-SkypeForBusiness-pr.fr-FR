---
title: Table McuJoinsAndLeaves dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Chaque enregistrement de cette table contient les détails de l’appel sur une combinaison d’un serveur de conférence ou de congé et de jointure utilisateur. Par exemple, si un utilisateur joint à une conférence qui inclut des fonctionnalités de conférence web et les éléments audio et vidéo, un enregistrement doit être créé pour jointure de conférence web de l’utilisateur, et un autre enregistrement doit être créé pour jointure de conférence audio/vidéo de l’utilisateur.
ms.openlocfilehash: 153da84534dae4a9ad2287c355b93a4477003e6f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient les détails de l’appel sur une combinaison d’un serveur de conférence ou de congé et de jointure utilisateur. Par exemple, si un utilisateur joint à une conférence qui inclut des fonctionnalités de conférence web et les éléments audio et vidéo, un enregistrement doit être créé pour jointure de conférence web de l’utilisateur, et un autre enregistrement doit être créé pour jointure de conférence audio/vidéo de l’utilisateur.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaires et étrangères  <br/> |Heure de l’instance de conférence. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**ID utilisateur** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro unique identifiant l’utilisateur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principal  <br/> |Si un utilisateur est connecté à plusieurs ordinateurs ou périphériques en même temps, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si l’utilisateur joint à partir d’un RTPC ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Primaires et étrangères  <br/> |Numéro unique qui identifie ce serveur de conférence. Consultez le [tableau MCU dans Skype pour Business Server 2015](mcus.md) pour plus d’informations. <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur joint à ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Identificateur qui spécifie le numéro de version du logiciel client utilisent dans la conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

