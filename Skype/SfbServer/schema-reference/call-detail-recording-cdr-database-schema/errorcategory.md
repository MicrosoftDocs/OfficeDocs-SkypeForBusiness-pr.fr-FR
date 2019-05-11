---
title: Table ErrorCategory dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial pour chaque Skype pour la classification de diagnostic Business Server 2015. Par défaut, Skype pour Business Server 2015 utilise les catégories suivantes :'
ms.openlocfilehash: b6226396302353b815138b41b7c19f170a0d6b4d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901086"
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
   

