---
title: Tableau de bord Analyse des appels et Qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: conceptual
ms.assetid: 4cd5fe35-8463-4996-a252-086cd3ca2d9a
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Apprenez-en davantage sur l’analyse des appels et le tableau de bord de qualité des appels et le moment où les utiliser pour surveiller et résoudre les problèmes de qualité d’appel.
ms.openlocfilehash: 535d3bf6ce2abf69143fb270e01bf4f0c2e230dc
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2019
ms.locfileid: "34433598"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Tableau de bord Analyse des appels et Qualité des appels

Microsoft teams et Skype entreprise vous permettent de surveiller et de résoudre les problèmes de qualité d’appel: le tableau de bord d’analyse des appels et de la qualité des appels (bord). Cet article décrit les deux et vous indique quand utiliser chacun d’eux.

L’analyse des appels et bord s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, imaginons qu’un spécialiste du support des communications détermine qu’il a besoin d’une aide supplémentaire pour résoudre un problème d’appel. Le spécialiste du support des communications transmet l’appel à un ingénieur du support de communication, qui a accès à des informations supplémentaires sur l’analyse des appels que le spécialiste du support des communications. Le technicien du support technique peut ainsi signaler à un ingénieur réseau qu’il a un problème. L’ingénieur réseau peut vérifier bord pour savoir si un problème global lié à un site peut être à l’origine des problèmes d’appel.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Qu’est-ce que l’analyse des appels et quand dois-je l’utiliser?

**L’analyse des appels est désormais disponible dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com).** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **historique des appels** . Pour cela, vous pouvez consulter la page de profil de l’utilisateur à l’aide de la recherche de l’utilisateur dans le tableau de **** bord ou en trouvant l’utilisateur dans le volet de navigation de gauche.

L’analyse des appels affiche des informations détaillées sur les périphériques, les réseaux et la connectivité liés aux appels et réunions spécifiques de chaque utilisateur d’un compte Microsoft teams ou Skype entreprise. Pourquoi cet utilisateur a-t-il mal appelé cet après-midi? À l’aide d’une analyse des appels, un administrateur 365 Office ou un agent de support technique peut examiner l’appareil, le réseau, la connectivité et d’autres facteurs liés à son appel pour résoudre les problèmes de qualité d’appel et de connexion dans Microsoft teams et Skype entreprise.

Pour afficher ces informations pour un utilisateur dans le centre d’administration de Microsoft Teams, cliquez sur l’onglet **historique des appels** pour cet utilisateur dans la page de détails de l’utilisateur, en affichant tous les appels et les réunions auxquels il a participé au cours des 30 derniers jours.

