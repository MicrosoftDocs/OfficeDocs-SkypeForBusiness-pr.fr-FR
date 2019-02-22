---
title: Tableau de bord Analyse des appels et Qualité des appels
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
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
ms.openlocfilehash: b3a65c4fa6a3dfe8de6b4ef70cd7657661cf4dc9
ms.sourcegitcommit: d3c459dc1304db5f5ba78b5e093b5a4fd797c8ec
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2019
ms.locfileid: "30178668"
---
# <a name="call-analytics-and-call-quality-dashboard"></a>Tableau de bord Analyse des appels et Qualité des appels

Microsoft Teams et Skype pour les entreprises permettent de deux manières pour surveiller et résoudre les problèmes de qualité des appels : Analytique d’appel et appel du tableau de bord qualité. Cet article décrit les deux et vous indique quand utiliser chacune d’elles.

Appel Analytique CQD s’exécuter en parallèle et peuvent être utilisés indépendamment ou ensemble. Par exemple, un spécialiste du support détermine qu’ils ont besoin d’aide pour résoudre un problème d’appel de communications. Les spécialistes de prise en charge des communications passe l’appel vers un ingénieur du support communications, qui a accès à plus d’informations à prendre en charge les communications spécialiste dans Analytique appeler. À son tour, l’ingénieur du support technique communications alerte ingénieur réseau à un problème. L’ingénieur réseau peut vérifier CQD pour voir si un problème général liés au site peut être une contribue cause de problèmes d’appel.

## <a name="whats-call-analytics-and-when-should-i-use-it"></a>What ' s Analytique appeler et quand dois-je utiliser ?

**Appel Analytique est désormais disponible dans le centre d’administration Microsoft Teams.** Pour afficher toutes les informations d’appel et les données d’un utilisateur, utilisez l’onglet **Historique des appels** . Vous pouvez procéder par la recherche sur la page de profil utilisateur par une recherche de l’utilisateur du tableau de bord ou la recherche de l’utilisateur des **utilisateurs** dans le volet de navigation gauche.

> [!IMPORTANT]
> Autorisations de l’agent de support technique et le téléchargement de topologie réseau seront disponibles dans le nouveau portail d’administration dans les mois à venir. En attendant, vous pouvez continuer à utiliser https://adminportal.services.skypeforbusiness.com pour l’accès de support technique de niveau 1 et niveau 2.
  

Appel Analytique affiche des informations détaillées sur les périphériques, les réseaux et connectivité liés aux appels spécifiques et des réunions pour chaque utilisateur de Microsoft Teams Skype pour un compte professionnel. Pourquoi cet utilisateur ont un appel médiocre après‑midi ? À l’aide d’Analytique d’appel, un administrateur Office 365 ou l’agent de support technique formé peut examiner le périphérique, réseau, connectivité et autres facteurs liés à son appel pour résoudre les problèmes de qualité et connexion appel dans Microsoft Teams et Skype pour les entreprises.

Pour afficher ces informations pour un utilisateur dans le centre d’administration Microsoft Teams, cliquez sur l’onglet **Historique des appels** pour cet utilisateur dans la page de détails utilisateur, en affichant tous les appels et les réunions que l’utilisateur a participé à des 30 derniers jours.

![Données utilisateur d’appel analytique.](media/call-analytics-user-data.png)

Pour obtenir des informations supplémentaires sur une session donnée, y compris media détaillées et les statistiques du réseau, cliquez sur une session pour voir les détails.

