---
title: Table Pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Le tableau de Pool est une table de prise en charge qui stocke des informations sur les différents pools frontaux. Chaque enregistrement de la table représente un pool.
ms.openlocfilehash: c4451f274e9afadbb7903e4095be22120c430689
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920061"
---
# <a name="pool-table"></a>Table Pool
 
Le tableau de Pool est une table de prise en charge qui stocke des informations sur les différents pools frontaux. Chaque enregistrement de la table représente un pool.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant ce pool.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Unique  <br/> |Nom de domaine complet de pool.  <br/> |
   

