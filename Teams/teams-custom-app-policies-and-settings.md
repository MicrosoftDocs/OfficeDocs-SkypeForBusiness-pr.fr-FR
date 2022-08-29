---
title: Gérer les stratégies et paramètres d’application personnalisés
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
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
description: Découvrez comment gérer des stratégies et paramètres d’application personnalisés pour contrôler les personnes de votre organisation qui peuvent charger des applications personnalisées dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 7ff0a37d815b3118aea0eb63abc8a414c4a99bd5
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397245"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser des stratégies et paramètres d’application personnalisés pour contrôler les personnes de votre organisation qui peuvent télécharger des applications personnalisées vers Microsoft Teams. Les administrateurs décident quels utilisateurs peuvent télécharger des applications personnalisées, et les administrateurs et les propriétaires d'équipe peuvent déterminer si des équipes spécifiques de votre organisation autorisent l'ajout d'applications personnalisées.  Après avoir modifié la stratégie d’application personnalisée, l’application des modifications peut prendre quelques heures. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

Les développeurs au sein de votre organisation peuvent ajouter une application personnalisée à Teams en téléchargeant un paquet d'applications (dans un fichier .zip) directement dans une équipe ou dans le contexte personnel. Cette méthode est différente de celle utilisée pour ajouter des applications dans le magasin d'applications Teams. L’ajout d’une application personnalisée en chargeant un package d’application, également appelé chargement indépendant, permet à des utilisateurs spécifiques au sein de votre organisation de tester une application, avant qu’elle ne soit prête à être largement distribuée.

## <a name="custom-app-policy-and-settings"></a>Stratégie et paramètres d’application personnalisés

Trois composants déterminent si un utilisateur peut charger une application personnalisée dans une équipe, ce qui vous donne un contrôle précis sur les personnes qui peuvent ajouter des applications personnalisées à une équipe et les applications personnalisées Teams à ajouter :

