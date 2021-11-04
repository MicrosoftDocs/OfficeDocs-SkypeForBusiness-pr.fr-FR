---
title: Table AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
ms.openlocfilehash: 772afa1ffe6ce34dc38676193825c0f2891d7bea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761832"
---
# <a name="appliedbandwidthsource-table"></a>Table AppliedBandwidthSource
 
La table AppliedBandwidthSource est une table de prise en charge. Chaque enregistrement représente une source.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primaire  <br/> |Numéro unique d’identification de cette source.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Uniques  <br/> |Il s’agit de la source de la capacité de bande passante imposée. Il décrit l’emplacement d’où vient la limite de bande passante (par exemple, « Serveur de stratégie », « SERVEUR TURN » ou « Modalité »).  <br/> |
   

