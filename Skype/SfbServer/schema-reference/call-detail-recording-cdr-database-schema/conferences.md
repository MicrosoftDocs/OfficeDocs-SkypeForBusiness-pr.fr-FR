---
title: Tableau conférences dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Chaque enregistrement de cette table contient les détails des appels sur une conférence.
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296447"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Tableau conférences dans Skype entreprise Server 2015
 
Chaque enregistrement de cette table contient les détails des appels sur une conférence.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Temps d’acquisition de la demande de conférence par l’agent CDR. Utilisé uniquement comme clé primaire pour identifier de manière unique une instance de conférence.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Externes  <br/> |URI de conférence. Pour plus d’informations, reportez-vous [à la table ConferenceUris dans Skype entreprise Server 2015](conferenceuris.md) . <br/> |
|**ConfInstance** <br/> |identificateur  <br/> | <br/> |Utile pour les conférences récurrentes; chaque instance d’une conférence périodique a le même **ConferenceUri**, mais aura un autre **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la Conférence.  <br/> |
|**ConferenceEndTime** <br/> |DateHeure  <br/> | <br/> |Heure de début de la Conférence.  <br/> |
|**PoolId** <br/> |int  <br/> |Externes  <br/> |Numéro d’identification identifiant le regroupement dans lequel la Conférence a été capturée. Pour plus d’informations, voir la [table pools](pools.md) . <br/> |
|**OrganizerId** <br/> |Ent  <br/> |Externes  <br/> |Numéro d’identification identifiant l’URI organisateur de la Conférence. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**Indication** <br/> |type  <br/> || Masque binaire qui contient les attributs de la Conférence. Valeurs possibles : <br/>  0X01 <br/>  Synthetic <br/>  Transaction <br/> |
|**Formé** <br/> |bit  <br/> ||Champ interne utilisé par le service de surveillance.  <br/> Ce champ a été présenté dans Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   
\*Pour la plupart des sessions, SessionIdSeq aura la valeur 1. S’il s’agit d’une session à partir de la même heure, le SessionIdSeq d’une personne sera 1, et pour l’autre, sera égale à 2, et ainsi de suite.
  

