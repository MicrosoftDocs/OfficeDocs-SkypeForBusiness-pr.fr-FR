---
title: Tableau des conférences dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de cette table contient des détails des appels sur une conférence.
ms.openlocfilehash: f0401c150f3835772ba0df20f8c02c64c9919921
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213262"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tableau des conférences dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient des détails des appels sur une conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure à laquelle la demande de conférence a été capturée par l’agent CDR. Utilisé uniquement comme une clé primaire pour identifier de manière unique une instance de la conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |URI de conférence. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile pour les conférences périodique ; chaque instance d’une conférence périodique a le même **ConferenceUri**, mais il aura une autre **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier le pool dans lequel la conférence ont été capturée. Consultez le [tableau de Pools](pools.md) pour plus d’informations. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier l’organisateur URI de cette conférence. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**Indicateur** <br/> |smallint  <br/> || Un masque de bits qui contient les attributs de la conférence. Valeurs possibles : <br/>  0 x 01 <br/>  Synthétique <br/>  Transaction <br/> |
|**Traités** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ est une nouveauté dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions SessionIdSeq aura la valeur 1. Si deux sessions démarrent exactement au même moment, le SessionIdSeq pour une est égal à 1, et pour l’autre est comprises entre 2 et ainsi de suite.
  

