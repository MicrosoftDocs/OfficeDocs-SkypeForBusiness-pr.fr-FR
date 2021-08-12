---
title: Table ErrorCategory dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'Le tableau ErrorCategory contient le nom convivial de chaque classification de diagnostic Skype Entreprise Server 2015. Par défaut, Skype Entreprise Server 2015 utilise les classifications suivantes :'
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347769"
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
   

