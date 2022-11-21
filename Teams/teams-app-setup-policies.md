---
title: Gérer les stratégies de mise en application dans Microsoft Teams
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
description: Découvrez comment créer, modifier et gérer des stratégies d’installation d’applications pour épingler des applications, installer des applications et permettre aux utilisateurs de charger des applications personnalisées.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4c94f0610535fa014b0f759b104dd1aef901e055
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131003"
---
# <a name="use-app-setup-policies-to-pin-and-auto-install-apps-in-teams"></a>Utiliser des stratégies de configuration des applications pour épingler et installer automatiquement des applications dans Teams

En tant qu’administrateur, vous utilisez des stratégies de configuration d’application pour installer et épingler des applications, et contrôler quels utilisateurs spécifiques peuvent charger des applications personnalisées. L’épinglage permet de promouvoir l’adoption des applications pertinentes de votre organisation et de fournir un accès rapide.

* **[Épingler des applications](#pin-apps) :** Les stratégies de configuration des applications vous permettent de choisir les applications à épingler, de définir l’ordre dans lequel les applications s’affichent pour vos utilisateurs dans la barre de l’application Teams ou dans la zone de rédaction des messages. Les administrateurs peuvent également contrôler si les utilisateurs finaux peuvent ou ne peuvent pas épingler leurs propres applications.

* **[Installer des applications](#install-apps) :** Les stratégies de configuration des applications vous permettent d’installer les applications autorisées pour le compte des utilisateurs lorsqu’ils démarrent Teams et pendant les réunions.

* **Charger des applications personnalisées :** Les stratégies de configuration des applications vous permettent de contrôler les utilisateurs qui peuvent charger des applications personnalisées dans Teams. Consultez [l’article Charger des applications personnalisées](teams-custom-app-policies-and-settings.md) .

Les stratégies d’installation d’application intégrées suivantes sont disponibles dans le Centre d’administration Microsoft Teams, par défaut :

* **Global (par défaut à l’échelle de l’organisation)** : cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie. Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.

* **FirstlineWorker**: cette stratégie s’applique aux employés de première ligne. La stratégie ne peut pas être personnalisée. Vous pouvez l’attribuer aux employés de première ligne de votre organisation.

## <a name="pin-apps"></a>Épingler des applications

L’épinglage d’une application affiche l’application dans la barre de l’application dans le client Teams. Les administrateurs peuvent épingler une application et autoriser les utilisateurs à épingler. L’épinglage est utilisé pour mettre en évidence les applications dont les utilisateurs ont le plus besoin et favoriser la facilité d’accès. L’épinglage fonctionne pour tous les [types d’applications dans Teams](deploy-apps-microsoft-teams-landing-page.md) : applications principales, applications fournies par Microsoft, applications tierces et applications personnalisées développées au sein de votre organisation.

Les administrateurs peuvent épingler une application via une stratégie de configuration d’application. Les applications épinglées par les administrateurs sont automatiquement installées pour les utilisateurs pour lesquels l’application est autorisée. Une telle application ne peut pas être désinstallée par les utilisateurs finaux. À l’aide d’une stratégie de configuration d’application, vous pouvez effectuer les tâches suivantes :

* Personnalisez Teams pour les utilisateurs finaux afin de mettre en évidence les applications les plus importantes pour eux. Vous choisissez les applications à épingler et l’ordre dans lequel les applications s’affichent.
* Contrôlez si les utilisateurs peuvent épingler des applications ou non.

Les applications sont épinglées à la barre des applications sur le côté gauche du client de bureau Teams et en bas des clients mobiles Teams. Les extensions de messagerie sont disponibles en bas de la zone de rédaction du message.

|Client de bureau Teams  |Client mobile Teams |
|---------|---------|
|![Capture d’écran montrant la barre de l’application dans le client de bureau Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Capture d’écran montrant la barre de l’application dans le client mobile Teams.](media/mobile-app-ui.png)      |

Pour épingler des applications à l’aide d’une stratégie de configuration d’application, procédez de la manière suivante :

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Sélectionnez **Ajouter**.

1. Entrez un nom pour votre stratégie, ainsi qu’une description.

1. Si vous le souhaitez, activez **l’épinglage utilisateur** pour permettre aux utilisateurs d’épingler des applications et de modifier l’ordre des applications épinglées.

1. Sous **Applications épinglées**, sélectionnez **Ajouter des applications**.

1. Dans le volet **Ajouter des applications épinglées**, recherchez les applications que vous souhaitez ajouter, puis sélectionnez **Ajouter**.

    :::image type="content" source="media/add-pinned-apps-trimmed.png" alt-text="Captures d’écran montrant comment ajouter des applications épinglées dans la stratégie de configuration d’application." lightbox="media/add-pinned-apps-large.png":::

1. Sélectionnez **Ajouter**.

1. Sous la **barre de l’application** ou les **extensions de messagerie**, organisez les applications dans l’ordre dans lequel vous souhaitez qu’elles apparaissent dans le client Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Capture d’écran des applications épinglées et des extensions de messagerie épinglées dans la stratégie d’installation.":::

1. Sélectionnez **Enregistrer**.

> [!NOTE]
> Dans Teams pour l’Éducation, l’application Affectations est épinglée par défaut dans la stratégie globale, même si elle ne figure pas dans la stratégie globale.

> [!NOTE]
> Pour les employés de première ligne de votre organisation, nous vous recommandons d’utiliser l’expérience d’application de première ligne personnalisée. Cette fonctionnalité épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [Licence F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline). Pour en savoir plus, consultez [Personnaliser les applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Installer des applications

À l’aide d’une stratégie de configuration d’application, un administrateur peut effectuer les tâches suivantes :

* Installez des applications pour les utilisateurs finaux dans leur environnement Teams personnel.
* Installez des applications pour les utilisateurs finaux en tant qu’[extensions de messagerie](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Les utilisateurs finaux peuvent installer des applications par eux-mêmes si la [stratégie d’autorisation d’application](teams-app-permission-policies.md) leur permet de les installer et si l’application est autorisée par l’administrateur Teams. Si une application est bloquée, les utilisateurs finaux peuvent [demander l’approbation de l’administrateur](user-requests-approve-apps.md).

Pour installer des applications à l’aide d’une stratégie de configuration d’application, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Sélectionnez **Ajouter**.

1. Fournissez un nom et une description pour la stratégie.

1. Sous **Applications installées**, sélectionnez **Ajouter des applications**.

1. Dans le volet **Ajouter des applications installées** , recherchez les applications que vous souhaitez installer pour les utilisateurs. Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.

1. Sélectionnez **Ajouter**.

:::image type="content" source="media/install-apps-in-meeting.png" alt-text="Capture d’écran de l’installation d’applications via une stratégie d’application.":::

## <a name="manage-app-setup-policies"></a>Gérer les stratégies de configuration des applications

Vous gérez les stratégies de configuration des applications dans le Centre d’administration Microsoft Teams. Utilisez la stratégie globale (par défaut à l’échelle de l’organisation) ou créez et attribuez des stratégies personnalisées. Les utilisateurs finaux obtiennent la stratégie globale. Si vous créez une stratégie personnalisée, elle remplace la stratégie globale. L’administrateur général ou l’administrateur de service Teams peut gérer ces stratégies.

Vous modifiez les paramètres de la stratégie globale pour inclure les applications souhaitées. Pour personnaliser Teams pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées.

:::image type="content" source="media/app-setup-policies-update.png" alt-text="Capture d’écran montrant la page stratégies de configuration de l’application avec des options pour gérer des stratégies ou ajouter de nouvelles stratégies.":::

### <a name="edit-an-app-setup-policy"></a>Modifier une stratégie de configuration d’application

Vous pouvez utiliser le Centre d’administration Microsoft Teams pour modifier une stratégie, y compris la stratégie globale (par défaut à l’échelle de l’organisation) et les stratégies personnalisées que vous créez. Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Choisissez la stratégie à modifier, puis sélectionnez **Modifier**.

1. Apportez les modifications souhaitées.

1. Sélectionnez **Enregistrer**.

### <a name="assign-a-custom-policy-in-app-setup-policy-to-users-and-groups"></a>Affecter une stratégie personnalisée dans la stratégie de configuration d’application à des utilisateurs et des groupes

Pour savoir comment attribuer des stratégies à vos utilisateurs finaux et à des groupes, découvrez [comment attribuer des stratégies à des utilisateurs et des groupes](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Considérations et limitations

* Vous ne pouvez pas installer d’applications personnalisées avec des onglets configurables à l’aide de stratégies de configuration d’application.

* Les utilisateurs finaux ne peuvent pas désinstaller une application installée par un administrateur.

* Les utilisateurs finaux peuvent désépingler une application épinglée via la stratégie de configuration d’application si l’épinglage utilisateur est autorisé dans la stratégie.

* Les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur les clients mobiles et de bureau Teams si l’option d’épinglage utilisateur est activée. Les utilisateurs ne peuvent pas modifier l’ordre de leurs applications épinglées sur les clients web Teams.

* Les épingles d’administration sont toujours prioritaires. Si l’option Épinglage utilisateur est activée, les applications épinglées par les utilisateurs s’affichent sous les applications épinglées par les administrateurs. Si l’option Épinglage utilisateur est désactivée, les utilisateurs perdent les épingles existantes et seules les applications épinglées par les administrateurs sont disponibles dans la barre de l’application.

* Le paramètre d’épinglage utilisateur est disponible dans le Centre d’administration Teams dans les environnements Microsoft 365 Government Community Cloud (GCC, GCC High et DoD), mais il n’a aucun effet.

* Dans Teams pour l’Éducation, l’application Affectations est épinglée par défaut dans la stratégie globale, même si elle ne figure pas dans la stratégie globale.

* Le nombre maximal d’applications épinglées que vous pouvez ajouter à une stratégie n’est pas limité. Toutefois, au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android). Si une stratégie a moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.

* Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

* Certaines applications ne peuvent pas être épinglées à Teams via une stratégie de configuration des applications. Cette fonctionnalité n’est pas prise en charge par toutes les applications. Pour rechercher les applications qui peuvent être épinglées, recherchez l’application dans le volet **Ajouter des applications épinglées**. Les onglets qui ont une étendue personnelle (onglets statiques) et des bots peuvent être épinglés au client de bureau Teams et ces applications sont disponibles dans le volet **Ajouter des applications épinglées**. Tandis que le magasin d’applications Teams répertorie toutes les applications Teams. Le volet **Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.

* Dans Teams pour l'éducation, l’application Appel n’est pas disponible. Lorsque vous créez une stratégie personnalisée dans la stratégie de configuration d’application, l’application Appel s’affiche dans la liste des applications. Toutefois, l’application n’est pas épinglée pour les clients Teams et les utilisateurs de Teams pour l’éducation ne verront pas l’application Appels dans Teams.

## <a name="related-articles"></a>Articles connexes

* [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
* [Attribuer des stratégies aux utilisateurs finaux dans Teams](assign-policies-users-and-groups.md)
