---
title: Table AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: c886c5179d40063c1325bea3167e06ae7fe37666
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411507"
---
# <a name="appliedbandwidthsource-table"></a>Table AppliedBandwidthSource
 
La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de cette source.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Uniques  <br/> |Il s’agit de la source de la capacité de bande passante imposée. Il décrit d’où vient la limite de bande passante (par exemple, « Serveur de stratégie », « SERVEUR TURN » ou « Modalité »).  <br/> |
   

