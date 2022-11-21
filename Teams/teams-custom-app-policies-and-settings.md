---
title: Gérer les stratégies et les paramètres d’application personnalisés et chargés de manière indépendante
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment gérer les stratégies et les paramètres pour contrôler qui dans votre organisation peut charger une version test des applications et charger des applications personnalisées.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 19f18d89ec2f423c1531639adb630992bdbdc547
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69130993"
---
# <a name="manage-custom-and-sideloaded-apps-in-teams-admin-center"></a>Gérer les applications personnalisées et chargées de manière indépendante dans le Centre d’administration Teams

Microsoft Teams permet aux développeurs au sein de votre organisation de créer, tester et déployer des applications personnalisées pour les utilisateurs internes de l’organisation. Ces applications sont appelées applications personnalisées ou applications métier (LOB). Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques. Les administrateurs contrôlent le déploiement des autorisations et pour les applications personnalisées à l’aide de différents paramètres et stratégies.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Capture d’écran montrant comment autoriser les applications personnalisées de votre organisation dans le panneau des paramètres à l’échelle de l’organisation." lightbox="media/custom-app-orgwide-setting.png":::

Une fois que vous avez autorisé l’utilisation d’une application personnalisée, vos utilisateurs finaux peuvent la trouver en sélectionnant **Créé pour votre organisation** dans le volet de navigation gauche du magasin Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Capture d’écran des applications personnalisées dans le magasin Teams dans l’application de bureau teams." lightbox="media/built-for-your-org2.png":::

En tant qu’administrateur Teams, vous utilisez des stratégies et des paramètres d’application personnalisés pour contrôler qui, dans votre organisation, peut charger des applications personnalisées dans Microsoft Teams. Les administrateurs décident quels utilisateurs peuvent télécharger des applications personnalisées, et les administrateurs et les propriétaires d'équipe peuvent déterminer si des équipes spécifiques de votre organisation autorisent l'ajout d'applications personnalisées. Une fois que vous avez modifié la stratégie d’application personnalisée, quelques heures sont nécessaires pour que les modifications prennent effet. Vous devez être administrateur de service Global Administration ou Teams pour gérer ces stratégies.

Les développeurs au sein de votre organisation peuvent ajouter une application personnalisée à Teams en téléchargeant un paquet d'applications (dans un fichier .zip) directement dans une équipe ou dans le contexte personnel. Cette méthode est différente de la façon dont les applications sont ajoutées via le magasin d’applications Teams. L’ajout d’une application personnalisée en chargeant un package d’application, également appelé chargement indépendant, permet à des utilisateurs spécifiques au sein de votre organisation de tester une application, avant qu’elle ne soit prête à être largement distribuée.

<!--- During the creation of an app, the developers create and add an app ID to the manifest file. You can view this external app ID on the Manage apps page after you enable the column `External app ID` from the column settings. You can also view it on the app details page of a custom app. The ID is applicable for custom apps only. --->

## <a name="understand-sideloading-of-custom-apps"></a>Comprendre le chargement indépendant des applications personnalisées

Lors du développement d’applications personnalisées et avant de les distribuer aux utilisateurs finaux, les développeurs testent les applications en les ajoutant à Teams Store pour les tester. Les développeurs peuvent tester eux-mêmes ou avec un groupe d’utilisateurs spécifié, mais l’application n’est pas disponible pour les autres utilisateurs finaux de l’organisation via le Store. Cette méthode est appelée chargement indépendant des applications et s’applique uniquement aux applications personnalisées.

Les développeurs peuvent recourir au chargement indépendant d’une application pour la mettre à la disposition des membres d’une équipe spécifique, généralement pour tester une application en cours de développement. De cette manière, seuls les développeurs de l’application peuvent l’utiliser sans nécessiter l’autorisation de l’administrateur, à condition que ce dernier autorise le chargement indépendant dans Teams.

Les développeurs peuvent partager une application chargée de manière indépendante avec une équipe spécifique sans la soumettre au catalogue d’applications Teams. Il rend l’application personnalisée chargée de manière indépendante disponible pour un groupe limité d’utilisateurs finaux, mais pas dans le magasin d’applications de votre organisation pour tous les utilisateurs finaux.

