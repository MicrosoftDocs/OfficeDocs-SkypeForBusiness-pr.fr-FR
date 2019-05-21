---
title: Table McuJoinsAndLeaves dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: Chaque enregistrement de cette table contient les détails de l’appel d’une combinaison d’une jointure utilisateur ou d’un serveur de conférence. Par exemple, si un utilisateur rejoint une conférence incluant des conférences Web et des éléments audio ou vidéo, un enregistrement sera créé pour la participation à la conférence Web de cet utilisateur et un autre enregistrement serait créé pour la participation de l’utilisateur à la conférence audio/vidéo.
ms.openlocfilehash: d61b3c1ef1aa6fe481a4022f7bc434b523b68213
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296069"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>Table McuJoinsAndLeaves dans Skype entreprise Server 2015
 
Chaque enregistrement de cette table contient les détails de l’appel d’une combinaison d’une jointure utilisateur ou d’un serveur de conférence. Par exemple, si un utilisateur rejoint une conférence incluant des conférences Web et des éléments audio ou vidéo, un enregistrement sera créé pour la participation à la conférence Web de cet utilisateur et un autre enregistrement serait créé pour la participation de l’utilisateur à la conférence audio/vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Etranger principal  <br/> |Numéro unique identifiant cet utilisateur. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**McuUserInstance** <br/> |int  <br/> |Principal  <br/> |Si un utilisateur ouvre une session sur plusieurs ordinateurs ou appareils en même temps, McuUserInstance identifie de façon unique la combinaison utilisateur/appareil.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |Le fait que l’utilisateur se connecte à partir d’un réseau PSTN ou non.  <br/> |
|**McuId** <br/> |int  <br/> |Etranger principal  <br/> |Numéro unique identifiant ce serveur de conférence. Pour plus d’informations, reportez-vous [à la table MCU dans Skype entreprise Server 2015](mcus.md) . <br/> |
|**DialogSessionIdTime** <br/> |DateHeure  <br/> |Externes  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Externes  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**UserJoinTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle l’utilisateur rejoint ce serveur de conférence.  <br/> |
|**UserLeaveTime** <br/> |DateHeure  <br/> | <br/> |Heure à laquelle l’utilisateur quitte ce serveur de conférence.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Externes  <br/> |Identificateur spécifiant le numéro de version de l’utilisation du logiciel client dans la Conférence. Pour plus d’informations, reportez-vous [à la table ClientVersions dans Skype entreprise Server 2015](clientversions.md) . <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

