---
title: Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Chaque enregistrement de ce tableau contient des détails d’appel sur une combinaison d’un serveur de conférence et de rejoindre ou quitter un utilisateur. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement est créé pour la rejoindre, et un autre est créé pour la jointur de conférence audio/vidéo de l’utilisateur.
ms.openlocfilehash: 8c9e6cba970e113d119ab3ce894dee8d5b4f6b28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821494"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau contient des détails d’appel sur une combinaison d’un serveur de conférence et de rejoindre ou quitter un utilisateur. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement est créé pour la rejoindre, et un autre est créé pour la jointur de conférence audio/vidéo de l’utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau Conférences dans Skype Entreprise [Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant cet utilisateur. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primaire  <br/> |Si un utilisateur est connecté à plusieurs ordinateurs ou appareils à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/appareil.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si l’utilisateur se joint à partir d’un RSTN ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant ce serveur de conférence. Pour plus [d’informations, voir le tableau Mcus dans Skype Entreprise Server 2015.](mcus.md) <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus d’informations, voir le tableau Dialogs dans Skype Entreprise [Server 2015.](dialogs.md) <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur rejoint ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Identificateur qui spécifie le numéro de version du logiciel client utilisé dans la conférence. Pour plus d’informations, voir le tableau ClientVersions dans Skype Entreprise [Server 2015.](clientversions.md) <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

