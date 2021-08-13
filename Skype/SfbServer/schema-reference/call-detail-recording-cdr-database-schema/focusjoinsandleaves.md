---
title: Table FocusJoinsAndLeaves dans Skype Entreprise Server 2015
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
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Chaque enregistrement de cette table contient les informations d’enregistrement des détails des détails des opérations sur la rejoindre et quitter les informations d’un utilisateur pour une conférence. Chaque conférence est représentée dans ce tableau par un enregistrement chaque fois qu’un utilisateur rejoint et quitte la conférence.
ms.openlocfilehash: 879c4df8dce048820e2d1a23f62ff5c7070611a7e0331cb496a50363aa98f3b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352083"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Table FocusJoinsAndLeaves dans Skype Entreprise Server 2015
 
Chaque enregistrement de cette table contient les informations d’enregistrement des détails des détails des opérations sur la rejoindre et quitter les informations d’un utilisateur pour une conférence. Chaque conférence est représentée dans ce tableau par un enregistrement chaque fois qu’un utilisateur rejoint et quitte la conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’ID pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Étranger  <br/> |Numéro unique identifiant cet utilisateur, référencé à partir de la [table Utilisateurs](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un utilisateur est connecté à plusieurs ordinateurs ou appareils en même temps, **UserInstance** est utilisé pour identifier de manière unique la combinaison utilisateur/appareil. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Que l’utilisateur se soit connecté en interne ou non.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Rôle de cet utilisateur dans la conférence, tel que présentateur ou participant.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à où cet utilisateur rejoint la conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à partir de la fin de la conférence pour cet utilisateur.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Étranger  <br/> |Version du logiciel client de l’utilisateur, référencé à la [table ClientVersions Skype Entreprise Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Identificateur global unique (GUID) du point de terminaison utilisé dans la conférence.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

