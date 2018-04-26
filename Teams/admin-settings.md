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
ms.openlocfilehash: 50490b08986f1a8f312aa79d5492b1ed8a97ecc8
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Paramètres d'administration pour les applications dans Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Les applications sont des onglets, des connecteurs, des robots ou n’importe quelle combinaison de ces trois, fournie par un service tiers. Il existe des stratégies d’admin équipes qui peuvent être configurés dans le centre d’administration Office 365 pour contrôler les applications de tiers externes sont autorisées. Ces stratégies vous permettent de spécifier les applications qui sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications à chargement latéral est autorisé.

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

> [!NOTE]
> Applications par défaut, tels que ceux créés par Microsoft, ne sont pas affectées par le paramètre **activer de nouvelles applications externes par défaut** .

Lorsque cette option est activée, les utilisateurs peuvent activer les nouvelles applications dès qu'elles sont ajoutées au catalogue d'applications Teams. Pour ouvrir le catalogue d'applications Teams, cliquez sur **Store** en bas de Teams et cliquez sur **Applications**. Si vous souhaitez contrôler la disponibilité des applications, désactivez cette option. Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes. 

Le chargement de version test consiste à ajouter un application à Teams en chargeant un fichier .zip directement dans une équipe. Le chargement de version test vous permet de tester une application au fur et à mesure qu'elle est développée. Il vous permet également de créer une application à des fins d'utilisation interne uniquement et de la partager avec votre équipe sans l'envoyer dans le catalogue d'applications Teams dans l'Office Store. 

Seuls les propriétaires ou membres d'équipes autorisés peuvent charger la version test d'une application dans Teams.  

![Capture d’écran de la section applications de développé dans les paramètres clients.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a>Création et chargement de packages d'application 

Pour en savoir plus sur les applications, voir [développer des applications pour les équipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



