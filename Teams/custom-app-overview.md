---
title: Gérer les applications personnalisées et chargées de manière indépendante
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/25/2022
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
ms.openlocfilehash: 42c970f3b354ac1f5b490359f0df9bcc01e97019
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494767"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>Comprendre et gérer des applications personnalisées et chargées de manière indépendante

Microsoft Teams permet aux développeurs de votre organisation de créer, tester et déployer des applications personnalisées pour les utilisateurs internes de l’organisation. Ces applications sont appelées applications personnalisées ou applications métier. Votre organisation peut commander la création d'applications personnalisées pour répondre à des besoins spécifiques. Les administrateurs contrôlent le déploiement et les autorisations pour les applications personnalisées à l’aide de différents paramètres et stratégies.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Capture d’écran montrant comment autoriser les applications personnalisées de votre organisation dans le panneau des paramètres à l’échelle de l’organisation." lightbox="media/custom-app-orgwide-setting.png":::

Une fois que vous avez autorisé l’utilisation d’une application personnalisée, vos utilisateurs finaux peuvent la trouver en sélectionnant **Built pour votre organisation** dans le volet de navigation gauche du magasin Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Capture d’écran des applications personnalisées dans le magasin Teams dans l’application de bureau teams." lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>Comprendre le chargement indépendant des applications personnalisées

Lors du développement d’applications personnalisées et avant de les distribuer aux utilisateurs finaux, les développeurs testent les applications en les ajoutant à Teams Store pour les tester. Les développeurs peuvent effectuer des tests seuls ou avec un groupe d’utilisateurs spécifié, mais l’application n’est pas disponible pour les autres utilisateurs finaux de l’organisation via le Store. Cette méthode est appelée chargement indépendant des applications et s’applique uniquement aux applications personnalisées.

Les développeurs peuvent recourir au chargement indépendant d’une application pour la mettre à la disposition des membres d’une équipe spécifique, généralement pour tester une application en cours de développement. De cette manière, seuls les développeurs de l’application peuvent l’utiliser sans nécessiter l’autorisation de l’administrateur, à condition que ce dernier autorise le chargement indépendant dans Teams.

Les développeurs peuvent partager une application chargée de manière indépendante avec une équipe spécifique sans la soumettre au catalogue d’applications Teams. Il rend l’application personnalisée chargée de manière indépendante à la disposition d’un groupe limité d’utilisateurs finaux, mais pas dans l’App Store de votre organisation pour tous les utilisateurs finaux.

En tant qu’administrateur, vous pouvez interdire le chargement indépendant de l’application pour tous les développeurs. Si vous interdisez le chargement indépendant, les développeurs peuvent toujours tester leurs applications en [créant un client de test distinct](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Une fois le développement d’applications personnalisées terminé, les développeurs demandent aux administrateurs de distribuer leur application personnalisée aux utilisateurs finaux. Pour plus d’informations, consultez [comment publier une application personnalisée](/microsoftteams/upload-custom-apps). En tant qu’administrateur, vous autorisez (ou bloquez) l’utilisation d’une application personnalisée pour tous les utilisateurs ou pour des utilisateurs spécifiques.

## <a name="allow-developers-to-upload-custom-apps"></a>Autoriser les développeurs à charger des applications personnalisées

Dans la stratégie d’installation d’application, vous pouvez créer une stratégie personnalisée ou modifier la stratégie globale pour autoriser le chargement d’applications personnalisées. Pour créer une stratégie personnalisée et l’appliquer à des utilisateurs spécifiques, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez à **Applications Teams** > **[Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup)**.
1. Sélectionnez **Ajouter**.
1. Fournissez un nom et une description pour la stratégie.
1. Activez ou désactivez **Charger des applications personnalisées**.
1. [Appliquez la stratégie aux utilisateurs](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) qui développent des applications personnalisées et sont autorisés à charger ces applications.

> [!NOTE]
> Pour modifier ce paramètre, autorisez les applications [personnalisées dans les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

## <a name="related-articles"></a>Articles connexes

* [Gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md)
* [Comprendre les stratégies pour régir les applications](app-policies.md)
* [Comprendre les applications tierces](overview-third-party-apps.md)
