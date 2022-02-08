---
title: Table PayloadDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
ms.openlocfilehash: 56241d40be8593a7d5cf5edbf05e8921b2a65ca3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394636"
---
# <a name="payloaddescription-table"></a>Table PayloadDescription
 
La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du codec.  <br/> |
   

