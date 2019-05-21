---
title: Table FocusJoinsAndLeaves dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Chaque enregistrement de cette table contient les informations CDR relatives à la jointure d’un utilisateur et laisse des informations pour une seule conférence. Chaque conférence est représentée dans ce tableau par un seul enregistrement pour chaque fois qu’un utilisateur rejoint et quitte la Conférence.
ms.openlocfilehash: 4eb9f6300613fb61a7173be547aa83adf61d1026
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296209"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Table FocusJoinsAndLeaves dans Skype entreprise Server 2015
 
Chaque enregistrement de cette table contient les informations CDR relatives à la jointure d’un utilisateur et laisse des informations pour une seule conférence. Chaque conférence est représentée dans ce tableau par un seul enregistrement pour chaque fois qu’un utilisateur rejoint et quitte la Conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**UserId** <br/> |int  <br/> |Externes  <br/> |Numéro unique identifiant cet utilisateur, référencé dans la [table utilisateurs](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, **UserInstance** est utilisé pour identifier de façon unique la combinaison utilisateur/appareil. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Si l’utilisateur s’est connecté à partir d’une connexion interne ou non.  <br/> |
|**Rôleutilisateur** <br/> |int  <br/> | <br/> |Le rôle de cet utilisateur dans la Conférence, comme le présentateur ou le participant.  <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle l’utilisateur rejoint la Conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle l’utilisateur quitte la Conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externes  <br/> |Version du logiciel client de l’utilisateur, référencée dans la [table ClientVersions dans Skype entreprise Server 2015](clientversions.md).  <br/> |
|**UserEndpointId** <br/> |Identificateur  <br/> ||Identifiant unique global (GUID) du point de terminaison utilisé dans la Conférence.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

