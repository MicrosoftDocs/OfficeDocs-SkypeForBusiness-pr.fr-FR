---
title: Gérer les stratégies et paramètres d’application personnalisés
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer des stratégies et des paramètres d’application personnalisés pour contrôler qui dans votre organisation peut charger des applications personnalisées dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681385"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams

> [!NOTE]
> Pour utiliser App Studio, consultez [Démarrage sur la plateforme Microsoft Teams avec C#/.NET et App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) La dernière étape ne fonctionne pas encore. Vous devrez donc télécharger le zip et l’installer à l’ancienne à [Télécharger un package d’application pour Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).

En tant qu’administrateur, vous pouvez utiliser des stratégies et des paramètres d’application personnalisés pour contrôler qui dans votre organisation peut charger des applications personnalisées dans Microsoft Teams. Les administrateurs décident quels utilisateurs peuvent charger des applications personnalisées, et les administrateurs et les propriétaires d’équipe peuvent déterminer si des équipes spécifiques de votre organisation autorisent l’ajout d’applications personnalisées.  Après avoir modifié la stratégie d’application personnalisée, quelques heures peuvent être nécessaires pour que les modifications prennent effet. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

## <a name="overview-of-custom-apps"></a>Vue d’ensemble des applications personnalisées

Les utilisateurs peuvent ajouter une application personnalisée à Teams en chargeant un package d’application (dans un fichier .zip) directement à une équipe ou dans le contexte personnel. Cela diffère de la façon dont les applications sont ajoutées via l’app store Teams. L’ajout d’une application personnalisée en chargeant un package d’application, également appelé chargement indépendant, vous permet de tester une application en cours de développement, avant qu’elle ne soit largement distribuée. Il vous permet également de créer une application pour une utilisation interne uniquement et de la partager avec votre équipe sans l’envoyer au catalogue d’applications Teams dans l’app store Teams.

![Capture d’écran montrant l’option charger une application personnalisée dans l’App Store.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Stratégie et paramètres d’application personnalisés

Trois composants déterminent si un utilisateur peut charger une application personnalisée dans une équipe, ce qui vous donne un contrôle précis sur les personnes qui peuvent ajouter des applications personnalisées à une équipe et les applications personnalisées teams à ajouter :

- [Stratégie d’application personnalisée de l’utilisateur](#user-custom-app-policy)
- [Paramètre d’application personnalisée d’équipe](#team-custom-app-setting)
- [Paramètre d’application personnalisée à l’échelle de l’organisation](#org-wide-custom-app-setting)

Ces paramètres n’affectent pas la possibilité de bloquer les applications tierces.  

### <a name="user-custom-app-policy"></a>Stratégie d’application personnalisée de l’utilisateur

Dans le cadre des [stratégies d’installation d’application](teams-app-setup-policies.md), les administrateurs peuvent utiliser un paramètre de stratégie **, Télécharger des applications personnalisées**, pour contrôler si un utilisateur peut charger des applications personnalisées dans Teams.

Si ce paramètre est désactivé :

- L’utilisateur ne peut pas charger une application personnalisée vers une équipe de votre organisation ou dans le contexte personnel.
- L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est activé :

- L’utilisateur peut charger des applications personnalisées vers les équipes qui l’autorisent et vers les équipes dont il est propriétaire, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.
- L’utilisateur peut charger des applications personnalisées dans le contexte personnel.
- L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres de la stratégie d’installation d’application globale pour inclure les applications souhaitées. Si vous souhaitez personnaliser Teams pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies d’installation d’application personnalisées.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée par l’utilisateur

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Applications Teams** > **Stratégies de configuration**.
2. Cliquez sur **Ajouter**.
3. Activez ou désactivez **Télécharger applications personnalisées**.
4. Choisissez les autres paramètres que vous souhaitez pour la stratégie.
5. Cliquez sur **Enregistrer**.

### <a name="team-custom-app-setting"></a>Paramètre d’application personnalisée d’équipe

Les administrateurs et les propriétaires d’équipe peuvent contrôler si une équipe autorise l’ajout d’applications personnalisées. Ce paramètre permet **aux membres de charger des applications personnalisées**, ainsi que la stratégie d’application personnalisée d’un utilisateur détermine qui peut ajouter des applications personnalisées à une équipe particulière.

Si ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées, si leur stratégie d’application personnalisée l’autorise.
- Les membres de l’équipe qui ne sont pas propriétaires d’équipe ne peuvent pas ajouter d’applications personnalisées à l’équipe.

Si ce paramètre est activé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées, si leur stratégie d’application personnalisée le permet.
- Les membres de l’équipe qui ne sont pas propriétaires d’équipe peuvent ajouter des applications personnalisées, si leur stratégie d’application personnalisée le permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre d’application personnalisée de l’équipe

1. Dans Teams, accédez à l’équipe, cliquez sur **Autres options...** >  **Gérer l’équipe**.
2. Cliquez sur **Paramètres**, puis développez **les autorisations de membre**.
3. Activez ou désactivez la case à cocher **Autoriser les membres à charger des applications personnalisées** .

    ![Capture d’écran montrant le paramètre d’application personnalisée de l’équipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’organisation

Le paramètre **Autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation dans la page [Gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent charger ou interagir avec des applications personnalisées. Ce paramètre agit comme un commutateur maître activé/désactivé pour les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe. Il est destiné à servir de commutateur principal lors des événements de sécurité. Par conséquent, les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe ne prendront effet que si le paramètre d’application personnalisée à l’échelle de l’organisation est activé même si les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe sont activés.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre d’application personnalisée à l’échelle de l’organisation

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Cliquez sur **Paramètres de l’application à l’échelle de l’organisation**.
3. Sous **Applications personnalisées**, activez ou **désactivez Autoriser l’interaction avec les applications personnalisées**.

    ![Capture d’écran montrant les paramètres d’application personnalisée à l’échelle de l’organisation.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Fonctionnement des stratégies et des paramètres d’application personnalisés

Ce tableau récapitule la stratégie et les paramètres d’application personnalisés, la façon dont ils fonctionnent ensemble et leur effet combiné sur le contrôle des utilisateurs de votre organisation qui peuvent charger des applications personnalisées dans Teams.

Par exemple, vous souhaitez autoriser uniquement les propriétaires d’équipe à charger des applications personnalisées vers des équipes spécifiques. Vous devez définir les éléments suivants :

- Activez le paramètre **Autoriser l’interaction avec les applications personnalisées** dans le centre d’administration Microsoft Teams.
- Désactivez **l’option Autoriser les membres à charger des applications personnalisées** pour chaque équipe à laquelle vous souhaitez restreindre l’accès.
- Créez et attribuez une stratégie d’installation d’application personnalisée dans le centre d’administration Microsoft Teams avec le **paramètre d’applications personnalisées Télécharger** activé, puis attribuez-la aux propriétaires de l’équipe.

|Paramètre d’application personnalisée à l’échelle de l’organisation |Paramètre d’application personnalisée d’équipe |Stratégie d’application personnalisée de l’utilisateur |Effet  |
|---------|---------|---------|---------|
| Désactivé    | Désactivé    | Désactivé     |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être téléchargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.   |
| Désactivé     | Désactivé     | Activé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être téléchargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Désactivé    | Activé        | Désactivé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être téléchargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser Windows PowerShell pour supprimer des applications personnalisées.         |
| Désactivé    | Activé      | Activé       |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être téléchargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Activé    | Désactivé       | Désactivé         |  L’utilisateur ne peut pas charger d’applications personnalisées.      |
| Activé     | Désactivé       | Activé         | Si l’utilisateur est propriétaire d’une équipe, il peut charger des applications personnalisées dans l’équipe. Si l’utilisateur n’est pas propriétaire d’une équipe, il ne peut pas charger d’applications personnalisées dans l’équipe. L’utilisateur peut charger des applications personnalisées dans le contexte personnel.     |
| Activé     | Activé     | Désactivé         | L’utilisateur ne peut pas charger d’applications personnalisées.       |
| Activé    | Activé        | Activé        | L’utilisateur peut charger des applications personnalisées dans l’équipe, que l’utilisateur soit ou non propriétaire de l’équipe. L’utilisateur peut charger des applications personnalisées dans le contexte personnel.       |

## <a name="related-topics"></a>Sujets associés

[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies-users-and-groups.md)
