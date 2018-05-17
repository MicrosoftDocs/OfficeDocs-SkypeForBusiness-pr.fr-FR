---
title: Appel Analytique et tableau de bord de qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Découvrez les Analytique d’appel et appel du tableau de bord qualité et quand les utiliser pour surveiller et résoudre les problèmes de qualité des appels dans Skype pour les entreprises.
ms.openlocfilehash: c8d73ee128425f106174ccad60a0b0c947cc07e5
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Appel Analytique et tableau de bord de qualité des appels

Skype pour les entreprises vous propose deux méthodes pour surveiller et résoudre les problèmes de qualité des appels : Analytique d’appel et appel du tableau de bord qualité. Cet article décrit les deux et vous indique quand utiliser chacune d’elles.
  
> [!NOTE]
> Appel Analytique est actuellement en mode Aperçu. Texte et images décrites ici peut ne pas correspondent votre expérience. 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>What ' s Analytique appeler et quand dois-je utiliser ?

Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité liés aux appels spécifiques et réunions pour chaque utilisateur dans un Skype pour un compte professionnel. Si vous êtes un Skype pour administrateur d’entreprise, vous pouvez utiliser Analytique appel dépannage Skype pour les problèmes de qualité et connexion appel Business.
  
Si vous souhaitez que non-Admin, tels que les agents de support technique d’un fournisseur externe, pour utiliser l’appel Analytique, vous pouvez attribuer les autorisations afin qu’ils peuvent utiliser Analytique appel mais ils ne peuvent pas accéder le reste de la Skype pour le centre d’administration Business : 
  
- **Les agents de support technique disposant des autorisations de niveau 1**: Agents voir un ensemble limité de données et les informations d’identification personnelle (PII) dans l’appel d’Analytique. Ils peuvent résoudre les appels, mais ils transmet des problèmes avec les réunions pour un agent de niveau 2.
    
- **Les agents de support technique disposant des autorisations de niveau 2**: Agents voir toutes les données disponibles dans Analytique appeler et résoudre les problèmes d’appels et les réunions. Ils ont un accès total à appeler des journaux et des informations sur le client.
    
Pour plus d’informations sur la configuration Analytique d’appel, voir [Set up Skype pour Business appeler Analytique](set-up-call-analytics.md). Pour plus d’informations sur comment les agents du support technique peuvent fonctionner avec Analytique d’appel, voir [Utiliser appel Analytique pour résoudre les problèmes d’appel de mauvaise qualité](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Quel est le tableau de bord qualité des appels, et quand dois-je utiliser ?

Appel Analytique vous donne des informations détaillées spécifiques sur la qualité des appels rencontrée par les utilisateurs. Pourquoi utilisateur Tony Smith disposer d’un appel médiocre après‑midi ? À l’aide d’Analytique d’appel, une Skype pour l’administrateur d’entreprise ou de l’agent de support technique formé puisse étudier le périphérique, réseau, connectivité et autres facteurs liés à l’appel de Tony.
  
Autorité de certification est conçue pour aider les administrateurs et les agents de support technique résoudre les problèmes de qualité d’appel avec des appels spécifiques, où le tableau de bord de qualité des appels (CQD) est conçu pour aider à Skype pour les administrateurs d’entreprise et optimisent un réseau les ingénieurs réseau. CQD déplace le focus des utilisateurs spécifiques et à la place examine compilent les informations pour un ensemble Skype pour l’organisation de l’entreprise. 
  
La qualité des appels médiocres Tony est peut-être en raison d’un problème de réseau qui affecte également le nombre d’autres utilisateurs. Expérience d’appels individuels de Tony n’est pas visible dans CQD, mais la qualité globale d’appels effectués à l’aide de Skype pour les entreprises est capturée. Avec le CQD, global modèles peuvent apparaître, permettant ainsi aux ingénieurs réseau à évaluer informé de la qualité des appels. CQD fournit des rapports des mesures de qualité des appels qui vous expliqueront appellent globale qualité, client-serveur et flux client client et la qualité de voix [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Capture d’écran du tableau de bord de qualité d’appel dans la Skype entreprise centre d’administration. Les onglets affichés sont SLA de qualité d’affichage globale la qualité des appels et serveur - Client, Client - Client.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Pour plus d’informations, voir [fonctionnalités du tableau de bord qualité des appels pour Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Appel Analytique CQD s’exécuter en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, qu'un agent de niveau 1 détermine qu’ils ont besoin d’aide pour résoudre un problème d’appel. L’agent de niveau 1 transmet l’appel à un agent de niveau 2, qui a accès à plus d’informations dans Analytique appeler que l’agent de niveau 1. À son tour, l’agent de niveau 2 peut alerter un ingénieur réseau à un problème. L’ingénieur réseau peut vérifier CQD pour voir si un problème général liés au site peut être une contribue cause de problèmes d’appel.
  
Pour plus d’informations sur CQD, voir [activation et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md) et les [Dimensions et mesures disponibles dans les appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](use-call-analytics-to-troubleshoot-poor-call-quality.md)

  
 