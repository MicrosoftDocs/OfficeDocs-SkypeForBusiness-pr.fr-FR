---
title: Appel Analytique et tableau de bord de qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Découvrez les Analytique d’appel et appel du tableau de bord qualité quand et comment les utiliser pour analyser et résoudre les problèmes de qualité des appels.
ms.openlocfilehash: a212afea9f8d5010fa68af66ce72b39280a7d11c
ms.sourcegitcommit: 09fcd68e30e7f83110f98172382c74f970b339a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2019
ms.locfileid: "29442436"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Appel Analytique et tableau de bord de qualité des appels

Microsoft Teams et Skype pour les entreprises permettent de deux manières pour surveiller et résoudre les problèmes de qualité des appels : Analytique d’appel et appel du tableau de bord qualité. Cet article décrit les deux et vous indique quand utiliser chacune d’elles.
  
**Appel Analytique est maintenant disponible dans le Microsoft Teams et Skype entreprise centre d’administration.** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **Historique des appels** . Vous pouvez procéder par la recherche sur la page de profil utilisateur par une recherche de l’utilisateur du tableau de bord ou la recherche de l’utilisateur des **utilisateurs** dans le volet de navigation gauche.

> [!IMPORTANT]
> Autorisations de l’agent de support technique et le téléchargement de topologie réseau seront disponibles dans le nouveau portail d’administration dans les mois à venir. En attendant, vous pouvez continuer à utiliser https://adminportal.services.skypeforbusiness.com pour l’accès de support technique de niveau 1 et niveau 2.
  
## <a name="whats-call-analytics-and-when-should-i-use-it"></a>What ' s Analytique appeler et quand dois-je utiliser ?

Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité liés aux appels spécifiques et des réunions pour chaque utilisateur de Microsoft Teams Skype pour un compte professionnel. Si vous êtes un administrateur Office 365, vous pouvez utiliser Analytique appeler pour résoudre les problèmes de qualité et connexion appel dans Microsoft Teams et Skype pour les entreprises.

Pour afficher ces informations pour un utilisateur dans le & Microsoft Teams Skype entreprise centre d’administration, cliquez sur l’onglet **Historique des appels** pour cet utilisateur dans la page de détails utilisateur, en affichant tous les appels et les réunions que l’utilisateur a participé à des 30 derniers jours.

![Données utilisateur d’appel analytique.](media/call-analytics-user-data.png)

Pour obtenir des informations supplémentaires sur une session donnée, y compris media détaillées et les statistiques du réseau, cliquez sur une session pour voir les détails.

![Appeler des données de session utilisateur analytique.](media/call-analytics-user-data-session.png)

Si vous souhaitez que non-Admin, tels que les agents de support technique d’un fournisseur externe, pour utiliser appel Analytique, vous pouvez attribuer les autorisations afin qu’ils peuvent utiliser Analytique appeler, mais ils ne peuvent pas accéder le reste de la & Microsoft Teams Skype entreprise centre d’administration : 
  
- **Prend en charge les agents de support technique avec communications autorisations spécialiste**: Agents voir un ensemble limité de données et les informations d’identification personnelle (PII) dans l’appel d’Analytique. Ils peuvent résoudre les appels, mais ils transmet des problèmes avec les réunions pour un ingénieur du support technique communications.
    
- **Prend en charge les agents de support technique avec communications ingénieur autorisations**: Agents voir toutes les données disponibles dans Analytique appeler et résoudre les problèmes d’appels et les réunions. Ils ont un accès total à appeler des journaux et des informations sur le client.

> [!NOTE]
> Le rôle de spécialiste de prise en charge des communications est équivalent au support de niveau 1 et le rôle ingénieur de prise en charge des communications est équivalent au support de niveau 2.

Pour plus d’informations sur les communications spécialiste prise en charge et les communications prennent en charge les rôles ingénieur, voir [utiliser les équipes Microsoft des rôles d’administration pour gérer les équipes](using-admin-roles.md).

> [!IMPORTANT]
> Autorisations de l’agent de support technique et le téléchargement de topologie réseau sont disponibles dans le & Microsoft Teams Skype entreprise centre d’administration. Spécialistes du Support de communications et de Communications ingénieurs du support technique peuvent utiliser ce portail pour accéder aux Analytique des appels et le tableau de bord qualité des appels.
    
Pour plus d’informations sur la configuration Analytique d’appel, voir [Set up Skype pour Business appeler Analytique](set-up-call-analytics.md). Pour plus d’informations sur comment les agents du support technique peuvent fonctionner avec Analytique d’appel, voir [Utiliser appel Analytique pour résoudre les problèmes d’appel de mauvaise qualité](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Quel est le tableau de bord qualité des appels, et quand dois-je utiliser ?

Appel Analytique vous donne des informations détaillées spécifiques sur la qualité des appels rencontrée par les utilisateurs. Pourquoi utilisateur Tony Smith disposer d’un appel médiocre après‑midi ? À l’aide d’Analytique d’appel, de Skype pour l’administrateur d’entreprise ou de l’agent de support technique formé Teams Microsoft puisse étudier le périphérique, réseau, connectivité et autres facteurs liés à l’appel de Tony.
  
Autorité de certification est conçue pour aider les administrateurs et les agents de support technique résoudre les problèmes de qualité d’appel avec des appels spécifiques, où le tableau de bord de qualité des appels (CQD) est conçu pour aider à Skype pour les administrateurs d’entreprise et optimisent un réseau les ingénieurs réseau. CQD déplace le focus des utilisateurs spécifiques et à la place examine compilent les informations pour un ensemble Skype pour l’organisation de l’entreprise. 
  
La qualité des appels médiocres Tony est peut-être en raison d’un problème de réseau qui affecte également le nombre d’autres utilisateurs. Expérience d’appels individuels de Tony n’est pas visible dans CQD, mais la qualité globale d’appels effectués à l’aide de Skype pour les entreprises est capturée. Avec le CQD, global modèles peuvent apparaître, permettant ainsi aux ingénieurs réseau à évaluer informé de la qualité des appels. CQD fournit des rapports des mesures de qualité des appels qui vous expliqueront appellent globale qualité, client-serveur et flux client client et la qualité de voix [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252). 
  
![Capture d’écran du tableau de bord de qualité d’appel dans la Skype entreprise centre d’administration. Les onglets affichés sont SLA de qualité d’affichage globale la qualité des appels et serveur - Client, Client - Client.](media/6eaccf99-8ee8-4f99-bdf2-ba1c72471cb9.png)
  
Pour plus d’informations, voir [fonctionnalités du tableau de bord qualité des appels pour Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Appel Analytique CQD s’exécuter en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, un spécialiste du support détermine qu’ils ont besoin d’aide pour résoudre un problème d’appel de communications. Les spécialistes de prise en charge des communications passe l’appel vers un ingénieur du support communications, qui a accès à plus d’informations à prendre en charge les communications spécialiste dans Analytique appeler. À son tour, l’ingénieur du support technique communications alerte ingénieur réseau à un problème. L’ingénieur réseau peut vérifier CQD pour voir si un problème général liés au site peut être une contribue cause de problèmes d’appel.
  
Pour plus d’informations sur CQD, voir [activation et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md) et les [Dimensions et mesures disponibles dans les appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Rubriques connexes

[Configurer Analytique d’appel](set-up-call-analytics.md)

[Utiliser l'analyse des appels pour résoudre les problèmes liés à la qualité médiocre des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et à l’aide de tableau de bord qualité d’appel pour Microsoft Teams et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md)