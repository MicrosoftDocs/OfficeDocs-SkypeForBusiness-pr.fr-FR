---
title: Table NetworkConnectionDetail
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
ms.openlocfilehash: d91928e40f6df9db1e53140726bbf04efad586ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807502"
---
# <a name="networkconnectiondetail-table"></a>Table NetworkConnectionDetail
 
La table NetworkConnectionDetail associe les types de connexion réseau aux identificateurs de connexion réseau utilisés ailleurs dans la base de données de qualité de l’utilisation. Ce tableau a été présenté dans Microsoft Lync Server 2013.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Principal  <br/> |Identificateur unique du type de connexion réseau.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Différent  <br/> |Type de connexion réseau correspondant au NetworkConnectionDetailKey. Les valeurs autorisées sont les suivantes :  <br/> 0--filaire  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--MobileBB  <br/> 4--autre  <br/> 5--tunnel  <br/> |
   

