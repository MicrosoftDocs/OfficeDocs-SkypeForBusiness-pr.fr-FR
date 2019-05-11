---
title: Table McuJoinsAndLeaves dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Chaque enregistrement de cette table contient des détails des appels sur une combinaison d’un serveur de participation ou laissez et de conférence utilisateur. Par exemple, si un utilisateur joint à une conférence qui inclut les éléments audio/vidéo et conférence web, un enregistrement doit être créé pour participer à une conférence de l’utilisateur web et un autre enregistrement doit être créé pour participer à une conférence audio/vidéo de l’utilisateur.
ms.openlocfilehash: d6bcd51e9c0e5832939004647348abe7368a2e43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930296"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient des détails des appels sur une combinaison d’un serveur de participation ou laissez et de conférence utilisateur. Par exemple, si un utilisateur joint à une conférence qui inclut les éléments audio/vidéo et conférence web, un enregistrement doit être créé pour participer à une conférence de l’utilisateur web et un autre enregistrement doit être créé pour participer à une conférence audio/vidéo de l’utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de la conférence. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier l’instance de la conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant cet utilisateur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principal  <br/> |Si un utilisateur est connecté plusieurs ordinateurs ou périphériques en une seule fois, McuUserInstance identifie de manière unique la combinaison utilisateur/périphérique.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si l’utilisateur provient d’un réseau RTC ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant ce serveur de conférence. Consultez le [tableau MCU Skype pour Business Server 2015](mcus.md) pour plus d’informations. <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Étrangère  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur joint à ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle que cet utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étrangère  <br/> |Identificateur qui spécifie le numéro de version du logiciel client utiliser à la conférence. Consultez la [table ClientVersions dans Skype pour Business Server 2015](clientversions.md) pour plus d’informations. <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

