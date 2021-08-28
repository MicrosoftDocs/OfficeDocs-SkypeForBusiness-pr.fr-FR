---
title: Table Pool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
ms.openlocfilehash: 058bda36020b739388dec63b063402d8891663ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626416"
---
# <a name="pool-table"></a>Table Pool
 
La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom de domaine complet du pool.  <br/> |
   

