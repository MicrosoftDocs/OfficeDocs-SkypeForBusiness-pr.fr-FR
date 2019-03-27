---
title: Table AppliedBandwidthSource
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: 2fed25b6ca2218cb8b7300507b5c8258b2c29798
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899784"
---
# <a name="appliedbandwidthsource-table"></a>Table AppliedBandwidthSource
 
La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Principal  <br/> |Numéro unique identifiant la source.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Unique  <br/> |Il s’agit de la source de l’extrémité de la bande passante imposée en cours. Il décrit la limite de bande passante provenance (par exemple, « Stratégie de serveur », « Activer le serveur » ou « Modalité »).  <br/> |
   

