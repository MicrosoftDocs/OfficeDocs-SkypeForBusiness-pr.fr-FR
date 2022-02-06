---
title: Table Conferences in Skype Entreprise Server 2015
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
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
---

# <a name="conferences-table-in-skype-for-business-server-2015"></a>Table Conferences in Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau contient des détails d’appel sur une conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure à où la demande de conférence a été capturée par l’agent d’cdr. Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Étranger  <br/> |URI de la conférence. Pour plus [d’informations, voir la table ConferenceUris Skype Entreprise Server 2015](conferenceuris.md). <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Utile pour les conférences périodiques ; Chaque instance d’une conférence périodique a le même **ConferenceUri**, mais aura une **confInstance différente**. <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Étranger  <br/> |Numéro d’identification du pool dans lequel la conférence a été capturée. Pour plus [d’informations, voir la table Pools](pools.md) . <br/> |
|**OrganizerId** <br/> |Int  <br/> |Étranger  <br/> |Numéro d’identification pour identifier l’URI de l’organisateur de cette conférence. Pour plus [d’informations, voir la table](users.md) Utilisateurs. <br/> |
|**Indicateur** <br/> |smallint  <br/> || Masque de bits contenant les attributs de conférence. Les valeurs possibles sont les suivantes : <br/>  0X01 <br/>  Synthétique <br/>  Transaction <br/> |
|**Traitée** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ a été introduit dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   
\* Pour la plupart des sessions, SessionIdSeq aura la valeur 1. Si deux sessions démarrent exactement en même temps, sessionIdSeq pour l’une sera 1 et pour l’autre 2, et ainsi de suite.
  

