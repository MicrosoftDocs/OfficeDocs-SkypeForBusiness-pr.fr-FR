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
ms.localizationpriority: medium
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
ms.openlocfilehash: dedbf806c6cda1ce174e1a3282b81a409b63bced
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610561"
---
# <a name="payloaddescription-table"></a>Table PayloadDescription
 
La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du codec.  <br/> |
   

