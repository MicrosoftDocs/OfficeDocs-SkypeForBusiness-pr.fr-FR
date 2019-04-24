---
title: Vue détaillée de la qualité de l’expérience
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Affichages couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la création de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont davantage de chances de conserver la compatibilité avec les futures versions à compatibilité descendante.
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212143"
---
# <a name="qoe-view-details"></a>Vue détaillée de la qualité de l’expérience
 
Affichages couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la création de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont davantage de chances de conserver la compatibilité avec les futures versions à compatibilité descendante.
  
|**Nom de l’affichage**|**Description**|
|:-----|:-----|
|[Vue audiostreamdetail](audiostreamdetail.md) <br/> |Stocke des informations sur chaque flux audio dans la base de données.  <br/> |
|[Vue MediaLine](medialine.md) <br/> |Stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient généralement un média audio et une ligne de média vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si le mode d’affichage galerie est utilisé.  <br/> |
|[Vue networkconfigurationsettings](networkconfigurationsettings.md) <br/> |Stocke des informations sur la configuration réseau.  <br/> |
|[Affichage de la session](session-0.md) <br/> |Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.  <br/> |
|[Vue UserAgent](useragent-0.md) <br/> |Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.  <br/> |
|[Vue videostreamdetail](videostreamdetail.md) <br/> |Stocke des informations sur chaque flux vidéo dans la base de données.  <br/> |
   

