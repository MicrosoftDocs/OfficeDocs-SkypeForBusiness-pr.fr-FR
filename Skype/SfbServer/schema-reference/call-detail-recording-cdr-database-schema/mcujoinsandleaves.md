---
title: Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Chaque enregistrement de ce tableau contient des détails d’appel sur une combinaison d’un serveur de conférence et de rejoindre ou quitter un utilisateur. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement sera créé pour la jointur de conférence web de cet utilisateur et un autre sera créé pour la jointur de conférence audio/vidéo de l’utilisateur.
ms.openlocfilehash: df18ca4785fab9b56057eb439ab55caa2b1a170f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737600"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau contient des détails d’appel sur une combinaison d’un serveur de conférence et de rejoindre ou quitter un utilisateur. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement sera créé pour la jointur de conférence web de cet utilisateur et un autre sera créé pour la jointur de conférence audio/vidéo de l’utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant cet utilisateur. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primaire  <br/> |Si un utilisateur est connecté à plusieurs ordinateurs ou appareils à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/appareil.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si l’utilisateur se joint à partir d’un RSTN ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant ce serveur de conférence. Pour plus d’informations, voir le tableau [Mcus Skype Entreprise Server 2015.](mcus.md) <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur rejoint ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Identificateur qui spécifie le numéro de version du logiciel client utilisé dans la conférence. Pour plus [d’informations, voir la table ClientVersions Skype Entreprise Server 2015.](clientversions.md) <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

