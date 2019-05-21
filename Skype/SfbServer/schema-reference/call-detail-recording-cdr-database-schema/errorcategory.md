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
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015. Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296286"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Table ErrorCategory dans Skype entreprise Server 2015
 
La table ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype entreprise Server 2015. Par défaut, Skype entreprise Server 2015 utilise les classifications suivantes:
  
- 0--succès
    
- 1-échec imprévu
    
- 2-échec inattendu
    
Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**RéfCatégorie** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique de la classification.  <br/> |
|**Nom** <br/> |nvarchar(256)  <br/> || Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes : <br/>  0--succès <br/>  1-échec imprévu <br/>  2-échec inattendu <br/> |
   

