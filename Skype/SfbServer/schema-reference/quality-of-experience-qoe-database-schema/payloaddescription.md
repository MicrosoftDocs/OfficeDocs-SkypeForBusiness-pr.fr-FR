---
title: Table PayloadDescription
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
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
ms.openlocfilehash: aa2d2048b61523ed0fab9b8b8796f7b3a29a83dbd1ebb5b5ec800e00520a387e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312982"
---
# <a name="payloaddescription-table"></a>Table PayloadDescription
 
La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du codec.  <br/> |
   

