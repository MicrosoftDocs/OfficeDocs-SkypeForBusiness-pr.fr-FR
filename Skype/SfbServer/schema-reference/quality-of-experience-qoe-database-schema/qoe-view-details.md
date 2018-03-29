---
title: Afficher les détails de QoE
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la génération de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont plus susceptibles d’assurer la compatibilité avec les versions ultérieures vers l’arrière.
ms.openlocfilehash: 72fe0a1cd4bd3319bbb6907a23bda0932b3ef619
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="qoe-view-details"></a>Afficher les détails de QoE
 
Vues couvrent les scénarios les plus courants pour renvoyer des données à partir de la base de données QoE SQL. Il est recommandé de vues utilisées pour la génération de rapports personnalisés au lieu d’accéder directement à la base de données ; C’est parce que les vues sont plus susceptibles d’assurer la compatibilité avec les versions ultérieures vers l’arrière.
  
|**Nom de la vue**|**Description**|
|:-----|:-----|
|[Vue de AudioStreamDetail](audiostreamdetail.md) <br/> |Stocke des informations sur chaque flux de données audio dans la base de données.  <br/> |
|[Vue de MediaLine](medialine.md) <br/> |Stocke des informations sur chaque ligne de support dans la base de données. Une session audio contient généralement une seule ligne de média audio. Un audio et vidéo (A / V) session contient en général un média audio et une ligne de la vidéo ; Toutefois, la session peut contenir deux lignes de média vidéo si un périphérique de conférence est utilisé ou si la galerie est utilisée.  <br/> |
|[Vue de NetworkConfigurationSettings](networkconfigurationsettings.md) <br/> |Stocke des informations sur la configuration du réseau.  <br/> |
|[Affichage de la session](session-0.md) <br/> |Stocke des informations sur les sessions qui ont des enregistrements dans la base de données.  <br/> |
|[Affichage de UserAgent](useragent-0.md) <br/> |Stocke des informations sur les agents utilisateur qui ont été impliquées dans des sessions avec des enregistrements dans la base de données.  <br/> |
|[Vue de VideoStreamDetail](videostreamdetail.md) <br/> |Stocke des informations sur chaque flux vidéo dans la base de données.  <br/> |
   

