---
title: Table des conférences dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de cette table contient les détails de l’appel à propos d’une conférence.
ms.openlocfilehash: f0d90f7abb99bce012e864fa2485386c335de409
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Table des conférences dans Skype pour Business Server 2015
 
Chaque enregistrement de cette table contient les détails de l’appel à propos d’une conférence.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure à laquelle la demande de la conférence a été capturée par l’agent de CD-r. Utilisé uniquement en tant que clé primaire pour identifier de manière unique une instance de la conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étrangère  <br/> |Conférence URI. Consultez la [table ConferenceUris dans Skype pour Business Server 2015](conferenceuris.md) pour plus d’informations. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même **ConferenceUri**, mais il aura une autre **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Étrangère  <br/> |Numéro d’ID pour identifier le pool dans lequel la conférence a été capturée. Consultez la [table de regroupements](pools.md) pour plus d’informations. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Étrangère  <br/> |Numéro d’identification pour identifier l’URI de cette conférence de l’organisateur. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**Indicateur** <br/> |smallint  <br/> || Un masque de bits qui contient les attributs de la conférence. Valeurs possibles : <br/>  0 x 01 <br/>  Synthétique <br/>  Transaction <br/> |
|**Traitement** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq a la valeur 1. Si deux sessions commencent à exactement au même moment, le SessionIdSeq pour une est égal à 1, et pour l’autre est 2 et ainsi de suite.
  

