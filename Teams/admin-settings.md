---
title: Paramètres d'administration pour les applications dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag
description: Découvrez comment autoriser et activer des applications dans Microsoft Teams, y compris le chargement de version test d'applications externes.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: da73768f69159c32543d0843139facc2b9ef4f9a
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706354"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Paramètres d'administration pour les applications dans Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Les applications sont des onglets, des connecteurs, des robots ou n’importe quelle combinaison de ces trois fournies par les équipes (applications internes et également appelé applications par défaut) ou par un tiers (également appelées applications externes). Dans le centre d’administration Microsoft 365, vous pouvez activer et désactiver des applications par défaut et configurer les paramètres pour contrôler les applications externes. Ces paramètres vous permettent de spécifier les applications externes sont autorisées et non autorisées, le nouveau comportement de l’application externe, et si les applications côté-chargement est autorisé.

 Pour gérer les paramètres d’administration pour les applications dans les équipes, accédez au centre d’administration Microsoft 365 et choisissez **paramètres** > **compléments Services &** > **Équipes Microsoft**. Si vous êtes connecté en tant qu’administrateur d’Office 365, ce lien vous dirige sur cette option :

https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Pour en savoir plus sur les paramètres d’administration, regardez la vidéo suivante : 
 
|  |  |
|---------|---------|
| Gestion de l’expérience des applications dans Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Autoriser les applications externes dans Teams

Par défaut, le paramètre **Autoriser les applications externes dans Microsoft Teams** est activé avec toutes les applications sélectionnées.  Si vous désactivez ce paramètre, toutes les applications tierces externes sont désactivées. 

## <a name="enable-new-external-apps-by-default"></a>Activer les applications externes nouvelles par défaut

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophée : meilleure pratique : gérer les applications externes individuellement 
 
Pour activer certaines applications (et en désactiver d'autres), désactivez l'option **Autoriser le chargement de version test d'applications externes**. Ensuite, désactivez les applications que vous ne voulez pas que les utilisateurs utilisent. Facultatif : désactivez l'option **Activer les applications externes nouvelles par défaut** (si vous souhaitez contrôler les nouvelles applications). 

> [!NOTE]
> Applications par défaut, telles que celles créées par Microsoft, ne sont pas affectées par le paramètre **activer de nouvelles applications externes par défaut** . Nouvelles applications sont activées par défaut lorsque l’utilisateur relâche par Microsoft.

Lorsque ce paramètre est activé, les utilisateurs peuvent activer des nouvelles applications dès qu’elles sont ajoutées au catalogue d’applications équipes. Pour ouvrir le catalogue d'applications Teams, cliquez sur **Store** en bas de Teams et cliquez sur **Applications**. Si vous souhaitez contrôler les applications qui sont disponibles, désactivez ce paramètre. Bien sûr, si vous la désactivez, n'oubliez pas de vérifier régulièrement les nouvelles applications afin que votre organisation ne passe pas à côté de nouvelles applications intéressantes. 

Le chargement de version test consiste à ajouter un application à Teams en chargeant un fichier .zip directement dans une équipe. Le chargement de version test vous permet de tester une application au fur et à mesure qu'elle est développée. Il vous permet également de créer une application à des fins d'utilisation interne uniquement et de la partager avec votre équipe sans l'envoyer dans le catalogue d'applications Teams dans l'Office Store. 

Seuls les propriétaires ou membres d'équipes autorisés peuvent charger la version test d'une application dans Teams.  

![Capture d’écran de la section applications externes développée.] (media/teams-tenant-wide-settings-external-apps.png "Capture d’écran de la section applications externes développée avec des applications externes")

## <a name="creating-and-uploading-app-packages"></a>Création et chargement de packages d'application 

Pour en savoir plus sur les applications, voir [Develop apps pour les équipes](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



