---
title: Table DeRegisterType dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des utilisateurs possible enregistre des types, tels que « client ouverte », « inscription expiré » ou 'client a cessé de répondre.'
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Table DeRegisterType dans Skype pour Business Server 2015
 
La table DeRegisterType est une table statique qui stocke la liste des utilisateurs possible enregistre des types, tels que « client ouverte », « inscription expiré » ou 'client a cessé de répondre.'
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0--inconnu <br/>  1--annulation d’enregistrement initié par le client <br/>  2 – l’enregistrement a expiré. <br/>  3 - le client est tombé en panne <br/>  4--les attributs utilisateur modifiés <br/>  5 - Registrar par défaut modifié <br/>  6--Client hérité mode de survie <br/> |
   

