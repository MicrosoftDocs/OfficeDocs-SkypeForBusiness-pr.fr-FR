---
title: Gérer les applications personnalisées et chargées de manière indépendante
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
description: Comprendre les applications personnalisées et les applications chargées de manière indépendante dans Microsoft Teams et gérer les applications pour régir leur comportement, leur déploiement et leurs autorisations.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d7c23b424db102b21e88944e2ab55d8a2fe98c08
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299296"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprendre et gérer des applications personnalisées et chargées de manière indépendante

Microsoft Teams permet aux développeurs de votre organisation de créer, tester et déployer des applications personnalisées pour les utilisateurs internes de l’organisation. Ces applications sont appelées applications personnalisées ou applications métier. Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques.

En tant qu’administrateur, vous avez le contrôle d’autoriser ou de bloquer ces applications pour l’ensemble de l’organisation ou pour des utilisateurs spécifiques. Les développeurs de votre organisation peuvent créer des solutions personnalisées à faible code en utilisant l'intégration de Teams avec [Microsoft Power Plateforme](/microsoftteams/platform/samples/teams-low-code-solutions).

Les développeurs peuvent soumettre leurs applications personnalisées via Teams pour approbation de la part de l’administrateur. Vous pouvez utiliser des stratégies d’installation d’application pour contrôler le déploiement, la distribution et les autorisations des applications personnalisées.

:::image type="content" source="media/custom-app-policy-trimmed.png" alt-text="Capture d’écran montrant comment autoriser des applications personnalisées dans votre organisation dans le panneau paramètres à l’échelle de l’organisation." lightbox="media/custom-app-policy.png":::

Une fois que vous avez autorisé l’utilisation d’une application personnalisée, vos utilisateurs finaux peuvent la trouver en sélectionnant **Built pour votre organisation** dans le volet de navigation gauche du magasin Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Capture d’écran des applications personnalisées dans le magasin Teams dans l’application de bureau teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Comprendre le chargement indépendant des applications personnalisées

Lors du développement d’applications personnalisées et avant de les distribuer aux utilisateurs finaux, les développeurs testent les applications en les ajoutant à Teams Store pour les tester. Les développeurs peuvent effectuer des tests seuls ou avec un groupe d’utilisateurs spécifié, mais l’application n’est pas disponible pour les autres utilisateurs finaux de l’organisation via le Windows Store. Cette méthode est appelée chargement indépendant des applications et s’applique uniquement aux applications personnalisées.

Les développeurs peuvent recourir au chargement indépendant d’une application pour la mettre à la disposition des membres d’une équipe spécifique, généralement pour tester une application en cours de développement. De cette manière, seuls les développeurs de l’application peuvent l’utiliser sans nécessiter l’autorisation de l’administrateur, à condition que ce dernier autorise le chargement indépendant dans Teams.

Les développeurs peuvent partager une application chargée de manière indépendante avec une équipe spécifique sans la soumettre au catalogue d’applications Teams. Il rend l’application personnalisée chargée de manière indépendante à la disposition d’un groupe limité d’utilisateurs finaux, mais pas dans l’App Store de votre organisation pour tous les utilisateurs finaux.

En tant qu’administrateur, vous pouvez interdire le chargement indépendant de l’application pour tous les développeurs. Si vous interdisez le chargement indépendant, les développeurs peuvent toujours tester leurs applications en [créant un client de test distinct](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Une fois le développement d’applications personnalisées terminé, les développeurs demandent aux administrateurs de distribuer leur application personnalisée aux utilisateurs finaux. Pour plus d’informations, consultez [comment publier une application personnalisée](/microsoftteams/upload-custom-apps). En tant qu’administrateur, vous pouvez autoriser ou interdire l’utilisation d’une application personnalisée pour des utilisateurs spécifiques.

## <a name="allow-developers-to-upload-custom-apps"></a>Autoriser les développeurs à charger des applications personnalisées

Vous pouvez créer une stratégie personnalisée ou modifier la stratégie globale pour autoriser ou bloquer des applications personnalisées en fonction des besoins de votre organisation. Pour créer une stratégie personnalisée qui permet aux développeurs de l’organisation de charger des applications personnalisées, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux stratégies **[d’installation](https://admin.teams.microsoft.com/policies/app-setup)** des **applications** >  Teams.

1. Sélectionnez **Ajouter**.

1. Fournissez un nom et une description pour la stratégie.

1. Activez ou **désactivez Charger des applications personnalisées**.

> [!NOTE]
> Pour modifier ce paramètre, autorisez les applications [tierces dans les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings) de votre locataire.

## <a name="related-articles"></a>Articles connexes

* [Gérer les stratégies et paramètres d’application personnalisés](teams-custom-app-policies-and-settings.md)
* [Comprendre les stratégies pour régir les applications](app-policies.md)
* [Comprendre les applications tierces](overview-third-party-apps.md)
