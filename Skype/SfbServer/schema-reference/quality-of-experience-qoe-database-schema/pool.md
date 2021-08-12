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
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
ms.openlocfilehash: e9ad0f0661bbd38a2d1175ab38113585c306baf234bc97e98bf40fca949d0cd9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312972"
---
# <a name="pool-table"></a>Table Pool
 
La table Pool est une table de prise en charge qui contient des informations sur les différents pools frontaux. Chaque enregistrement dans la table représente un pool.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant ce pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom de domaine complet du pool.  <br/> |
   

