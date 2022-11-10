---
title: Vue d’ensemble des stratégies d’application pour gérer les applications dans Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/25/2022
search.appverid: ''
description: Découvrez les stratégies d’autorisation d’application et les stratégies de configuration utilisées pour gérer les applications dans Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 8e059199d4963004e287b456c98bb80717f849b3
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912433"
---
# <a name="know-about-policies-to-manage-access-and-installation-of-teams-apps"></a>Connaître les stratégies de gestion de l’accès et de l’installation des applications Teams

Microsoft Teams utilise des stratégies d’application pour régir le comportement d’accès et d’installation des applications. Les stratégies d’application aident les administrateurs Teams à contrôler le comportement d’application suivant :

* Configurez l’accès aux applications pour chaque utilisateur individuel ou pour un groupe d’utilisateurs. Il permet à l’administrateur de contrôler les applications autorisées pour chaque utilisateur final.

* Épinglez ces applications pour les utilisateurs finaux qui sont pertinentes pour les besoins de votre organisation. En outre, les administrateurs peuvent installer des applications pour les utilisateurs finaux sans intervention de l’utilisateur. Il aide les utilisateurs finaux à démarrer facilement avec les applications pertinentes.

* Contrôler les développeurs de votre organisation qui peuvent soumettre des applications personnalisées pour approbation par l’administrateur. Il vous permet de contrôler l’accès à la fonctionnalité de chargement d’applications personnalisées.

## <a name="app-permission-policies"></a>Stratégies d’autorisation d’application

Avec les stratégies d’autorisation d’application, l’administrateur Teams contrôle les applications disponibles pour chaque utilisateur de son organisation. Vous pouvez autoriser quelques applications pour tous les utilisateurs, vous pouvez autoriser quelques applications pour un groupe spécifique d’utilisateurs, ou vous pouvez autoriser des applications spécifiques pour des utilisateurs spécifiques. Les stratégies d’autorisation d’application fonctionnent en tandem avec les paramètres à l’échelle de l’organisation et autorisent ou bloquent l’état de chaque application individuelle.

Les stratégies d’autorisation d’application s’appliquent à tous les [types d’applications disponibles dans Teams](deploy-apps-microsoft-teams-landing-page.md). Voici quelques exemples de scénarios dans lesquels vous utilisez des stratégies d’autorisation d’application :

* Déployez progressivement une application pour certains utilisateurs initialement et pour tous les utilisateurs à terme.
* Autorisez une application personnalisée pour le recrutement et la gestion des talents uniquement pour les membres de votre service RH et bloquez-la pour tous les autres utilisateurs de l’organisation.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Capture d’écran de la stratégie d’autorisation d’application." lightbox="media/app-permission-policy.png":::

Pour plus d’informations, consultez [Comment gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Stratégies de configuration d’application

Les stratégies de configuration des applications vous permettent de configurer comment et où les applications sont disponibles pour les utilisateurs dans leur client Teams. Vous choisissez les applications que vous souhaitez épingler à la barre d’application dans les clients Teams et définissez l’ordre dans lequel les applications sont affichées.

L’épinglage ou l’installation d’applications permet de sensibiliser et d’adopter les applications souhaitées dans votre organisation. Les modifications s’appliquent aux clients Teams web, de bureau et mobiles.

Voici quelques exemples de scénarios dans lesquels vous utilisez des stratégies de configuration d’application :

* Épinglez une application personnalisée de recrutement et de gestion des talents pour les membres de votre équipe rh.
* Modifiez l’ordre des [applications principales](deploy-apps-microsoft-teams-landing-page.md#core-apps) à l’aide de l’épinglage pour les utilisateurs de votre organisation.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Capture d’écran de la stratégie de configuration d’application dans le Centre d’administration Teams." lightbox="media/app-setup-policy.png":::

Pour en savoir plus, consultez [Comment gérer les stratégies de configuration des applications](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Option de chargement d’applications personnalisées

Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques. Les développeurs au sein de votre organisation peuvent créer, tester et déployer des applications personnalisées pour les utilisateurs internes de Teams de l’organisation. Vous utilisez la stratégie de configuration des applications pour contrôler qui, au sein de votre organisation, peut charger des applications personnalisées. Vous utilisez des paramètres à l’échelle de l’organisation pour permettre aux utilisateurs finaux d’utiliser des applications personnalisées. Vous utilisez des stratégies d’autorisation pour autoriser uniquement des utilisateurs finaux spécifiques à utiliser une application personnalisée.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Capture d’écran montrant comment autoriser les applications personnalisées de votre organisation dans le panneau des paramètres à l’échelle de l’organisation." lightbox="media/custom-app-policy.png":::

Pour en savoir plus, consultez [comment gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Articles connexes

* [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
* [Gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md)
* [Gérer les stratégies de configuration des applications](teams-app-setup-policies.md)
* [Gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md)
