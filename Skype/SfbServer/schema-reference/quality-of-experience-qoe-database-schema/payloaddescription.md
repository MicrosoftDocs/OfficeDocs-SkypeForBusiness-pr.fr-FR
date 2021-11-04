---
title: Table PayloadDescription
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 02fb4b00bfa0067078cfd7ff3f4df71ea0a82f50
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767282"
---
# <a name="payloaddescription-table"></a>Table PayloadDescription
 
La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du codec.  <br/> |
   

