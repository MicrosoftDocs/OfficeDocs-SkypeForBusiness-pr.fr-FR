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
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806294"
---
# <a name="payloaddescription-table"></a>Table PayloadDescription
 
La table PayloadDescription est une table de prise en charge. Chaque enregistrement représente un codec utilisé dans une session audio ou vidéo.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique identifiant le codec.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Uniques  <br/> |Nom du codec.  <br/> |
   

