---
title: Gérer les stratégies de mise en application dans Microsoft Teams
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
description: Découvrez comment créer, modifier et gérer des stratégies d’installation d’applications pour épingler des applications, installer des applications et permettre aux utilisateurs de charger des applications personnalisées.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: cfcd041fd755016ec04832f42c497e2b0ad51469
ms.sourcegitcommit: ebffec34c050421dc8d09a16907644657ce323f4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2022
ms.locfileid: "67637007"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gérer les stratégies de mise en application dans Microsoft Teams

En tant qu’administrateur, vous utilisez des stratégies de configuration d’application pour installer et épingler des applications, et autoriser les utilisateurs à charger des applications personnalisées. L’épinglage permet de promouvoir l’adoption d’applications pertinentes dans votre organisation.

* **Épingler des applications :** Les stratégies d’installation d’applications vous permettent de choisir les applications à épingler, de définir l’ordre dans lequel les applications s’affichent pour vos utilisateurs dans la barre des applications Teams ou dans la zone de composition des messages. Les administrateurs peuvent également contrôler si les utilisateurs finaux peuvent ou ne peuvent pas épingler leurs propres applications. Consultez [Épingler des applications](#pin-apps).
* **Installer des applications :** Les stratégies de configuration des applications vous permettent d’installer les applications autorisées pour le compte des utilisateurs lorsqu’ils démarrent Teams et pendant les réunions. Pour plus d’informations, consultez [Installer des applications](#install-apps).
* **Charger des applications personnalisées :** Les stratégies de configuration des applications vous permettent d’autoriser les utilisateurs à charger des applications personnalisées dans Teams. Pour plus d’informations, consultez [Charger des applications personnalisées](teams-custom-app-policies-and-settings.md).

Les stratégies d’installation d’application intégrées suivantes sont disponibles dans le Centre d’administration Microsoft Teams, par défaut :

* **Global (par défaut à l’échelle de l’organisation)** : cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie. Modifiez la stratégie globale pour épingler les applications les plus importantes pour vos utilisateurs.

* **FirstlineWorker**: cette stratégie s’applique aux employés de première ligne. La stratégie ne peut pas être personnalisée. Vous pouvez l’attribuer aux employés de première ligne de votre organisation.

## <a name="pin-apps"></a>Épingler des applications

L’épinglage d’applications vous permet de mettre en évidence les applications dont les utilisateurs de votre organisation ont le plus besoin. L’épinglage fonctionne pour tous les types d’applications dans Teams : les applications principales, les applications fournies par Microsoft, les applications tierces et les applications personnalisées développées au sein de votre organisation. L’épinglage d’une application via une stratégie de configuration d’application l’installe également, si l’application est autorisée pour l’utilisateur. À l’aide d’une stratégie de configuration d’application, vous pouvez effectuer les tâches suivantes :

* Personnalisez Microsoft Teams pour les utilisateurs finaux afin de mettre en évidence les applications les plus importantes pour eux. Vous choisissez les applications à épingler et l’ordre dans lequel les applications s’affichent.
* Contrôlez si les utilisateurs peuvent épingler des applications ou non.

Les applications sont épinglées à la barre des applications sur le côté gauche du client de bureau Teams et en bas des clients mobiles Teams.

|Client de bureau Teams  |Client mobile Teams |
|---------|---------|
|![Barre d’applications dans le client de bureau Teams.](media/app-setup-policies-desktop-app-bar.png).  |   ![Barre d’applications dans le client mobile Teams.](media/mobile-app-ui.png)      |

Les extensions de messagerie sont disponibles en bas de la zone de rédaction du message.

Pour épingler des applications à l’aide d’une stratégie de configuration d’application, procédez de la manière suivante :

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.

1. Sélectionnez **Ajouter**.

1. Entrez un nom pour votre stratégie, ainsi qu’une description.

1. Activez **Épinglage par l’utilisateur**.

   > [!NOTE]
   > Le paramètre **Épinglage par l’utilisateur** est disponible dans le Centre d’administration Teams dans les environnements Microsoft 365 Cloud de la communauté du secteur public (GCC, GCC High et DoD), mais il n’a aucun effet.

1. Sous **Applications épinglées**, sélectionnez **Ajouter des applications**.

1. Dans le volet **Ajouter des applications épinglées**, recherchez les applications que vous souhaitez ajouter, puis sélectionnez **Ajouter**. Vous pouvez également filtrer les applications par stratégie d’autorisation d’application.

1. Sélectionnez **Ajouter**.

1. Sous **Barre de l’application** ou **Extensions de messagerie**, organisez les applications dans l’ordre dans lequel vous souhaitez qu’elles apparaissent dans Teams.

   :::image type="content" source="media/pin-messaging-extensions.png" alt-text="Capture d’écran des applications épinglées et des extensions de messagerie épinglées dans la stratégie d’installation.":::

1. Sélectionnez **Enregistrer**.

> [!NOTE]
> Dans Teams pour l’Éducation, l’application Affectations est épinglée par défaut dans la stratégie globale, même si elle ne figure pas dans la stratégie globale.

> [!NOTE]
> Pour les employés de première ligne de votre organisation, nous vous recommandons d’utiliser l’expérience d’application de première ligne personnalisée. Cette fonctionnalité épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [Licence F](https://www.microsoft.com/en-us/microsoft-365/enterprise/frontline?rtc=1#office-SKUChooser-0dbn8nt). Pour en savoir plus, consultez [Personnaliser les applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

## <a name="install-apps"></a>Installer des applications

À l’aide d’une stratégie de configuration d’application, un administrateur peut effectuer les tâches suivantes :

* Installez des applications pour les utilisateurs finaux dans leur environnement Teams personnel.
* Installez des applications pour les utilisateurs finaux en tant qu’[extensions de messagerie](/microsoftteams/platform/messaging-extensions/what-are-messaging-extensions).

Les utilisateurs finaux peuvent installer des applications par eux-mêmes si la [stratégie d’autorisation d’application](teams-app-permission-policies.md) les autorise et que l’application est autorisée par l’administrateur Teams. Au lieu de cela, si une application est bloquée pour un utilisateur ou une organisation, les utilisateurs finaux peuvent [demander l’approbation de l’administrateur](user-requests-approve-apps.md).

Pour installer des applications à l’aide d’une stratégie d’installation d’application, procédez comme suit :

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

![Page Stratégies de configuration d’application pour gérer les stratégies ou ajouter de nouvelles stratégies.](media/app-setup-policies-update.png)

### <a name="edit-an-app-setup-policy"></a>Modifier une stratégie de configuration d’application

Vous pouvez utiliser le Centre d’administration Microsoft Teams pour modifier une stratégie, y compris la stratégie globale (par défaut à l’échelle de l’organisation) et les stratégies personnalisées que vous créez. Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Choisissez la stratégie à modifier, puis sélectionnez **Modifier**.

1. Apportez les modifications souhaitées.

1. Sélectionnez **Enregistrer**.

### <a name="assign-a-custom-app-setup-policy-to-users-and-groups"></a>Affecter une stratégie de configuration d’application personnalisée aux utilisateurs et aux groupes

Pour savoir comment attribuer des stratégies à vos utilisateurs finaux et à des groupes, découvrez [comment attribuer des stratégies à des utilisateurs et des groupes](assign-policies-users-and-groups.md).

## <a name="considerations-and-limitations"></a>Considérations et limitations

* Vous ne pouvez pas installer d’applications personnalisées avec des onglets configurables à l’aide de stratégies de configuration d’application.
* Les utilisateurs finaux ne peuvent pas désinstaller une application installée par un administrateur.
* Les applications épinglées via la stratégie d’installation d’application peuvent être désépinglées par l’utilisateur (si l’épinglage par l’utilisateur est autorisé dans la stratégie d’installation).
* Dans Teams pour l’Éducation, l’application Affectations est épinglée par défaut dans la stratégie globale, même si elle ne figure pas dans la stratégie globale.
* Le nombre maximal d’applications épinglées que vous pouvez ajouter à une stratégie n’est pas limité. Toutefois, au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android). Si une stratégie a moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continueront à utiliser la configuration existante.
* Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

## <a name="faqs"></a>Foire aux questions

### <a name="working-with-app-setup-policies"></a>Utilisation des stratégies de configuration d’application

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Je ne trouve pas d’application dans le volet « Ajouter des applications épinglées ».

Certaines applications ne peuvent pas être épinglées à Teams via une stratégie de configuration des applications. Cette fonctionnalité n’est pas prise en charge par toutes les applications. Pour rechercher les applications qui peuvent être épinglées, recherchez l’application dans le volet **Ajouter des applications épinglées**. Les onglets qui ont une étendue personnelle (onglets statiques) et des bots peuvent être épinglés au client de bureau Teams et ces applications sont disponibles dans le volet **Ajouter des applications épinglées**.

Rappelez-vous que le magasin d’applications Teams répertorie toutes les applications Teams. Le volet **Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées à Teams via une stratégie.

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Je suis un administrateur Teams pour l’Éducation. Que dois-je savoir sur les stratégies de configuration des applications dans Teams pour l’éducation ?

L’application Appel n’est pas disponible dans Teams pour l’éducation. Lorsque vous créez une stratégie de configuration pour une application personnalisée, l’application d’appel s’affiche dans la liste des applications. Toutefois, l’application n’est pas épinglée pour les clients Teams et les utilisateurs de Teams pour l’éducation ne verront pas l’application Appels dans Teams.

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans Teams ?

Pour afficher toutes les applications épinglées à un utilisateur, les utilisateurs peuvent être amenés à effectuer les opérations suivantes en fonction du nombre d’applications installées et de la taille de leur fenêtre cliente Teams.

|Client de bureau Teams |Client mobile Teams |
|---------|---------|
|Dans la barre de l’application sur le côté de Teams, sélectionnez **... Autres applications**.| Dans la barre de l’application près du bas de Teams, balayez vers le haut.|
|![Plus d’applications dans le client de bureau Teams.](media/app-setup-policies-desktop-more-apps.png)   |![plus d’applications dans le client mobile Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Qu’est-il nécessaire de savoir sur l’expérience mobile de Teams

Les clients mobiles Teams (iOS et Android) prennent en charge les applications personnelles avec des onglets statiques. Les applications épinglées au client de bureau Teams s’affichent dans les clients mobiles Teams. Les bots personnels s’affichent dans la conversation sur les clients mobiles.

Les applications tierces (qui peuvent être téléchargées à partir de Teams Store) doivent être approuvées avant qu’elles n’apparaissent sur les appareils mobiles. Si un administrateur épingle une application, qui n’est pas approuvée par Microsoft for Mobile, elle s’affiche sur le Bureau Teams, mais pas sur mobile. Pour plus d’informations, consultez [Clients mobiles](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients).

Avec les clients mobiles Teams, les utilisateurs voient les principales applications Teams telles que l’activité, la conversation et Teams, et vous pouvez épingler certaines des applications fournies par Microsoft.

#### <a name="order-of-apps-pinned-through-a-policy"></a>Ordre des applications épinglées via une stratégie

Les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur les clients mobiles et de bureau Teams si l’option **Épinglage par l’utilisateur** est activée. Les utilisateurs ne peuvent pas modifier l’ordre de leurs applications épinglées sur les clients web Teams.

#### <a name="does-user-pinning-take-precedence"></a>L’épinglage par l’utilisateur est-il prioritaire ?

Les épingles d’administration sont toujours prioritaires. Si **l’option d’épinglage utilisateur** est activée, les applications épinglées par les utilisateurs s’affichent sous les applications épinglées par les administrateurs. Si **l’option d’épinglage** d’utilisateur est désactivée, les utilisateurs perdent les broches existantes et seules les applications épinglées par les administrateurs sont disponibles dans la barre des applications.

### <a name="custom-teams-apps"></a>Applications Teams personnalisées

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mon organisation a créé une application Teams personnalisée et l’a publiée, soit dans AppSource, soit dans le catalogue d’applications client, mais l’icône de l’application ne s’affiche pas comme prévu lorsque l’application est épinglée à la barre de l’application dans Teams. Comment résoudre ce problème ?

Veillez à suivre les instructions relatives au logo avant d’envoyer l’application. Pour plus d’informations, consultez [Liste de vérification pour l’envoi de Mon tableau de bord vendeur](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).

## <a name="related-articles"></a>Articles connexes

* [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
* [Attribuer des stratégies aux utilisateurs finaux dans Teams](assign-policies-users-and-groups.md)