- [Stratégie utilisateur et application](#user-custom-app-policy)
- [Paramètre d’application personnalisée d’équipe](#team-custom-app-setting)
- [Paramètre d’application personnalisée à l’échelle de l’organisation](#org-wide-custom-app-setting)

Ces paramètres n’affectent pas la possibilité de bloquer des applications tierces.  

### <a name="user-custom-app-policy"></a>Stratégie utilisateur et application

Dans le cadre des [stratégies de configuration des applications](teams-app-setup-policies.md), les administrateurs peuvent utiliser un paramètre de stratégie **Charger des applications personnalisées** pour contrôler si un utilisateur peut charger des applications personnalisées dans Teams.

Par défaut, ce paramètre est désactivé :

- L’utilisateur ne peut pas charger une application personnalisée vers une équipe de votre organisation ou dans le contexte personnel.
- L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est désactivé :

- L’utilisateur peut télécharger des applications personnalisées vers des équipes qui l’autorisent et vers des équipes pour lesquelles il est propriétaire, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.
- L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.
- L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres dans la stratégie globale pour y inclure les applications de votre choix. Si vous voulez personnaliser Teams pour différents groupes d’utilisateurs au sein de votre organisation, vous pouvez créer et attribuer une ou plusieurs stratégies personnalisées.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée par l’utilisateur

1. Connectez-vous au Centre d’administration Teams et accédez aux stratégies **[d’installation](https://admin.teams.microsoft.com/policies/app-setup)** des **applications** >  Teams.
1. Sélectionnez **Ajouter**.
1. Activez ou désactivez **Charger des applications personnalisées**.
1. Choisissez les autres paramètres que vous souhaitez pour la stratégie.
1. Sélectionnez **Enregistrer**.

### <a name="team-custom-app-setting"></a>Paramètre d’application personnalisée d’équipe

Les administrateurs et les propriétaires d’équipe peuvent contrôler si une équipe autorise l’ajout d’applications personnalisées. Ce paramètre, **Autoriser les membres à charger des applications personnalisées**, ainsi que la stratégie d’application personnalisée d’un utilisateur détermine qui peut ajouter des applications personnalisées à une équipe particulière.

Par défaut, ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
- Les membres de l’équipe qui ne sont pas propriétaires de l’équipe ne peuvent pas ajouter d’applications personnalisées à l’équipe.

Si ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées, si leur stratégie d’application personnalisée le permet.
- Les membres de l’équipe qui ne sont pas propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre d’application personnalisée de l’équipe

1. Dans Teams, accédez à une équipe, puis sélectionnez **Plus d’options ...** >  **Gérer l’équipe**.
2. Sélectionnez **Paramètres** et développez **les autorisations de membre**.
3. Cochez ou videz la case **Autoriser les membres à télécharger des applications personnalisées**.

    ![Capture d’écran montrant le paramètre d’application personnalisée de l’équipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’organisation

Le paramètre **Autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation sur la page [Gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent charger ou interagir avec des applications personnalisées. Ce paramètre agit comme un commutateur maître activé/désactivé pour les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe. Il est destiné à servir de commutateur principal lors des événements de sécurité. Par conséquent, les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe ne prendront effet que si le paramètre d’application personnalisée à l’échelle de l’organisation est activé même si les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe sont activés.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre d’application personnalisée à l’échelle de l’organisation

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Sélectionnez **les paramètres de l’application à l’échelle de l’organisation**.
1. Sous **Applications personnalisées**, activer ou désactiver **Autoriser l’interaction avec les applications personnalisées**.

    ![Capture d’écran montrant les paramètres d’application personnalisée à l’échelle de l’organisation.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Fonctionnement commun des paramètres et des stratégies d’application personnalisées

Ce tableau résume la politique et les paramètres des applications personnalisées, la manière dont ils fonctionnent ensemble, et leur effet combiné sur le contrôle des personnes de votre organisation qui peuvent télécharger des applications personnalisées sur Teams.

Par exemple, vous souhaitez autoriser uniquement les propriétaires d’équipe à charger des applications personnalisées vers des équipes spécifiques. Vous devez définir ce qui suit :

- Activez le paramètre **Autoriser l’interaction avec les applications personnalisées** dans le Centre d’administration Microsoft Teams.
- Désactiver les membres **Autoriser les membres à télécharger des applications personnalisées** pour chaque équipe à laquelle vous souhaitez restreindre l’accès.
- Créez et affectez une stratégie de configuration d’application personnalisée dans le Centre d’administration Microsoft Teams avec le paramètre **Charger le paramètre des applications personnalisées**, puis l’affecter aux propriétaires de l’équipe.

|Paramètre d’application personnalisée à l’échelle de l’organisation |Paramètre d’application personnalisée d’équipe |Stratégie utilisateur et application |Effet  |
|---------|---------|---------|---------|
| Désactivé    | Désactivé    | Désactivé     |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être chargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.   |
| Désactivé     | Désactivé     | Activé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être chargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Désactivé    | Activé        | Désactivé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être téléchargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser Windows PowerShell pour supprimer des applications personnalisées.         |
| Désactivé    | Activé      | Activé       |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent être chargées par personne à l’exception d’un Administration de service Teams ou d’un administrateur général. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Activé    | Désactivé       | Désactivé         |  L’utilisateur ne peut pas charger d’applications personnalisées.      |
| Activé     | Désactivé       | Activé         | Si l’utilisateur est propriétaire de l’équipe, il peut télécharger des applications personnalisées vers l’équipe. Si l’utilisateur n’est pas propriétaire d’une équipe, il ne peut pas charger d’applications personnalisées dans l’équipe. L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.     |
| Activé     | Activé     | Désactivé         | L’utilisateur ne peut pas charger d’applications personnalisées.       |
| Activé    | Activé        | Activé        | L’utilisateur peut télécharger des applications personnalisées vers l’équipe, que l’utilisateur soit propriétaire ou non de l’équipe. L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.       |

## <a name="related-articles"></a>Articles connexes

- [Administration paramètres pour les applications dans Teams](admin-settings.md).
- [Affectez des stratégies à vos utilisateurs dans Teams](assign-policies-users-and-groups.md).
