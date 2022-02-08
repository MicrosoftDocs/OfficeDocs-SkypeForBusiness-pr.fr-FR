---
title: Table NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: d41b89ce85ee365d883c2224f2da29fca3cab926
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394706"
---
# <a name="networkconnectiondetail-table"></a>Table NetworkConnectionDetail
 
La table NetworkConnectionDetail mappe des types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données Qualité de l’expérience (QoE). Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primaire  <br/> |Identificateur unique du type de connexion réseau.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Uniques  <br/> |Type de connexion réseau correspondant à la valeur NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :
  <br/> 0 -- Câblé  <br/> 1 -- WiFi  <br/> 2 -- Ethernet  <br/> 3 -- MobileBB  <br/> 4 -- Autre  <br/> 5 -- Tunnel  <br/> |
   

