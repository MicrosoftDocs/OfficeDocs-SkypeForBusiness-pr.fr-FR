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
description: Découvrez comment gérer les stratégies et paramètres d’application personnalisées pour contrôler les membres de votre organisation qui peuvent télécharger des applications personnalisées dans Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: b2225429eee73ecd5c6b33b62d4d1be24da306b9
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442540"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams

> [!NOTE]
> Pour utiliser App Studio, voir Démarrer sur la plateforme [Microsoft Teams avec C#/.NET et App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) La dernière étape ne fonctionne pas encore. Vous devrez donc télécharger le zip et l’installer à l’ancienne sur [Télécharger un package](/microsoftteams/platform/concepts/apps/apps-upload) d’application pour Microsoft Teams.

En tant qu’administrateur, vous pouvez utiliser les stratégies et paramètres d’application personnalisés pour contrôler les membres de votre organisation qui peuvent télécharger des applications personnalisées sur Microsoft Teams. Les administrateurs déterminent quels utilisateurs peuvent télécharger des applications personnalisées, et les administrateurs et les propriétaires d’équipe peuvent déterminer si des équipes spécifiques de votre organisation autorisent l’ajout d’applications personnalisées.  Après avoir modifié la stratégie d’application personnalisée, l’application des modifications peut prendre quelques heures. Vous devez être un administrateur général ou un administrateur du service Teams pour gérer ces stratégies.

## <a name="overview-of-custom-apps"></a>Vue d’ensemble des applications personnalisées

Les utilisateurs peuvent ajouter une application personnalisée à Teams en téléchargeant un package d’application (dans un fichier .zip) directement à une équipe ou dans le contexte personnel. Cette différence est différente de la manière dont les applications sont ajoutées via Teams app store. L’ajout d’une application personnalisée en chargeant un package d’application (également appelé chargement test) vous permet de tester une application au cours de son développement avant qu’elle soit prête à être distribuée à grande échelle. Il vous permet également de créer une application pour un usage interne uniquement et de la partager avec votre équipe sans la soumettre au catalogue d’applications Teams du Teams App Store.

![Capture d’écran montrant l’option télécharger une application personnalisée dans le magasin d’applications.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Stratégie et paramètres d’application personnalisés

Trois composants déterminent si un utilisateur peut télécharger une application personnalisée dans une équipe, ce qui vous donne un contrôle plus important sur les personnes qui peuvent ajouter des applications personnalisées à une équipe et les applications personnalisées d’équipes qui peuvent être ajoutées :

- [Stratégie d’application personnalisée utilisateur](#user-custom-app-policy)
- [Paramètre de l’application personnalisée d’équipe](#team-custom-app-setting)
- [Paramètre d’application personnalisée à l’échelle de l’organisation](#org-wide-custom-app-setting)

Ces paramètres n’affectent pas la possibilité de bloquer des applications tierces.  

### <a name="user-custom-app-policy"></a>Stratégie d’application personnalisée utilisateur

Dans [le cadre des](teams-app-setup-policies.md) stratégies de configuration d’application, les administrateurs peuvent utiliser un paramètre de **stratégie, Télécharger** applications personnalisées, pour contrôler si un utilisateur peut télécharger des applications personnalisées sur Teams.

Si ce paramètre est désactivé :

- L’utilisateur ne peut pas télécharger une application personnalisée pour une équipe de votre organisation ou dans son contexte personnel.
- L’utilisateur peut interagir avec les applications personnalisées, selon le paramètre d’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est désactivé :

- Selon le paramètre de l’application personnalisée à l’échelle de l’organisation, l’utilisateur peut télécharger des applications personnalisées dans les équipes qui le autorisent et pour les équipes dont ils sont propriétaires.
- L’utilisateur peut télécharger des applications personnalisées dans son contexte personnel.
- L’utilisateur peut interagir avec les applications personnalisées, selon le paramètre d’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres de la stratégie de configuration d’application globale pour inclure les applications que vous souhaitez utiliser. Si vous voulez personnaliser Teams pour différents groupes d’utilisateurs de votre organisation, créez et affectez une ou plusieurs stratégies de configuration d’application personnalisées.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée par l’utilisateur

1. Dans le navigation gauche du Microsoft Teams d’administration, voir Teams **d’applicationsSetup** > .
2. Cliquez sur **Ajouter**.
3. Activer ou désactiver Télécharger **applications personnalisées**.
4. Choisissez d’autres paramètres pour la stratégie.
5. Cliquez sur **Enregistrer**.

### <a name="team-custom-app-setting"></a>Paramètre de l’application personnalisée d’équipe

Les administrateurs et les propriétaires d’équipe peuvent contrôler si une équipe autorise l’ajout d’applications personnalisées. Ce paramètre, **Autoriser les membres à télécharger des** applications personnalisées, de même que la stratégie d’application personnalisée d’un utilisateur, détermine qui peut ajouter des applications personnalisées à une équipe particulière.

Si ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
- Les membres d’une équipe qui ne sont pas propriétaires de l’équipe ne peuvent pas ajouter des applications personnalisées à l’équipe.

Si ce paramètre est désactivé :

- Les propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.
- Les membres d’une équipe qui ne sont pas propriétaires d’équipe peuvent ajouter des applications personnalisées si leur stratégie d’application personnalisée le permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre d’application personnalisée d’équipe

1. Dans Teams, allez à l’équipe, cliquez sur Plus **d’options s s** **sManage** >  team.
2. Cliquez **Paramètres** sur, puis développez **les autorisations Membres**.
3. Cochez ou **cochez la case Autoriser les membres à télécharger des applications** personnalisées.

    ![Capture d’écran montrant le paramètre de l’application personnalisée d’équipe.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’organisation

Le paramètre **autoriser l’interaction** avec les applications personnalisées à l’échelle de l’organisation sur [la page Gérer](manage-apps.md) les applications s’applique à tous les membres de votre organisation et décide s’ils peuvent télécharger des applications personnalisées ou interagir avec elles. Ce paramètre agit comme commutateur maître dans les paramètres de stratégie d’application personnalisée de l’utilisateur et de l’équipe. Il est conçu pour servir de commutateur maître pendant les événements de sécurité. Ainsi, les paramètres de stratégie d’application personnalisée des utilisateurs et des équipes ne prennent effet que si le paramètre d’application personnalisée à l’échelle de l’organisation est activé, même si les paramètres de stratégie d’application personnalisées de l’utilisateur et de l’équipe sont activés.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre d’application personnalisée à l’échelle de l’organisation

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Cliquez **sur les paramètres de l’application à l’échelle de l’organisation**.
3. Sous **Applications personnalisées**, activer ou désactiver **l’application Autoriser l’interaction avec les applications personnalisées**.

    ![Capture d’écran montrant les paramètres d’application personnalisée à l’échelle de l’organisation.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Fonctionnement des stratégies et paramètres d’application personnalisés

Ce tableau récapitule la stratégie et les paramètres d’application personnalisées, la façon dont elles fonctionnent ensemble et leur effet combiné sur le contrôle des membres de votre organisation qui peuvent télécharger des applications personnalisées sur Teams.

Par exemple, vous voulez autoriser uniquement les propriétaires d’équipes à télécharger des applications personnalisées dans des équipes spécifiques. Vous devez définir ce qui suit :

- Activer le paramètre **Autoriser l’interaction avec les applications** personnalisées dans le Microsoft Teams d’administration.
- Désactiver **l’application Autoriser les membres à télécharger des applications personnalisées** pour chaque équipe à laquelle vous souhaitez limiter l’accès.
- Créez et affectez une stratégie de configuration d’application personnalisée dans le Centre d’administration Microsoft Teams avec le paramètre **d’Télécharger** d’applications personnalisées désactivé et affectez-le aux propriétaires d’équipe.

|Paramètre d’application personnalisée à l’échelle de l’organisation |Paramètre de l’application personnalisée d’équipe |Stratégie d’application personnalisée utilisateur |Effet  |
|---------|---------|---------|---------|
| Désactivé    | Désactivé    | Désactivé     |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent pas être téléchargées par tout le monde sauf un Teams de service ou un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.   |
| Désactivé     | Désactivé     | Activé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent pas être téléchargées par tout le monde sauf un Teams de service ou un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Désactivé    | Activé        | Désactivé        |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent pas être téléchargées par tout le monde sauf un Teams de service ou un administrateur global. Vous pouvez utiliser Windows PowerShell pour supprimer des applications personnalisées.         |
| Désactivé    | Activé      | Activé       |L’interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Les applications personnalisées ne peuvent pas être téléchargées par tout le monde sauf un Teams de service ou un administrateur global. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Activé    | Désactivé       | Désactivé         |  L’utilisateur ne peut pas télécharger d’applications personnalisées.      |
| Activé     | Désactivé       | Activé         | Si l’utilisateur est propriétaire de l’équipe, il peut télécharger des applications personnalisées dans l’équipe. Si l’utilisateur n’est pas propriétaire de l’équipe, il ne peut pas télécharger d’applications personnalisées dans l’équipe. L’utilisateur peut télécharger des applications personnalisées dans son contexte personnel.     |
| Activé     | Activé     | Désactivé         | L’utilisateur ne peut pas télécharger d’applications personnalisées.       |
| Activé    | Activé        | Activé        | L’utilisateur peut télécharger des applications personnalisées à l’équipe, que l’utilisateur en soit le propriétaire ou non. L’utilisateur peut télécharger des applications personnalisées dans son contexte personnel.       |

## <a name="related-topics"></a>Voir aussi

[Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)

[Attribuer des stratégies à vos utilisateurs](assign-policies-users-and-groups.md)
