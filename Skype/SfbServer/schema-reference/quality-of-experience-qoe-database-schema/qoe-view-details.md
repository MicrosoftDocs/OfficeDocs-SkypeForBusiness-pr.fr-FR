---
title: Vue détaillée de la qualité de l’expérience
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Les vues couvrent les cas les plus courants de retour de données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés plutôt que d’accéder directement aux tables de la base de données. en effet, les vues sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures.
ms.openlocfilehash: c492b06f2b6e8050e4992837f0f2b7ebba106858
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294753"
---
# <a name="qoe-view-details"></a>Vue détaillée de la qualité de l’expérience
 
Les vues couvrent les cas les plus courants de retour de données à partir de la base de données SQL QoE. Il est recommandé d’utiliser des affichages pour créer des rapports personnalisés plutôt que d’accéder directement aux tables de la base de données. en effet, les vues sont plus susceptibles de garantir la compatibilité descendante avec les versions ultérieures.
  
|**Nom de la vue**|**Description**|
|:-----|:-----|
|[Affichage AudioStreamDetail](audiostreamdetail.md) <br/> |Stocke les informations relatives à chaque flux audio dans la base de données.  <br/> |
|[Affichage MediaLine](medialine.md) <br/> |Stocke les informations relatives à chaque ligne multimédia dans la base de données. Une seule session audio contient généralement une ligne multimédia audio. Une session audio et vidéo (A/V) contient généralement une seule ligne de médias audio et une seule ligne de média vidéo. Toutefois, la session peut contenir deux lignes de média vidéo si un appareil de conférence est utilisé ou si la vue Galerie est utilisée.  <br/> |
|[Affichage NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Stocke des informations sur la configuration du réseau.  <br/> |
|[Affichage de session](session-0.md) <br/> |Stocke les informations sur les sessions contenant des enregistrements dans la base de données.  <br/> |
|[Affichage UserAgent](useragent-0.md) <br/> |Stocke les informations sur les agents utilisateur impliqués dans les sessions contenant des enregistrements dans la base de données.  <br/> |
|[Affichage VideoStreamDetail](videostreamdetail.md) <br/> |Stocke des informations sur chaque flux vidéo dans la base de données.  <br/> |
   

