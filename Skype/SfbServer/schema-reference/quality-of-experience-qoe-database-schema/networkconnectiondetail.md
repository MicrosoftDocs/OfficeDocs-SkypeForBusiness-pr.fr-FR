---
title: Table NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: d6e8bf04c8426a6278528de90f383c9867f92c8b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626446"
---
# <a name="networkconnectiondetail-table"></a>Table NetworkConnectionDetail
 
La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique du type de connexion réseau.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Uniques  <br/> |Type de connexion réseau correspondant à la valeur NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :
  <br/> 0 -- Câblé  <br/> 1 -- WiFi  <br/> 2 -- Ethernet  <br/> 3 -- MobileBB  <br/> 4 -- Autre  <br/> 5 -- Tunnel  <br/> |
   

