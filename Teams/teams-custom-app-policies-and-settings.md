---
title: Gérer les stratégies et paramètres d’application personnalisés
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer les stratégies et paramètres d’application personnalisés pour contrôler les utilisateurs de votre organisation qui peuvent télécharger des applications personnalisées dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 454d3b4a057b15ad0f329434f541cd03d2b41a7f
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938453"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams

> [!NOTE]
> Pour utiliser app Studio, voir mise [en route sur la plateforme Microsoft teams avec C#/.net et App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) la dernière étape ne fonctionne pas pour le moment, vous devrez donc télécharger le code postal et l’installer dans l’ancien moyen de [Télécharger un package d’application dans Microsoft teams](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload).

En tant qu’administrateur, vous pouvez utiliser des stratégies et des paramètres d’application personnalisés pour contrôler qui, au sein de votre organisation, peut télécharger des applications personnalisées dans Microsoft Teams. Les administrateurs décident quels utilisateurs peuvent télécharger des applications personnalisées, et les administrateurs et propriétaires d’équipe peuvent déterminer si des équipes spécifiques de votre organisation autorisent leur ajout d’applications personnalisées.  Après la modification de la stratégie d’application personnalisée, l’entrée en vigueur des modifications peut prendre quelques heures. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

## <a name="overview-of-custom-apps"></a>Vue d’ensemble des applications personnalisées

Les utilisateurs peuvent ajouter une application personnalisée aux équipes en chargeant un package d’application (dans un fichier. zip) directement dans une équipe ou dans le contexte personnel. C’est différent de la façon dont les applications sont ajoutées par le biais de l’App Store Teams. L’ajout d’une application personnalisée en chargeant un package d’application, également connu sous le nom de chargement indépendant, vous permet de tester une application au fur et à mesure qu’elle est développée, avant qu’elle ne soit prête à être diffusée. Elle vous permet également de générer une application pour une utilisation interne uniquement et de la partager avec votre équipe sans l’envoyer au catalogue d’applications teams dans le magasin d’applications Teams.

![Capture d’écran montrant l’option Télécharger une application personnalisée dans l’App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Stratégie et paramètres d’application personnalisés

Trois composants permettent de déterminer si un utilisateur peut télécharger une application personnalisée dans une équipe, en vous offrant un contrôle précis sur les personnes qui peuvent ajouter des applications personnalisées à une équipe et celles auxquelles des applications personnalisées peuvent être ajoutées :

- [Stratégie d’application personnalisée utilisateur](#user-custom-app-policy)
- [Paramètre de l’application personnalisée d’équipe](#team-custom-app-setting)
- [Paramètre d’application personnalisée à l’échelle de l’Organisation](#org-wide-custom-app-setting)

Ces paramètres n’affectent pas la possibilité de bloquer des applications tierces.  

### <a name="user-custom-app-policy"></a>Stratégie d’application personnalisée utilisateur

Dans le cadre de [stratégies de configuration des applications](teams-app-setup-policies.md), les administrateurs peuvent utiliser un paramètre de stratégie et télécharger des **applications personnalisées**pour contrôler si un utilisateur peut télécharger des applications personnalisées dans Teams.
 
Si ce paramètre est désactivé :

- L’utilisateur ne peut pas télécharger une application personnalisée dans une équipe de votre organisation ou dans le contexte personnel.
- Les utilisateurs peuvent interagir avec les applications personnalisées, en fonction du paramètre de l’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est activé, procédez comme suit :

- L’utilisateur peut télécharger des applications personnalisées dans teams pour le permettre aux équipes pour lesquelles il s’agit de propriétaires, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.
- L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel. 
- Les utilisateurs peuvent interagir avec les applications personnalisées, en fonction du paramètre de l’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres de la stratégie de configuration de l’application globale de manière à inclure les applications souhaitées. Si vous voulez personnaliser teams pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies de configuration d’application personnalisées.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée par un utilisateur

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration des **applications teams**  >  **Setup policies**.
2. Cliquez sur **Ajouter**.
3. Activez ou désactivez l’option **Télécharger des applications personnalisées**.
4. Choisissez tout autre paramètre souhaité pour la stratégie.
5. Cliquez sur **Enregistrer**.

### <a name="team-custom-app-setting"></a>Paramètre de l’application personnalisée d’équipe

Les administrateurs et les propriétaires d’équipe peuvent contrôler si une équipe permet d’y ajouter des applications personnalisées. Ce paramètre **permet de permettre aux membres de télécharger des applications personnalisées**, ainsi que de définir la stratégie d’application personnalisée d’un utilisateur, qui peut ajouter des applications personnalisées à une équipe particulière.
 
Si ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
- Les membres d’une équipe qui ne sont pas des propriétaires d’équipe ne peuvent pas ajouter des applications personnalisées à l’équipe.

Si ce paramètre est activé, procédez comme suit :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
- Les membres d’une équipe qui ne sont pas des propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre de l’application personnalisée d’équipe

1. Dans Teams, accédez à l’équipe, cliquez sur **plus d’options ̇ ̇ ̇**  >  **gérer l’équipe**.
2. Cliquez sur **paramètres**, puis développez **autorisations de membre**.
3. Activez ou désactivez la case à cocher **autoriser les membres à télécharger des applications personnalisées** .

    ![Capture d’écran montrant le paramètre de l’application personnalisée d’équipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’Organisation

Le paramètre **autoriser les interactions avec les applications personnalisées** de l’organisation sur la page [gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent télécharger des applications personnalisées ou interagir avec celles-ci. Ce paramètre a pour priorité l’utilisation de la stratégie et du paramètre d’application personnalisés pour l’utilisateur et l’équipe. Il est conçu pour être utilisé en tant que commutateur d’activation/désactivation du maître lors des événements de sécurité.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre de l’application personnalisée à l’échelle de l’Organisation

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps.
2. Cliquez sur **paramètres de l’application à l’échelle de l’organisation**.
3. Sous **applications personnalisées**, activez ou désactivez l’option **autoriser l’interaction avec les applications personnalisées**.

    ![Capture d’écran montrant les paramètres de l’application personnalisée à l’échelle de l’Organisation](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Fonctionnement des stratégies et paramètres d’application personnalisés

Le tableau suivant résume la stratégie et les paramètres de l’application personnalisée, la façon dont ils fonctionnent conjointement et leurs effets combinés sur le contrôle des membres de votre organisation qui peuvent télécharger des applications personnalisées dans Teams.

Par exemple, supposons que vous souhaitiez autoriser uniquement les propriétaires d’équipe à télécharger des applications personnalisées dans des équipes spécifiques. Vous devez définir les éléments suivants :
- Activez le paramètre **autoriser les interactions avec les applications personnalisées** dans le centre d’administration Microsoft Teams.
- Désactivez l’option **autoriser les membres à télécharger des applications personnalisées** pour toutes les équipes auxquelles vous voulez limiter l’accès.
- Dans le centre d’administration de Microsoft Teams, créez et attribuez une stratégie de configuration d’application personnalisée avec le paramètre **Télécharger les applications personnalisées** activé et attribuez-la aux propriétaires de l’équipe.

|Paramètre d’application personnalisée à l’échelle de l’Organisation |Paramètre de l’application personnalisée d’équipe |Stratégie d’application personnalisée utilisateur |Pris  |
|---------|---------|---------|---------|
| Désactivé    | Désactivé    | Désactivé     |Les interactions avec toutes les applications personnalisées sont bloquées pour votre organisation. Les applications personnalisées ne peuvent pas être chargées par tout le monde à l’exception de l’administrateur de service teams ou d’un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.   |
| Désactivé     | Désactivé     | Activé        |Les interactions avec toutes les applications personnalisées sont bloquées pour votre organisation. Les applications personnalisées ne peuvent pas être chargées par tout le monde à l’exception de l’administrateur de service teams ou d’un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Désactivé    | Activé        | Désactivé        |Les interactions avec toutes les applications personnalisées sont bloquées pour votre organisation. Les applications personnalisées ne peuvent pas être chargées par tout le monde à l’exception de l’administrateur de service teams ou d’un administrateur global. Vous pouvez utiliser Windows PowerShell pour supprimer des applications personnalisées.         |
| Désactivé    | Activé      | Activé       |Les interactions avec toutes les applications personnalisées sont bloquées pour votre organisation. Les applications personnalisées ne peuvent pas être chargées par tout le monde à l’exception de l’administrateur de service teams ou d’un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Activé    | Désactivé       | Désactivé         |  L’utilisateur ne peut pas charger des applications personnalisées.      |
| Activé     | Désactivé       | Activé         | S’il s’agit d’un propriétaire d’équipe, il peut télécharger des applications personnalisées à l’équipe. Si l’utilisateur n’est pas propriétaire d’une équipe, il ne peut pas charger d’applications personnalisées dans l’équipe. L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.     |
| Activé     | Activé     | Désactivé         | L’utilisateur ne peut pas charger des applications personnalisées.       |
| Activé    | Activé        | Activé        | L’utilisateur peut télécharger des applications personnalisées dans l’équipe, qu’il s’agisse d’un propriétaire d’équipe ou non. L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.       |

## <a name="related-topics"></a>Sujets associés
 
[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)