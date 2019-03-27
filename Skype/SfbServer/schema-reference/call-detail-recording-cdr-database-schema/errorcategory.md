---
title: Table ErrorCategory dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise les catégories suivantes :'
ms.openlocfilehash: 70322d30b516d003fcac015a4eda7382a13cd2be
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886958"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Table ErrorCategory dans Skype pour Business Server 2015
 
La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise les catégories suivantes :
  
- 0 - Réussite
    
- 1 : échec attendu
    
- 2 - Échec inattendu
    
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique pour la classification.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> || Valeur et le nom convivial attribué à la classification. Les valeurs autorisées sont les suivantes : <br/>  0 - Réussite <br/>  1 : échec attendu <br/>  2 - Échec inattendu <br/> |
   

