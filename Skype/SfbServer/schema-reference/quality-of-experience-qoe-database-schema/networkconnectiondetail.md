---
title: Table NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919990"
---
# <a name="networkconnectiondetail-table"></a>Table NetworkConnectionDetail
 
La table NetworkConnectionDetail mappe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’expérience. Ce tableau a été introduit dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique pour le type de connexion réseau.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Unique  <br/> |Type de connexion réseau qui correspond à la NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :  <br/> 0--filaire  <br/> 1--Wi-Fi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--autres  <br/> 5--tunnel  <br/> |
   

