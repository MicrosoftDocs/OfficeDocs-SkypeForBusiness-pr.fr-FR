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
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Apprenez-en davantage sur l’analyse des appels et le tableau de bord de qualité des appels et le moment où les utiliser pour surveiller et résoudre les problèmes de qualité d’appel.
ms.openlocfilehash: be63c4e227e74e242169ec5c3b5e0b01a43a0730
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824906"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Tableau de bord Analyse des appels et Qualité des appels

Microsoft teams et Skype entreprise vous permettent de surveiller et de résoudre les problèmes de qualité d’appel : le tableau de bord d’analyse des appels et de la qualité des appels (bord). Cet article décrit les deux et vous indique quand utiliser chacun d’eux.

L’analyse des appels et bord s’exécutent en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, imaginons qu’un spécialiste du support des communications détermine qu’il a besoin d’une aide supplémentaire pour résoudre un problème d’appel. Le spécialiste du support des communications transmet l’appel à un ingénieur du support de communication, qui a accès à des informations supplémentaires sur l’analyse des appels que le spécialiste du support des communications. Le technicien du support technique peut ainsi signaler à un ingénieur réseau qu’il a un problème. L’ingénieur réseau peut vérifier bord pour savoir si un problème global lié à un site peut être à l’origine des problèmes d’appel.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>Qu’est-ce que l’analyse des appels et quand dois-je l’utiliser ?

**L’analyse des appels est désormais disponible dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com).** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **historique des appels** de la page de profil d’un utilisateur. Pour afficher l’onglet, recherchez l’utilisateur dans le tableau de bord ou recherchez-le à partir de l’onglet **utilisateurs** dans la barre de navigation gauche.

L’analyse des appels affiche des informations détaillées sur les périphériques, les réseaux et la connectivité liés aux appels et aux réunions de chaque utilisateur dans un compte client Microsoft teams ou Skype entreprise. Pourquoi cet utilisateur a-t-il mal appelé cet après-midi ? Dans le cadre de l’analyse des appels, un administrateur 365 Office ou un agent de support technique peut examiner l’appareil, le réseau, la connectivité ainsi que d’autres facteurs liés à un appel pour résoudre les problèmes de qualité d’appel et de connexion dans Microsoft teams et Skype entreprise.

Pour afficher ces informations pour un utilisateur dans le centre d’administration de Microsoft Teams, cliquez sur l’onglet **historique des appels** pour cet utilisateur dans la page de détails de l’utilisateur pour afficher tous les appels et réunions de cet utilisateur au cours des 30 derniers jours.

![Capture d’écran de toutes les données utilisateur d’analyse.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

Pour obtenir des informations supplémentaires sur une session donnée, notamment les statistiques détaillées sur le média et la mise en réseau, cliquez sur une session pour afficher les détails.

![Capture d’écran des données de session utilisateur d’analyse des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Si vous voulez que les personnes qui ne sont pas des administrateurs (par exemple, les agents de support technique d’un fournisseur externe) puissent utiliser l’analyse des appels, vous pouvez attribuer des autorisations de manière à ce qu’elles puissent utiliser le reste du centre d’administration Microsoft teams :
  
- **Les agents de support technique dotés d’une autorisation de support des communications**: les agents voient un ensemble limité de données et des informations d’identification personnelle dans l’analyse des appels. Ils peuvent résoudre les problèmes des appels, mais ils peuvent résoudre les problèmes liés aux réunions passés à un ingénieur du support des communications.
- Les **agents de support technique dotés des autorisations du support des communications**: les agents voient toutes les données disponibles dans les analyses des appels et résoudre les problèmes liés aux appels et aux réunions. Ils disposent d’un accès total aux journaux d’appels et aux informations client.

> [!NOTE]
> Le rôle de spécialiste de la prise en charge des communications équivaut au rôle de support de niveau 1 du portail d’évaluation et au rôle de support technique de niveau 2 du portail d’évaluation.

Pour plus d’informations sur les rôles de technicien de support de communications et de support technique des communications, voir [utiliser les rôles d’administrateur Microsoft teams pour gérer teams](using-admin-roles.md).

> [!IMPORTANT]
> Les autorisations d’agent de support technique et le chargement de la topologie réseau sont disponibles dans le centre d’administration Microsoft Teams. Les spécialistes de la prise en charge des communications peuvent utiliser ce portail pour accéder à l’analyse des appels et au tableau de bord de qualité des appels.

Pour plus d’informations sur l’analyse des appels, reportez-vous à la rubrique [configuration d’une analyse d’appel Skype entreprise](set-up-call-analytics.md). Pour plus d’informations sur la façon dont les agents de support technique peuvent travailler avec l’analyse des appels, voir utiliser l’analyse des appels [pour résoudre les problèmes de mauvaise qualité d’appel](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Qu’est-ce que le tableau de bord de qualité des appels et quand dois-je l’utiliser ?
  
La fonction d’analyse des appels permet aux administrateurs et aux techniciens d’assistance de résoudre les problèmes de qualité d’appel avec des *appels spécifiques*. Le tableau de bord de qualité des appels (bord) est conçu pour permettre aux administrateurs d’équipe, aux administrateurs Skype entreprise et aux ingénieurs réseau d' *optimiser un réseau*. BORD déplace le focus sur des utilisateurs spécifiques et examine plutôt les informations agrégées d’une équipe complète ou Skype entreprise. Pour plus d’informations, reportez-vous [à la rubrique fonctionnalités du tableau de bord de qualité des appels pour teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
Supposez que la mauvaise qualité des appels est due à un problème réseau qui affecte également de nombreux autres utilisateurs. L’utilisation individuelle des appels n’est pas visible dans bord, mais la qualité générale des appels passés à l’aide de Microsoft teams ou de Skype entreprise est capturée. Avec bord, les modèles globaux peuvent devenir évidents, afin que les ingénieurs du réseau puissent effectuer des analyses éclairées de la qualité des appels. BORD fournit des rapports sur les métriques de la qualité d’appel qui vous permettent d’avoir une vue d’ensemble de la qualité des appels, des flux client-client, des flux client-client et du [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de qualité vocale.
  
![Capture d’écran du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

Les rapports bord de localisation de l’utilisateur agrègent la qualité et la fiabilité des appels au sein de l’immeuble. Les données peuvent être évaluées pour déterminer si le problème est limité à un utilisateur unique ou s’il concerne un plus grand nombre d’utilisateurs.

![Capture d’écran des rapports d’emplacement du tableau de bord de qualité des appels.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

> [!NOTE]
> Pour activer des affichages spécifiques de la construction ou du point de terminaison dans bord, un administrateur doit [Télécharger des informations de bâtiment ou de point de terminaison](turning-on-and-using-call-quality-dashboard.md#upload-tenant-data-information) sur la page de téléchargement des données du client bord.

Si vous voulez que les utilisateurs qui ne sont pas administrateurs (par exemple, les agents de support technique) puissent utiliser le tableau de bord de qualité des appels, vous pouvez attribuer à ces utilisateurs l’un des rôles suivants, qui disposent également des autorisations nécessaires pour accéder au tableau de bord de qualité des appels :

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
  
## <a name="related-topics"></a>Rubriques connexes

[Vidéo : vue d’ensemble de la qualité d’appel](https://aka.ms/teams-quality)

[Configurer l’analyse des appels](set-up-call-analytics.md)

[Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](turning-on-and-using-call-quality-dashboard.md)