En tant qu’administrateur, vous pouvez interdire le chargement indépendant de l’application pour tous les développeurs. Si vous interdisez le chargement indépendant, les développeurs peuvent toujours tester leurs applications en [créant un client de test distinct](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Une fois le développement d’applications personnalisées terminé, les développeurs demandent aux administrateurs de distribuer leur application personnalisée aux utilisateurs finaux. Pour plus d’informations, consultez [comment publier une application personnalisée](/microsoftteams/upload-custom-apps). En tant qu’administrateur, vous autorisez (ou bloquez) l’utilisation d’une application personnalisée pour tous les utilisateurs ou pour des utilisateurs spécifiques.

## <a name="custom-app-policy-and-settings"></a>Stratégie et paramètres d’application personnalisés

Trois paramètres déterminent si un utilisateur peut charger une application personnalisée dans une équipe. Il permet aux administrateurs de contrôler de manière précise qui peut ajouter des applications personnalisées à une équipe et à quelles équipes les applications personnalisées peuvent être ajoutées. Ces paramètres n’affectent pas la possibilité de bloquer des applications tierces.

* [Stratégie utilisateur et application](#user-custom-app-policy)
* [Paramètre d’application personnalisée d’équipe](#team-custom-app-setting)
* [Paramètre d’application personnalisée à l’échelle de l’organisation](#org-wide-custom-app-setting)

### <a name="user-custom-app-policy"></a>Stratégie utilisateur et application

Dans le cadre des [stratégies de configuration](teams-app-setup-policies.md) des applications, les administrateurs peuvent utiliser le paramètre **Charger des applications personnalisées** pour contrôler si un utilisateur peut charger des applications personnalisées dans Teams.

Par défaut, ce paramètre est désactivé :

* L’utilisateur ne peut pas charger une application personnalisée vers une équipe de votre organisation ou dans le contexte personnel.
* L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est désactivé :

* L’utilisateur peut télécharger des applications personnalisées vers des équipes qui l’autorisent et vers des équipes pour lesquelles il est propriétaire, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.
* L’utilisateur peut télécharger des applications personnalisées dans le contexte personnel.
* L’utilisateur peut interagir avec des applications personnalisées, en fonction du paramètre d’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres dans la stratégie globale pour y inclure les applications de votre choix. Si vous voulez personnaliser Teams pour différents groupes d’utilisateurs au sein de votre organisation, vous pouvez créer et attribuer une ou plusieurs stratégies personnalisées.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée par l’utilisateur

1. Connectez-vous au Centre d’administration Teams et accédez aux stratégies **[d’installation des](https://admin.teams.microsoft.com/policies/app-setup)** **applications** >  Teams.
1. Sélectionnez **Ajouter**.
1. Fournissez un nom et une description pour la stratégie.
1. Activez ou désactivez le paramètre **Charger des applications personnalisées** .
1. Choisissez les autres paramètres que vous souhaitez pour la stratégie.
1. Sélectionnez **Enregistrer**.
1. [Appliquez la stratégie aux utilisateurs](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) qui développent des applications personnalisées et sont autorisés à charger ces applications.

> [!NOTE]
> Pour modifier ce paramètre, autorisez les applications personnalisées dans les [paramètres de l’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

### <a name="team-custom-app-setting"></a>Paramètre d’application personnalisée d’équipe

Les administrateurs et les propriétaires d’équipe peuvent contrôler si une équipe autorise l’ajout d’applications personnalisées. Ce paramètre, **Autoriser les membres à charger des applications personnalisées**, ainsi que la stratégie d’application personnalisée d’un utilisateur détermine qui peut ajouter des applications personnalisées à une équipe particulière.

Par défaut, ce paramètre est désactivé :

* Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
* Les membres de l’équipe qui ne sont pas propriétaires de l’équipe ne peuvent pas ajouter d’applications personnalisées à l’équipe.

Si ce paramètre est désactivé :

* Les propriétaires d’équipe peuvent ajouter des applications personnalisées, si leur stratégie d’application personnalisée le permet.
* Les membres de l’équipe qui ne sont pas propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre d’application personnalisée de l’équipe

1. Dans Teams, accédez à une équipe, puis sélectionnez **Plus d’options ...** >  **Gérer l’équipe**.
1. Sélectionnez **Paramètres** et développez **Autorisations de membre**.
1. Cochez ou videz la case **Autoriser les membres à télécharger des applications personnalisées**.

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="Capture d’écran montrant le paramètre d’application personnalisée de l’équipe." lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’organisation

Le paramètre **Autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation sur la page [Gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent charger ou interagir avec des applications personnalisées. Ce paramètre agit comme un commutateur maître activé/désactivé pour les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe. Il est destiné à servir de commutateur principal lors des événements de sécurité. Les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe prennent effet uniquement après avoir activé le paramètre d’application personnalisée à l’échelle de l’organisation.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre d’application personnalisée à l’échelle de l’organisation

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Sélectionnez **Paramètres de l’application à l’échelle de l’organisation**.
1. Sous **Applications personnalisées**, activer ou désactiver **Autoriser l’interaction avec les applications personnalisées**.

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="Capture d’écran montrant les paramètres d’application personnalisée à l’échelle de l’organisation.":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>Fonctionnement commun des paramètres et des stratégies d’application personnalisées

Ce tableau résume la politique et les paramètres des applications personnalisées, la manière dont ils fonctionnent ensemble, et leur effet combiné sur le contrôle des personnes de votre organisation qui peuvent télécharger des applications personnalisées sur Teams.

Par exemple, vous souhaitez autoriser uniquement les propriétaires d’équipe à charger des applications personnalisées vers des équipes spécifiques. Vous devez définir ce qui suit :

* Activez le paramètre **Autoriser l’interaction avec les applications personnalisées** dans le Centre d’administration Microsoft Teams.
* Désactiver les membres **Autoriser les membres à télécharger des applications personnalisées** pour chaque équipe à laquelle vous souhaitez restreindre l’accès.
* Créez et affectez une stratégie personnalisée dans la stratégie de configuration des applications dans le Centre d’administration Microsoft Teams avec le paramètre **Charger des applications personnalisées** activé, puis affectez-la aux propriétaires de l’équipe.

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

* [Administration paramètres pour les applications dans Teams](admin-settings.md).
* [Affectez des stratégies à vos utilisateurs dans Teams](assign-policies-users-and-groups.md).
