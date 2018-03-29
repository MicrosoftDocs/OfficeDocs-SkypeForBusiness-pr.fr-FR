---
title: Table Conference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: La table est une table de prise en charge. Chaque enregistrement représente une conférence ou une session de peer-to-peer.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Table Conference
 
La table est une table de prise en charge. Chaque enregistrement représente une conférence ou une session de peer-to-peer.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant cet enregistrement de la conférence.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |Conférence URI si il s’agit d’une conférence, ou DialogID si ce est une session peer-to-peer.  <br/> |
|**Somme de contrôle** <br/> |int  <br/> |index  <br/> |Total de contrôle de la conférence URI. Il est utilisé en interne.  <br/> |
|**NextUpdateTS** <br/> |DateHeure  <br/> ||À usage interne uniquement.  <br/> |
   

