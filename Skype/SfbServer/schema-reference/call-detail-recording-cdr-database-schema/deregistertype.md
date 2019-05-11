---
title: Table DeRegisterType dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901172"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Table DeRegisterType dans Skype pour Business Server 2015
 
La table DeRegisterType est une table statique qui stocke la liste des utilisateurs enregistre différents types, tels que l’initiative du client, « expiration de l’inscription » ou « client ne répond plus ».
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valeurs autorisées : <br/>  0 : inconnu <br/>  1--initiative du client désinscription <br/>  2--expiration de l’inscription <br/>  3 - client bloqué <br/>  4--modifié des attributs utilisateur <br/>  5 - serveurs d’inscriptions par défaut modifié <br/>  6--De Client hérité en Mode survie <br/> |
   

