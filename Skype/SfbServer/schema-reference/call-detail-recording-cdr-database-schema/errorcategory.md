---
title: Table ErrorCategory dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype Entreprise Server 2015. Par défaut, Skype Entreprise Server 2015 utilise les classifications suivantes :'
ms.openlocfilehash: 19fa265b337f293656473aa24c85bb5fc22008de
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743910"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Table ErrorCategory dans Skype Entreprise Server 2015
 
Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype Entreprise Server 2015. Par défaut, Skype Entreprise Server 2015 utilise les classifications suivantes :
  
- 0 : réussite
    
- 1 - Échec attendu
    
- 2 - Échec inattendu
    
Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique pour la classification.  <br/> |
|**Name** <br/> |nvarchar(256)  <br/> || Valeur et nom convivial attribués à la classification. Les valeurs autorisées sont les suivantes : <br/>  0 : réussite <br/>  1 - Échec attendu <br/>  2 - Échec inattendu <br/> |
   

