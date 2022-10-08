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
description: Découvrez les stratégies d’autorisation d’application et les stratégies d’installation utilisées pour gérer les applications dans Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1c99cd9c0be3251a237b547cd8a2096d2d0e02af
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494647"
---
# <a name="app-policies-used-to-manage-access-to-and-installation-of-apps"></a>Stratégies d’application utilisées pour gérer l’accès aux applications et leur installation

Microsoft Teams utilise des stratégies d’application pour régir le comportement d’accès et d’installation des applications. Les stratégies d’application aident les administrateurs Teams à contrôler le comportement d’application suivant :

* Configurez l’accès aux applications pour chaque utilisateur individuel ou pour un groupe d’utilisateurs. Il permet à l’administrateur de contrôler les applications autorisées pour chaque utilisateur final.

* Épinglez les applications pour les utilisateurs finaux qui sont pertinentes pour les besoins de votre organisation. En outre, les administrateurs peuvent installer des applications pour les utilisateurs finaux sans intervention de l’utilisateur. Il permet aux utilisateurs finaux de bien démarrer avec les applications pertinentes.

* Contrôlez les développeurs de votre organisation qui peuvent envoyer des applications personnalisées pour approbation administrateur. Il vous aide à contrôler l’accès aux fonctionnalités de chargement d’applications personnalisées.

## <a name="app-permission-policies"></a>Stratégies d’autorisation d’application

Avec les stratégies d’autorisation d’application, l’administrateur Teams contrôle les applications disponibles pour chaque utilisateur de son organisation. Vous pouvez autoriser quelques applications pour tous les utilisateurs, vous pouvez autoriser quelques applications pour un groupe spécifique d’utilisateurs, ou vous pouvez autoriser des applications spécifiques pour des utilisateurs spécifiques. Les stratégies d’autorisation d’application fonctionnent en tandem avec les paramètres à l’échelle de l’organisation et autorisent ou bloquent l’état de chaque application individuelle.

Les stratégies d’autorisation d’application s’appliquent à tous les [types d’applications disponibles dans Teams](deploy-apps-microsoft-teams-landing-page.md). Voici quelques exemples de scénarios dans lesquels vous utilisez des stratégies d’autorisation d’application :

* Déployer progressivement une application pour certains utilisateurs au départ et pour tous les utilisateurs par la suite.
* Autorisez une application personnalisée de recrutement et de gestion des talents uniquement pour les membres de votre service RH et bloquez-la pour tous les autres utilisateurs de l’organisation.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Capture d’écran de la stratégie d’autorisation d’application." lightbox="media/app-permission-policy.png":::

Pour en savoir plus, découvrez [comment gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Stratégies de configuration d’application

Les stratégies d’installation des applications vous permettent de configurer comment et où les applications sont disponibles pour les utilisateurs dans leur client Teams. Vous choisissez les applications que vous souhaitez épingler à la barre des applications dans les clients Teams et définissez l’ordre dans lequel les applications sont affichées.

L’épinglage ou l’installation d’applications permet de sensibiliser et d’adopter les applications souhaitées dans votre organisation. Les modifications s’appliquent aux clients Web, De bureau et Teams mobiles.

Voici quelques exemples de scénarios dans lesquels vous utilisez des stratégies d’installation d’application :

* Épinglez une application personnalisée de recrutement et de gestion des talents pour les membres de votre équipe RH.
* Modifiez l’ordre des applications principales pré-épinglées pour les utilisateurs de votre organisation.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Capture d’écran de la stratégie de configuration d’application dans le Centre d’administration Teams." lightbox="media/app-setup-policy.png":::

Pour en savoir plus, consultez [Comment gérer les stratégies de configuration des applications](teams-app-setup-policies.md).

### <a name="option-to-upload-custom-apps"></a>Option de chargement d’applications personnalisées

Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques. Les développeurs de votre organisation peuvent créer, tester et déployer des applications personnalisées pour les utilisateurs internes de Teams de l’organisation. Vous utilisez la stratégie d’installation d’application pour contrôler qui dans votre organisation peut charger des applications personnalisées. Vous utilisez des paramètres à l’échelle de l’organisation pour permettre aux utilisateurs finaux d’utiliser des applications personnalisées. Vous utilisez des stratégies d’autorisation pour autoriser uniquement des utilisateurs finaux spécifiques à utiliser une application personnalisée.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Capture d’écran montrant comment autoriser les applications personnalisées de votre organisation dans le panneau des paramètres à l’échelle de l’organisation." lightbox="media/custom-app-policy.png":::

Pour en savoir plus, découvrez [comment gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Articles connexes

* [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
* [Gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md)
* [Gérer les stratégies de configuration des applications](teams-app-setup-policies.md)
* [Gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md)
