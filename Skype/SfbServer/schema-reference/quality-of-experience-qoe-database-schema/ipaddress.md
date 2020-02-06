---
title: Table IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: La table IPAddress mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809542"
---
# <a name="ipaddress-table"></a>Table IPAddress
 
La table IPAddress mappe les adresses IP aux identificateurs d’adresse IP uniques utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Principal  <br/> |Identificateur unique de l’adresse IP spécifiée.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Différent  <br/> |Une adresse IP unique (par exemple, 189.168.1.1) qui correspond à IpAddressKey. Il peut s’agir d’une adresse IPv4 ou IPv6.  <br/> |
   

