---
title: Table ErrorCategory dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015. Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes :'
ms.openlocfilehash: f3ad3f86a382b900d53c5e86140a46d7f32ca1c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815252"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Table ErrorCategory dans Skype entreprise Server 2015
 
La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015. Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes :
  
- 0--succès
    
- 1-échec imprévu
    
- 2-échec inattendu
    
Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RéfCatégorie** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique de la classification.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> || Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes : <br/>  0--succès <br/>  1-échec imprévu <br/>  2-échec inattendu <br/> |
   