![Appeler des données de session utilisateur analytique.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

Si vous souhaitez que non-Admin, tels que les agents de support technique d’un fournisseur externe, pour utiliser l’appel Analytique, vous pouvez attribuer les autorisations afin qu’ils peuvent utiliser Analytique d’appel, mais ils ne peuvent pas accéder le reste du centre d’administration Microsoft Teams : 
  
- **Prend en charge les agents de support technique avec communications autorisations spécialiste**: Agents voir un ensemble limité de données et les informations d’identification personnelle (PII) dans l’appel d’Analytique. Ils peuvent résoudre les appels, mais ils transmet des problèmes avec les réunions pour un ingénieur du support technique communications.
    
- **Prend en charge les agents de support technique avec communications ingénieur autorisations**: Agents voir toutes les données disponibles dans Analytique appeler et résoudre les problèmes d’appels et les réunions. Ils ont un accès total à appeler des journaux et des informations sur le client.

> [!NOTE]
> Le rôle de spécialiste de prise en charge des communications est équivalent au support de niveau 1 et le rôle ingénieur de prise en charge des communications est équivalent au support de niveau 2.

Pour plus d’informations sur les communications spécialiste prise en charge et les communications prennent en charge les rôles ingénieur, voir [utiliser les équipes Microsoft des rôles d’administration pour gérer les équipes](using-admin-roles.md).

> [!IMPORTANT]
> Autorisations de l’agent de support technique et téléchargement de topologie réseau sont disponibles dans le centre d’administration Microsoft Teams. Spécialistes du Support de communications et de Communications ingénieurs du support technique peuvent utiliser ce portail pour accéder aux Analytique des appels et le tableau de bord qualité des appels.
    
Pour plus d’informations sur la configuration Analytique d’appel, voir [Set up Skype pour Business appeler Analytique](set-up-call-analytics.md). Pour plus d’informations sur comment les agents du support technique peuvent fonctionner avec Analytique d’appel, voir [Utiliser appel Analytique pour résoudre les problèmes d’appel de mauvaise qualité](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="whats-the-call-quality-dashboard-and-when-should-i-use-it"></a>Quel est le tableau de bord qualité des appels, et quand dois-je utiliser ?
  
Autorité de certification est conçue pour aider les administrateurs et les agents de support technique résoudre les problèmes de qualité d’appel avec des appels spécifiques, où le tableau de bord de qualité des appels (CQD) est conçu pour aider les administrateurs Microsoft Teams, Skype pour les administrateurs d’entreprise, et optimisent un réseau les ingénieurs réseau. CQD déplace le focus des utilisateurs spécifiques et au lieu de cela examine compilent les informations pour un ensemble de Microsoft Teams ou Skype pour l’organisation de l’entreprise. Pour plus d’informations, voir [fonctionnalités du tableau de bord qualité des appels pour Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md#BKMKFeaturesOfTheCQD).
  
La qualité des appels médiocres l’utilisateur est peut-être en raison d’un problème de réseau qui affecte également le nombre d’autres utilisateurs. L’expérience de l’appel n’est pas visible dans CQD, mais la qualité globale d’appels effectués à l’aide de Microsoft Teams ou Skype pour les entreprises est capturée. Avec le CQD, global modèles peuvent apparaître, permettant ainsi aux ingénieurs réseau à évaluer informé de la qualité des appels. CQD fournit des rapports des mesures de qualité des appels qui vous expliqueront globale appellent qualité, flux serveur-client, flux client client et qualité de voix [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252).
  
![Capture d’écran du tableau de bord de qualité des appels. Les onglets affichés sont SLA de qualité de voix globale la qualité des appels et serveur - Client, Client - Client.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

À l’aide de rapports de Location-Enhanced de CQD, la qualité des appels agrégation et la fiabilité de la création de l’utilisateur peuvent être évaluées pour déterminer si le problème est isolé à un seul utilisateur ou affecte un segment supérieur d’utilisateurs.

![Capture d’écran des rapports d’emplacement hautement appel qualité du tableau de bord. Les onglets affichés sont vue d’ensemble, bâtiments - filaire, bâtiments - Wi-Fi et Mobile (ETL). Un filtre est appliqué pour afficher le flux de données dans un bâtiment en particulier.](media/call-quality-dashboard-location-enhanced-reports-building-selection.png)

> [!NOTE]
> Pour activer la construction spécifiques dans CQD, un administrateur doit [télécharger les informations de création](turning-on-and-using-call-quality-dashboard.md#BKMKBuildingInformationUpload) sur la page de téléchargement des données client du CQD.

Si vous souhaitez que non-Admin, tels que les agents du support technique, pour utiliser l’appel du tableau de bord qualité, vous pouvez affecter ces utilisateurs le rôle de **l’Ingénieur du Support technique équipes Communications**, **Spécialiste des équipes Communications prise en charge**ou **Lecteur de rapports** . Les utilisateurs avec les rôles suivants peuvent accéder tableau de bord qualité des appels :

- Administrateur global
- Skype pour administrateur
- Administrateur du service Teams
- Administrateur des communications Teams
- Ingénieur du support technique pour les communications Teams
- Spécialiste des équipes Communications prise en charge
- Lecteur de rapports

> [!NOTE]
> Les rôles ingénieur du Support technique équipes Communications, spécialiste des équipes Communications prise en charge et rapports de lecteur ne peut pas modifier les fichiers sur la page de téléchargement des données client du CQD ni activer CQD pour un client.

Pour plus d’informations sur ces rôles, voir [rôles d’administrateur sur Office 365](/office365/admin/add-users/about-admin-roles).

Pour plus d’informations sur CQD, voir [activation et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md) et les [Dimensions et mesures disponibles dans les appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](dimensions-and-measures-available-in-call-quality-dashboard.md).
  
## <a name="related-topics"></a>Rubriques connexes

[Vidéo : Vue d’ensemble de la qualité des appels](https://aka.ms/teams-quality)

[Configurer Analyse des appels](set-up-call-analytics.md)

[Utiliser l’Analyse des appels pour résoudre les problèmes de qualité des appels](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activation et à l’aide de tableau de bord qualité d’appel pour Microsoft Teams et Skype pour Business Online](turning-on-and-using-call-quality-dashboard.md)