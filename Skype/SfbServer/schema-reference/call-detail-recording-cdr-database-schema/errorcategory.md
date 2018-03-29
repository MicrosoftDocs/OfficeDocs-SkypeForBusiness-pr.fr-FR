---
title: Table ErrorCategory dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise des classifications suivantes :'
ms.openlocfilehash: 23df7ecb7e10dc104e6274edb762369ad539f8fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Table ErrorCategory dans Skype pour Business Server 2015
 
La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise des classifications suivantes :
  
- 0 - Réussite
    
- 1--échec attendu
    
- 2 - arrêt
    
Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**Code catégorie** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique pour la classification.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> || Valeur et le nom convivial attribué à la classification. Les valeurs autorisées sont les suivantes : <br/>  0 - Réussite <br/>  1--échec attendu <br/>  2 - arrêt <br/> |
   

