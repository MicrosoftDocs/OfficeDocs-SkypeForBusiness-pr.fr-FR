---
title: Table NetworkConnectionDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: 6df2511c2dfee0158b4633be5dfa8549639cfc6d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212389"
---
# <a name="networkconnectiondetail-table"></a>Table NetworkConnectionDetail
 
La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique pour le type de connexion réseau.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |Type de connexion réseau qui correspond à la NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :  <br/> 0--filaire  <br/> 1--Wi-Fi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--autres  <br/> 5--tunnel  <br/> |
   

