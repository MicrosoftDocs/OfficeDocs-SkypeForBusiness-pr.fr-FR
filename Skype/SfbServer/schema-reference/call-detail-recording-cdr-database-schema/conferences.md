---
title: Table Conferences in Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
ms.openlocfilehash: cbcda30c47b4bbeac012f80d64f297a9a1259f2c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838446"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Table Conferences in Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure de capture de la demande de conférence par l’agent d’cdr. Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de la conférence. Pour plus d’informations, voir la [table ConferenceUris Skype Entreprise Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile pour les conférences périodiques ; chaque instance d’une conférence périodique a le même **ConferenceUri,** mais aura une **confInstance différente.** <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |Numéro d’identification du pool dans lequel la conférence a été capturée. Pour plus [d’informations, voir](pools.md) la table Pools. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Étranger  <br/> |Numéro d’ID permettant d’identifier l’URI de l’organisateur de cette conférence. Pour plus [d’informations, voir](users.md) la table Utilisateurs. <br/> |
|**Indicateur** <br/> |smallint  <br/> || Masque de bits contenant les attributs de conférence. Les valeurs possibles sont les suivantes : <br/>  0X01 <br/>  Synthétique <br/>  Transaction <br/> |
|**Traitée** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   
\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si deux sessions démarrent exactement en même temps, sessionIdSeq pour l’une sera 1 et pour l’autre 2, et ainsi de suite.
  

