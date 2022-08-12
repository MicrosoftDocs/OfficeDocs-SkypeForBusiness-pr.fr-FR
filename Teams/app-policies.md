---
title: Vue d’ensemble des stratégies d’application pour gérer les applications dans Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
search.appverid: ''
description: Découvrez les stratégies d’autorisation d’application, les stratégies de configuration des applications et les stratégies d’application personnalisées utilisées pour gérer les applications dans Microsoft Teams.
audience: admin
ms.localizationpriority: high
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 5a377923412ad1835e4a0a3c099d31adf283267b
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299033"
---
# <a name="overview-of-app-policies-used-to-manage-access-to-apps"></a>Vue d’ensemble des stratégies d’application utilisées pour gérer l’accès aux applications

Microsoft Teams utilise des stratégies pour régir le comportement d’accès et d’installation. Les stratégies aident les administrateurs Teams à contrôler le comportement d’application suivant :

* Configurez l’accès aux applications pour les utilisateurs à un niveau détaillé. Il permet à chaque utilisateur final d’utiliser uniquement les applications qu’un administrateur a autorisées pour lui.

* Épinglez les applications appropriées à un utilisateur spécifique. Cela offre une prise en main facile de l’utilisateur final qui peut accéder rapidement aux applications pertinentes, car les applications épinglées s’installent automatiquement sans intervention.

## <a name="app-permission-policies"></a>Stratégies d’autorisation d’application

Avec les stratégies d’autorisation d’application, l’administrateur Teams peut contrôler les applications disponibles pour les utilisateurs spécifiques de leur organisation. Vous pouvez définir un mappage d’accès exact entre l’application et l’utilisateur, ou n’importe quelle combinaison des deux. Par exemple, vous pouvez autoriser quelques applications pour tous les utilisateurs, pour un groupe spécifique d’utilisateurs ou autoriser une application spécifique pour un utilisateur spécifique.

Les stratégies d’autorisation d’application s’appliquent à tous les types d’applications disponibles dans Teams. Par exemple, vous pouvez utiliser des stratégies d’autorisation d’application pour déployer progressivement une application tierce ou une application personnalisée, en l’autorisant pour des utilisateurs spécifiques.

:::image type="content" source="media/app-permission-policy-trimmed.png" alt-text="Capture d’écran de la stratégie d’autorisation d’application." lightbox="media/app-permission-policy.png":::

Pour en savoir plus, consultez [Comment gérer les paramètres et les stratégies d’application personnalisés](teams-app-permission-policies.md).

## <a name="app-setup-policies"></a>Stratégies de configuration d’application

Les stratégies d’installation d’applications vous permettent de personnaliser l’expérience d’application pour vos utilisateurs. Choisissez les applications que vous souhaitez épingler à la barre d'applications dans les clients Teams, ainsi que l'ordre dans lequel elles apparaissent, sur les clients Web, bureau et mobiles.

Voici quelques exemples de la façon dont vous pouvez utiliser des stratégies de configuration d’application :

* Installez des applications pour les utilisateurs finaux dans leur environnement Teams personnel. Cela permet de favoriser la sensibilisation et l’adoption des applications souhaitées. Par exemple, épinglez une application personnalisée de recrutement et de gestion des talents aux membres de votre équipe RH.
* Épinglez de manière sélective les applications principales, telles que Conversation, Teams et Appel.

:::image type="content" source="media/app-setup-policy-trimmed.png" alt-text="Capture d’écran de la stratégie de configuration d’application dans le Centre d’administration Teams." lightbox="media/app-setup-policy.png":::

Pour en savoir plus, consultez [Comment gérer les stratégies de configuration des applications](teams-app-setup-policies.md).

## <a name="custom-app-policies"></a>Stratégies d’application personnalisées

Teams permet aux développeurs au sein de votre organisation de créer, tester et déployer des applications personnalisées pour les utilisateurs internes de l’organisation. Les développeurs peuvent soumettre leurs applications personnalisées via Teams pour approbation auprès des administrateurs Teams. Vous pouvez utiliser des stratégies de configuration d’application pour contrôler qui dans votre organisation peut charger des applications personnalisées. Les administrateurs peuvent autoriser les utilisateurs finaux de leur organisation à utiliser des applications personnalisées et des développeurs pour charger des applications personnalisées, à l’aide des paramètres d’application à l’échelle de l’organisation.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Capture d’écran montrant comment autoriser les applications personnalisées de votre organisation dans le panneau des paramètres à l’échelle de l’organisation." lightbox="media/custom-app-policy.png":::

Pour en savoir plus, consultez [Comment gérer les paramètres et les stratégies d’application personnalisés](teams-custom-app-policies-and-settings.md).

## <a name="related-articles"></a>Articles connexes

* [Gérer Teams avec des stratégies](manage-teams-with-policies.md)
