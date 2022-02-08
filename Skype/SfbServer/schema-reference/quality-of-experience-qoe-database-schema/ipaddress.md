---
title: Table IPAddress
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 52086b456d9011730252c8c104aba46369467350
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390816"
---
# <a name="ipaddress-table"></a>Table IPAddress
 
La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique pour l’adresse IP spécifiée.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Uniques  <br/> |Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.  <br/> |
   

