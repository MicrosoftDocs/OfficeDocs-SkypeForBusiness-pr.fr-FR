---
title: Vue détaillée de la qualité de l’expérience (QoE)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Les vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des vues pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données . Cela est dû au fait que les affichages sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.
ms.openlocfilehash: f3a22ba6b8984334e3b4c4f1e7cea293a7741b01
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858071"
---
# <a name="qoe-view-details"></a>Vue détaillée de la qualité de l’expérience (QoE)
 
Les vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des vues pour créer des rapports personnalisés au lieu d’accéder directement aux tables de base de données . Cela est dû au fait que les affichages sont plus susceptibles de maintenir une compatibilité ascendante avec les futures sorties.
  
|**Nom de la vue**|**Description**|
|:-----|:-----|
|[Affichage AudioStreamDetail](audiostreamdetail.md) <br/> |Stocke les informations sur chaque flux audio dans la base de données.  <br/> |
|[Affichage MediaLine](medialine.md) <br/> |Stocke des informations sur chaque ligne de média dans la base de données. Une session audio contient généralement une ligne de média audio. Une session audio et vidéo (A/V) contient généralement une ligne de média audio et une ligne de média vidéo ; toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence ou la Vue Galerie est utilisé.  <br/> |
|[Affichage NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Stocke des informations sur la configuration du réseau.  <br/> |
|[Affichage de session](session-0.md) <br/> |Stocke des informations sur les sessions disposant d’enregistrements dans la base de données.  <br/> |
|[Affichage UserAgent](useragent-0.md) <br/> |Stocke des informations sur les agents utilisateurs qui ont participé à des sessions disposant d’enregistrements dans la base de données.  <br/> |
|[Vue VideoStreamDetail](videostreamdetail.md) <br/> |Stocke des informations sur chaque flux vidéo dans la base de données.  <br/> |
   

