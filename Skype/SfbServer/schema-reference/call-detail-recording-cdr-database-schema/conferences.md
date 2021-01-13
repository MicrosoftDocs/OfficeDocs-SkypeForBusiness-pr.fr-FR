---
title: Table Conferences in Skype for Business Server 2015
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
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813214"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Table Conferences in Skype for Business Server 2015
 
Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure de capture de la demande de conférence par l’agent d’cdr. Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de la conférence. Pour plus d’informations, voir le tableau ConferenceUris dans Skype Entreprise [Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même **ConferenceUri,** mais aura une **confInstance différente.** <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |Numéro d’identification du pool dans lequel la conférence a été capturée. Pour plus [d’informations, voir](pools.md) la table Pools. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Étranger  <br/> |Numéro d’ID permettant d’identifier l’URI de l’organisateur de cette conférence. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**Indicateur** <br/> |smallint  <br/> || Masque de bits contenant les attributs de conférence. Les valeurs possibles sont les suivantes : <br/>  0X01 <br/>  Synthétique <br/>  Transaction <br/> |
|**Traitée** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   
\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si deux sessions démarrent exactement en même temps, sessionIdSeq pour l’une sera 1 et pour l’autre 2, et ainsi de suite.
  

