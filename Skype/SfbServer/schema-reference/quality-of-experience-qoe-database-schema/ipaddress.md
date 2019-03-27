---
title: Table IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe des adresses IP pour les identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876957"
---
# <a name="ipaddress-table"></a>Table IPAddress
 
La table IPAddress mappe des adresses IP pour les identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de l’adresse IP spécifiée.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Unique  <br/> |Adresse IP unique (par exemple, 189.168.1.1) qui correspond à la IpAddressKey. Cela peut être soit une adresse IPv4 ou IPv6.  <br/> |
   

