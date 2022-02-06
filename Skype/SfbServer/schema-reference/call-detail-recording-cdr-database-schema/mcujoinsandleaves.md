---
title: Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 'Chaque enregistrement de ce tableau contient des détails sur une combinaison d’utilisateurs qui rejoignent ou quittent le serveur de conférence. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement sera créé pour la jointur de conférence web de cet utilisateur, et un autre sera créé pour la jointur de conférence audio/vidéo de l’utilisateur.'
---

# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau contient des détails sur une combinaison d’utilisateurs qui rejoignent ou quittent le serveur de conférence. Par exemple, si un utilisateur rejoint une conférence qui inclut des conférences web et des éléments audio/vidéo, un enregistrement sera créé pour la jointur de conférence web de cet utilisateur, et un autre sera créé pour la jointur de conférence audio/vidéo de l’utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus [d’informations, voir le tableau Conferences Skype Entreprise Server 2015](conferences.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. Pour plus [d’informations, voir le tableau Conferences Skype Entreprise Server 2015](conferences.md). <br/> |
|**UserId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant cet utilisateur. Pour plus [d’informations, voir la table](users.md) Utilisateurs. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primaire  <br/> |Si un utilisateur est connecté à plusieurs ordinateurs ou appareils à la fois, McuUserInstance identifie de manière unique la combinaison utilisateur/appareil.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Si l’utilisateur se joint à partir d’un RSTN ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro unique identifiant ce serveur de conférence. Pour plus [d’informations, voir le tableau Mcus Skype Entreprise Server 2015](mcus.md). <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Étranger  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Étranger  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur rejoint ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Le moment où cet utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Identificateur qui spécifie le numéro de version du logiciel client utilisé dans la conférence. Pour plus [d’informations, voir le tableau ClientVersions Skype Entreprise Server 2015](clientversions.md). <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

