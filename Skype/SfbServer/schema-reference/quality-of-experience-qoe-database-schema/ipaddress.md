---
title: Table d’adresse IP
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP pour les identificateurs uniques d’adresse IP utilisées ailleurs dans la base de données de qualité. Cette table a été introduite dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Table d’adresse IP
 
La table IPAddress mappe les adresses IP pour les identificateurs uniques d’adresse IP utilisées ailleurs dans la base de données de qualité. Cette table a été introduite dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de l’adresse IP spécifiée.  <br/> |
|**Adresse IP** <br/> |varchar(50)  <br/> |Unique  <br/> |Adresse IP unique (par exemple, 189.168.1.1) qui correspond à la IpAddressKey. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
   

