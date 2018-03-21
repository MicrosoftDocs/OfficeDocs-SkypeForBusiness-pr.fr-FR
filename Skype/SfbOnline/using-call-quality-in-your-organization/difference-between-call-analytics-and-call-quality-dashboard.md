---
title: "Quelle est la différence entre appeler une Analytique et appelez le tableau de bord qualité ?"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
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
description: "Apprenez à appeler l’Analytique et appelez le tableau de bord qualité et quand les utiliser pour surveiller et résoudre les problèmes de qualité de l’appel dans Skype pour les entreprises."
ms.openlocfilehash: a17b98451013f24810fd437fa3eb638f98610a8f
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="whats-the-difference-between-call-analytics-and-call-quality-dashboard"></a>Quelle est la différence entre appeler une Analytique et appelez le tableau de bord qualité ?

Skype pour entreprises vous offre deux manières de surveiller et de résoudre les problèmes de qualité de l’appel : appeler l’Analytique et appelez le tableau de bord qualité. Cet article décrit les deux et vous indique quand utiliser chacun d'entre eux.
  
> [!NOTE]
> Analytique de l’appel est en cours d’aperçu. Texte et images décrites ici peut ne pas correspondent de votre expérience. 
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Ce qui est d’appeler l’Analytique, et quand dois-je l’utiliser ?

Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité lié aux appels spécifiques et de réunions pour chaque utilisateur dans un Skype pour le compte de l’entreprise. Si vous êtes un Skype pour l’administration de l’entreprise, vous pouvez utiliser Analytique d’appeler pour résoudre les problèmes de Skype pour les problèmes de connexion et de qualité appel professionnels.
  
Si vous souhaitez que les non-administrateurs, tels que les agents du support technique d’un fournisseur externe, pour utiliser appeler Analytique, vous pouvez attribuer des autorisations qu’ils peuvent utiliser Analytique d’appeler mais ils ne peuvent pas accéder au reste de la Skype pour le centre d’administration de l’entreprise : 
  
- **Les agents du support technique avec les autorisations de niveau 1**: Agents voir un jeu de données et les informations d’identification personnelle (PII) dans l’appel d’Analytique limité. Ils peuvent résoudre les appels, mais ils transmet problèmes liés aux réunions d’un agent de niveau 2.
    
- **Les agents du support technique avec les autorisations de niveau 2**: Agents voir toutes les données disponibles dans l’appel d’Analytique et résolution des problèmes liés à la fois des appels et des réunions. Ils ont un accès complet à appeler des journaux et des informations sur le client.
    
Pour plus d’informations sur la configuration d’appeler l’Analytique, consultez [configurer Skype pour Analytique d’appeler commerciale](set-up-call-analytics.md). Pour plus d’informations sur la façon des agents du support technique peuvent les appeler l’Analytique, consultez [Analytique d’appeler utiliser pour résoudre les problèmes d’appel de mauvaise qualité](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Quel est le tableau de bord qualité appeler, et quand dois-je l’utiliser ?

Appel Analytique vous donne des informations détaillées et spécifiques sur la qualité des appels rencontrée par les utilisateurs. Pourquoi l’utilisateur Tony Smith possédait un appel médiocre cet après-midi ? À l’aide d’appeler l’Analytique, un Skype pour l’administrateur d’entreprise ou de l’agent de support technique qualifié peut étudier le périphérique, réseau, connectivité et autres facteurs liés à l’appel de Tony.
  
Autorité de certification est conçue pour aider les administrateurs et les agents du support technique résoudre les problèmes de qualité d’appel avec des appels spécifiques, où le tableau de bord de qualité appeler (CQD) est conçu pour aider les Skype pour les administrateurs de l’entreprise et aux ingénieurs réseau optimisent un réseau. CQD déplace le focus à partir des utilisateurs spécifiques et examine à la place d’agrègent les informations pour un ensemble Skype pour l’organisation de l’entreprise. 
  
Qualité de l’appel médiocre de Tony est peut-être en raison d’un problème de réseau qui affecte également beaucoup d’autres utilisateurs. Expérience d’appels individuelles de Tony n’est pas visible dans CQD, mais la qualité globale des appels effectués à l’aide de Skype pour entreprise est capturée. Avec le CQD, global modèles peuvent apparaître, permettant ainsi aux ingénieurs de réseau à évaluer informé de la qualité des appels. CQD fournit des rapports de métriques de qualité d’appel qui vous expliqueront appellent globale qualité, client-serveur et les flux de données client-client et qualité de la voix [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Capture d’écran de tableau de bord qualité appel dans le Skype pour entreprise Admin Center. Les onglets affichés sont appeler la qualité globale, le serveur - Client, Client - Client et SLA de qualité d’affichage.](../images/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Pour plus d’informations, consultez [fonctionnalités du tableau de bord qualité appeler pour Skype pour entreprise en ligne](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Analytique de l’appel CQD s’exécuter en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, qu'un agent de niveau 1 détermine qu’il doit obtenir de l’aide pour résoudre un problème d’appel. L’agent de niveau 1 transmet l’appel à un agent de niveau 2, qui a accès à des informations plus Analytique d’appeler que l’agent de niveau 1. À son tour, l’agent de niveau 2 peut avertir un ingénieur réseau à un problème. L’ingénieur réseau peut vérifier CQD pour voir si un problème de site global peut être une cause contribue de problèmes d’appel.
  
Pour plus d’informations sur CQD, voir [activation et à l’aide d’appel de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md) et [Dimensions et mesures disponibles dans l’appel de tableau de bord qualité pour les équipes Microsoft et Skype pour entreprise en ligne](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Rubriques connexes
[Configurer l'analyse des appels Skype Entreprise](set-up-call-analytics.md)

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels Skype Entreprise](use-call-analytics-to-troubleshoot-poor-call-quality.md)