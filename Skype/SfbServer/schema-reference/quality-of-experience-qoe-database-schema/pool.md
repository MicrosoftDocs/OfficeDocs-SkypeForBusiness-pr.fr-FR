---
title: Table Pool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: fb79f21bd78c0c503da920eab04c30f45cdfc3d6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856401"
---
# <a name="pool-table"></a>Table Pool
 
La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom de domaine complet du pool.  <br/> |
   