![Capture d’écran de toutes les données utilisateur d’analyse.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Pour obtenir des informations supplémentaires sur une session donnée, notamment des statistiques détaillées sur le média et la mise en réseau, cliquez sur une session pour afficher les détails.

![Capture d’écran des données de session utilisateur d’analyse des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Si vous voulez que les personnes qui ne sont pas administrateurs (par exemple, les agents de support technique d’un fournisseur externe) utilisent l’analyse des appels, vous pouvez attribuer des autorisations de manière à ce qu’elles puissent utiliser l’analyse des appels, mais elles ne peuvent pas accéder au reste du centre d’administration Microsoft teams: 
  
- Les agents de support technique dotés d’une **autorisation de support des communications**: les agents voient un ensemble limité de données et des informations d’identification personnelle dans l’analyse des appels. Ils peuvent résoudre les problèmes liés aux appels, mais ils pourront résoudre les problèmes liés aux réunions à un ingénieur du support des communications.
    
- Les **agents de support technique dotés des autorisations du support des communications**: les agents voient toutes les données disponibles dans les analyses des appels et résoudre les problèmes liés aux appels et aux réunions. Ils disposent d’un accès total aux journaux d’appels et aux informations client.

> [!NOTE]
> Le rôle de spécialiste de la prise en charge des communications équivaut au rôle de support de niveau 1 du portail d’évaluation et au rôle de support technique de niveau 2 du portail d’évaluation.

Pour plus d’informations sur les rôles de technicien de support de communications et de support technique des communications, voir [utiliser les rôles d’administrateur Microsoft teams pour gérer teams](using-admin-roles.md).

> [!IMPORTANT]
> Les autorisations d’agent de support technique et le chargement de la topologie réseau sont disponibles dans le centre d’administration Microsoft Teams. Les spécialistes de la prise en charge des communications peuvent utiliser ce portail pour accéder à l’analyse des appels et au tableau de bord de qualité des appels.
    
Pour plus d’informations sur la configuration de l’analyse des appels, reportez-vous à la rubrique [configuration d’une analyse des appels Skype entreprise](set-up-call-analytics.md). Pour plus d’informations sur la façon dont les agents de support technique peuvent travailler avec l’analyse des appels, voir utiliser l’analyse des appels [pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Qu’est-ce que le tableau de bord de qualité des appels et quand dois-je l’utiliser?
  
Même si l’analyse des appels permet aux administrateurs et aux agents de support technique de résoudre les problèmes de qualité d’appel avec des appels spécifiques, le tableau de bord de qualité des appels (bord) est conçu pour permettre aux administrateurs d’équipe, aux administrateurs Skype entreprise et aux ingénieurs réseau d’optimiser un réseau. BORD déplace le focus sur des utilisateurs spécifiques et examine plutôt les informations agrégées d’une équipe complète ou Skype entreprise. Pour plus d’informations, reportez-vous [à la rubrique fonctionnalités du tableau de bord de qualité des appels pour teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
La qualité des appels est peut-être médiocre en raison d’un problème réseau affectant également de nombreux autres utilisateurs. L’utilisation individuelle des appels n’est pas visible dans bord, mais la qualité générale des appels passés à l’aide de Microsoft teams ou de Skype entreprise est capturée. Avec bord, les modèles globaux risquent de se révéler invisibles, ce qui permet aux ingénieurs réseau d’effectuer des analyses éclairées de la qualité des appels. BORD fournit des rapports sur les mesures de la qualité d’appel qui vous permettent d’accéder à des informations sur la qualité des appels globales, les flux de clients du serveur, les flux client-client et le [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualité vocale.
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

À l’aide des rapports d’emplacement de bord, il est possible d’évaluer la qualité et la fiabilité des appels dans le bâtiment de l’utilisateur pour déterminer si le problème est isolé d’un utilisateur ou s’il a des répercussions sur un plus grand nombre d’utilisateurs.

![Capture d’écran des rapports d’emplacement du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Pour activer des affichages spécifiques de la construction ou du point de terminaison dans bord, un administrateur doit [Télécharger des informations de bâtiment ou de point de terminaison](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) sur la page de téléchargement des données du client bord. 

Si vous voulez que les personnes qui ne sont pas des administrateurs, telles que les agents de support technique, puissent utiliser le tableau de bord de qualité **** des appels, vous pouvez les **** affecter à l' **ingénieur du support des communications**de l’équipe. Les utilisateurs dotés des rôles suivants peuvent accéder au tableau de bord de qualité des appels:

- Administrateur général
- Lecteur global
- Administrateur Skype entreprise
- Administrateur du service Teams
- Administrateur des communications Teams
- Ingénieur du support technique pour les communications Teams
- Spécialiste du support des communications teams
- Lecteur de rapports

> [!NOTE]
> Le technicien du support technique de Microsoft Teams, le spécialiste du support des communications d’équipe et les rôles du lecteur de rapports ne peuvent pas modifier les fichiers sur la page de téléchargement des données du client bord, ni activer bord pour un client.

Pour plus d’informations sur ces rôles, voir [à propos des rôles d’administrateur Office 365](/office365/admin/add-users/about-admin-roles).

Pour plus d’informations sur bord, reportez-vous [à activation et utilisation du tableau de bord de qualité des appels de Microsoft Teams, de Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md) et des [dimensions et mesures disponibles dans le tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Voir aussi

[Vidéo: vue d’ensemble de la qualité d’appel](https://aka.ms/teams-quality)

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md)
