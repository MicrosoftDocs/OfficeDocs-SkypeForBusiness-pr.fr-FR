---
title: Gérer les stratégies d’autorisation d’application dans Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez les stratégies d'autorisation des applications dans Microsoft Teams et comment contrôler la disponibilité des applications pour vos utilisateurs finaux.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 24c4b85bb1c4b97597bad6a38e6a67c35dc1abb0
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377042"
---
# <a name="manage-access-to-teams-apps-using-app-permission-policies"></a>Gérer l’accès aux applications Teams à l’aide de stratégies d’autorisation d’application

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler les applications disponibles pour chaque utilisateur de votre organisation. Les autorisations que vous définissez pour autoriser ou bloquer toutes les applications ou applications spécifiques s’appliquent à tous les [types d’applications dans Teams](deploy-apps-microsoft-teams-landing-page.md). Vous devez être administrateur de service Global Administration ou Teams pour gérer ces stratégies.

Pour autoriser une application, vous devez l’autoriser dans [les paramètres de l’application à l’échelle](manage-apps.md#manage-org-wide-app-settings) de [l’organisation, les paramètres de chaque application](manage-apps.md#allow-and-block-apps) et la stratégie d’autorisation de l’application. Bien que les deux autres méthodes autorisent simplement l’utilisation d’une application dans votre organisation, les stratégies d’autorisation vous permettent de contrôler quels utilisateurs peuvent utiliser une application spécifique. Vous contrôlez l’accès par utilisateur et par application en créant et en appliquant la stratégie à des utilisateurs spécifiques.

Le Centre d’administration Teams vous permet de créer deux types de stratégies d’autorisation :

* `Global (Org-wide default)` la stratégie existe par défaut et s’applique à tous les utilisateurs. Toutes les modifications apportées à cette stratégie ont un impact sur tous les utilisateurs, car cette stratégie est appliquée par défaut à tous les utilisateurs.
* Une stratégie créée par l’administrateur s’applique uniquement aux utilisateurs auxquels elle est appliquée. Créez une stratégie pour autoriser des applications pour des utilisateurs spécifiques ou un groupe d’utilisateurs.

   :::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Capture d’écran montrant une stratégie d’autorisation d’application en cours de création." lightbox="media/app-permission-policy.png":::

Si votre organisation est déjà sur Teams, les paramètres d’application que vous avez **configurés dans les paramètres à l’échelle du locataire** dans le Centre d'administration Microsoft 365 sont reflétés dans les paramètres d’application à l’échelle de l’organisation dans la page [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) du Centre d’administration Teams. Si vous débutez avec Teams et que vous commencez à peine, par défaut, toutes les applications sont autorisées dans le paramètre global à l’échelle de l’organisation. Il inclut les applications publiées par Microsoft, les fournisseurs de logiciels tiers et votre organisation.

> [!NOTE]
> Pour en savoir plus sur les paramètres des applications tierces dans l’environnement Cloud High (GCCH) de la communauté du secteur public Microsoft 365 et le département de la défense (DoD), consultez [Gérer les paramètres d’application à l’échelle de l’organisation pour Microsoft 365 Government](manage-apps.md#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-an-app-permission-policy"></a>Créer une stratégie d’autorisation d’application

Utilisez une ou plusieurs stratégies d'autorisation d'application personnalisées si vous souhaitez contrôler les applications disponibles pour différents groupes d'utilisateurs. Vous pouvez créer et attribuer des stratégies personnalisées distinctes sur la base de la publication d’applications par Microsoft, des tiers ou votre organisation. Après avoir créé une stratégie personnalisée, vous ne pouvez pas la modifier si les applications tierces sont désactivées dans les paramètres d'application à l'échelle de l'organisation.

1. Connectez-vous au Centre d’administration Teams et accédez aux stratégies **[d’autorisation](https://admin.teams.microsoft.com/policies/app-permission)** des **applications** >  Teams.
1. Sélectionnez **Ajouter**.
1. Fournissez un nom et une description pour la stratégie.
1. Sous **Applications Microsoft**, **Applications tierces** et **Applications personnalisées**, sélectionnez l’une des options suivantes :

    * `Allow all apps`
    * `Allow specific apps and block all others`
    * `Block specific apps and allow all others`
    * `Block all apps`

1. Si vous avez sélectionné **Autoriser des applications spécifiques et bloquer toutes les autres**, ajoutez les applications que vous souhaitez autoriser :

    1. Sélectionnez **Autoriser des applications**.
    1. Recherchez les applications que vous souhaitez autoriser, puis sélectionnez **Ajouter**. Les résultats de la recherche sont filtrés sur le développeur de l’application (**Applications Microsoft**, **Applications tierces** ou **Applications personnalisées**).
    1. Après avoir choisi une ou plusieurs applications, **sélectionnez Autoriser**.

1. Si vous avez sélectionné **Bloquer des applications spécifiques et autorisez toutes les autres** applications, recherchez et choisissez les applications que vous souhaitez bloquer, puis sélectionnez **Bloquer**.

1. Sélectionnez **Enregistrer**.

## <a name="edit-an-app-permission-policy"></a>Modifier une stratégie d’autorisation à l’application

Vous pouvez utiliser le Centre d’administration Teams pour modifier la stratégie globale ou les stratégies personnalisées que vous avez créées.

1. Connectez-vous au Centre d’administration Teams et accédez aux stratégies **[d’autorisation](https://admin.teams.microsoft.com/policies/app-permission)** des **applications** >  Teams.
1. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis sélectionnez **Modifier**.
1. Apportez les modifications nécessaires pour autoriser ou bloquer des applications spécifiques dans chacune des trois catégories.
1. Sélectionnez **Enregistrer**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Affecter une stratégie d’autorisation d’application personnalisée aux utilisateurs

Les stratégies d’autorisation d’application prennent effet uniquement lorsque vous appliquez une stratégie à un utilisateur ou à un groupe d’utilisateurs. Découvrez les différentes façons [d’affecter la stratégie aux utilisateurs](policy-assignment-overview.md#ways-to-assign-policies).

## <a name="considerations-when-using-app-permission-policies"></a>Considérations relatives à l’utilisation de stratégies d’autorisation d’application

Voici quelques considérations à prendre en compte lors de l’utilisation de stratégies d’autorisation d’application pour accorder l’accès ou interdire l’accès aux applications :

* Les stratégies d’autorisation d’application prennent effet uniquement lorsque vous appliquez une stratégie à un utilisateur ou à un groupe d’utilisateurs.

* Après avoir modifié ou attribué une stratégie, l’application des modifications peut prendre quelques heures.

* Un utilisateur final ne peut pas interagir avec les fonctionnalités d’une application que l’utilisateur n’est pas autorisé à utiliser.

* Les utilisateurs peuvent rechercher des applications bloquées et demander l’approbation de l’administrateur. Les administrateurs conservent le contrôle total pour [approuver ou ignorer les demandes des utilisateurs](user-requests-approve-apps.md).

* Les stratégies d’installation d’application fonctionnent avec les stratégies d’autorisation d’application. Vous sélectionnez les applications à épingler dans la stratégie d’installation à partir d’un ensemble d’applications autorisées. Toutefois, si un utilisateur a une stratégie d’autorisation d’application qui bloque l’utilisation d’une application épinglée, l’utilisateur ne peut pas utiliser l’application.

* Les stratégies d’application s’appliquent aux utilisateurs qui utilisent Teams sur le web, le mobile ou le bureau.

## <a name="related-articles"></a>Articles connexes

* [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
* [Attribuer des stratégies à vos utilisateurs](policy-assignment-overview.md)
* [Comparaison de la disponibilité des fonctionnalités Teams](/office365/servicedescriptions/teams-service-description#feature-availability)
