---
title: Paramètres d'administration pour les applications dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Découvrez comment autoriser et activer des applications dans Microsoft Teams, y compris le chargement de version test d'applications externes.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58fb8598f8e63aa3e8abc943dcffde64452da462
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Paramètres d'administration pour les applications dans Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Les applications sont des onglets, des connecteurs et des bots ou toute combinaison de ces éléments, fournis par un service tiers. Des stratégies d'administration Teams peuvent être configurées dans le Centre d'administration Office 365 pour contrôler l'autorisation d'applications tierces externes. Ces stratégies vous permettent de spécifier les applications autorisées et non autorisées, le comportement d'une nouvelle application externe, ainsi que l'autorisation du chargement de version test d'applications.

> [!NOTE]
> Pour gérer les paramètres d’administration dans Teams, accédez au centre d’administration Office 365 et ouvrez l’option **Paramètres** > **Services et compléments**, puis sélectionnez **Microsoft Teams**. Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option :
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Pour en savoir plus sur les paramètres d’administration, regardez la vidéo suivante : 
 
|  |  |
|---------|---------|
| Gestion de l’expérience des applications dans Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Autoriser les applications externes dans Teams

Par défaut, le paramètre **Autoriser les applications externes dans Microsoft Teams** est activé avec toutes les applications sélectionnées.  Si vous désactivez cette option, tous les applications tierces externes sont désactivées. 

## <a name="enable-new-external-apps-by-default"></a>Activer les applications externes nouvelles par défaut

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophée : meilleure pratique : gérer les applications externes individuellement 
 
Pour activer certaines applications (et en désactiver d'autres), désactivez l'option **Autoriser le chargement de version test d'applications externes**. Ensuite, désactivez les applications que vous ne voulez pas que les utilisateurs utilisent. Facultatif : désactivez l'option **Activer les applications externes nouvelles par défaut** (si vous souhaitez contrôler les nouvelles applications). 

Lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams. Pour ouvrir le catalogue d'applications Teams, cliquez sur **Store** en bas de Teams et cliquez sur **Applications**. Si vous souhaitez contrôler la disponibilité des applications, désactivez cette option. Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes. 

Le chargement de version test consiste à ajouter un application à Teams en chargeant un fichier .zip directement dans une équipe. Le chargement de version test vous permet de tester une application au fur et à mesure qu'elle est développée. Il vous permet également de créer une application à des fins d'utilisation interne uniquement et de la partager avec votre équipe sans l'envoyer dans le catalogue d'applications Teams dans l'Office Store. 

Seuls les propriétaires ou membres d'équipes autorisés peuvent charger la version test d'une application dans Teams.  

![Capture d’écran de la section applications de développé dans les paramètres clients.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)


## <a name="creating-and-uploading-app-packages"></a>Création et chargement de packages d'application 

Pour en savoir plus sur les applications, consultez le document [Développer des applications pour Teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



