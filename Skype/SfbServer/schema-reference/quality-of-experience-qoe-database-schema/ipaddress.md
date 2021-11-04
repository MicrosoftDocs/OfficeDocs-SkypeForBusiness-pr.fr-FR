---
title: Table IPAddress
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 004bdbbe652a275788293bb42cda2e779b698d65
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756173"
---
# <a name="ipaddress-table"></a>Table IPAddress
 
La table IPAddress mappe les adresses IP à des identificateurs d’adresse IP uniques utilisés dans la base de données Qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primaire  <br/> |Identificateur unique pour l’adresse IP spécifiée.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Uniques  <br/> |Adresse IP unique (par exemple, 189.168.1.1) qui est mappée à IpAddressKey. Il peut d’agir d’une adresse IPv4 ou IPv6.  <br/> |
   

