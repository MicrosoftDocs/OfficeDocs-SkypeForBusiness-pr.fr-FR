---
title: Gérer les applications Microsoft Power Platform dans le centre d’administration Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: joglocke
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer l’accès aux applications personnalisées créées sur Microsoft Power Platform dans le centre d’administration Microsoft Teams.
ms.openlocfilehash: 5675083c3a7b0aaea2fb053609cbf7da800dbe42
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753569"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gérer les applications Microsoft Power Platform dans le centre d’administration Microsoft teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Applications Microsoft Power Platform dans teams

Cet article vous fournit une vue d’ensemble de la gestion des applications [Microsoft Power Platform](https://powerplatform.microsoft.com/) dans le centre d’administration Microsoft Teams.

> [!NOTE]
> Cet article s’applique aux applications personnalisées créées par les détenteurs de votre organisation à l’aide d’applications Power ou d’agents d’alimentation virtuelles. Ces applications personnalisées sont automatiquement ajoutées à Teams. Cet article ne s’applique pas à l’application Power Apps ou à l’application agents virtuels d’alimentation installés à partir de la page d’applications ou épinglée à teams via une stratégie de configuration d’application. Vous pouvez gérer ces applications comme vous le feriez pour n’importe quelle autre application sur la page [gérer les applications](manage-apps.md) , à l’aide de stratégies d' [autorisation d’application](teams-app-permission-policies.md)et de stratégies de [Configuration des applications](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) est un environnement de développement d’applications à faible code/sans code, qui permet aux développeurs de votre organisation de créer des applications personnalisées qui se connectent à vos données métiers. Les [agents d’alimentation virtuelle](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) n’ont pas de code de bâtiment de robot pour créer des robots puissants. Grâce à l’intégration des applications de plateforme de production Microsoft à Teams, les organisations peuvent rationaliser les processus d’entreprise, répondre aux besoins fluctuants de l’entreprise plus rapidement pour renforcer la collaboration et créer et partager des solutions personnalisées pour être plus productif.  

Les applications Microsoft Power Platform créées par les marqueurs de votre organisation sont automatiquement ajoutées à Teams. Les décideurs peuvent contrôler les personnes autorisées à accéder à leur application à l’aide de la [fonctionnalité de partage dans Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) et de la [fonctionnalité de partage dans les agents d’alimentation virtuelles](https://docs.microsoft.com/power-virtual-agents/admin-share-bots).

Lors de la création ou du partage d’une application Microsoft Power Platform, les utilisateurs peuvent l’afficher et l’installer sur la page applications en accédant à la page applications **pour le *nom*** de  >  **votre organisation créée par vos collègues**. (Il peut s’écouler quelques minutes après la création ou le partage d’une application pour l’application.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Capture d’écran de la page applications affichant les applications Microsoft Power Platform répertoriées dans la liste des collègues":::

Un utilisateur verra une application **créée par vos collègues** si l’application satisfait l’une des conditions suivantes.

|Applications Power |Agent virtuel d’alimentation  |
|---------|---------|
|<ul><li>L’utilisateur a créé l’application.</li><li>L’application a été partagée directement par l’utilisateur.</li><li>L’utilisateur a récemment utilisé l’application. </li></ul>| <ul><li>L’utilisateur a créé le bot.</li><li>Le bot appartient à une équipe dont l’utilisateur est membre. </li></ul>        |

Les utilisateurs installent les applications Microsoft Power Platform de la même manière que pour les autres applications Teams. Gardez à l’esprit que les utilisateurs ne peuvent installer que le contexte pour lesquels ils disposent d’autorisations, par exemple une équipe, une discussion dont ils sont membres ou leur cadre personnel.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gestion de l’accès aux applications Microsoft Power Platform dans le centre d’administration Microsoft teams

En tant qu’administrateur, vous pouvez contrôler si les applications de la plateforme énergétique Microsoft sont répertoriées **par vos collègues** dans la page applications dans Microsoft Teams. Vous pouvez bloquer ou accepter collectivement toutes les applications créées dans Power applications ou toutes les applications créées dans les agents d’alimentation virtuelles au niveau de l’organisation sur la page [gérer les applications](manage-apps.md) ou pour des utilisateurs spécifiques utilisant des stratégies d' [autorisation d’application](teams-app-permission-policies.md).

Les applications **d’alimentation partagées** et les applications d' **agent virtuel d’alimentation partagées** dans le magasin d’applications de votre organisation représentent toutes les applications créées sur cette plateforme particulière. Si vous bloquez une de ces applications ou les deux au niveau de l’organisation ou pour des utilisateurs spécifiques, ces utilisateurs ne peuvent pas voir les applications provenant de ces plates-formes **intégrées par vos collègues** et ne peuvent pas les installer dans Teams.  

Gardez à l’esprit que vous pouvez contrôler l’accès à toutes les applications créées dans Power Apps et aux agents d’alimentation virtuelles, mais vous ne pouvez pas autoriser ou bloquer des applications individuelles. Les décideurs décident qui peut accéder aux applications qu’ils créent par le biais de la fonctionnalité de partage à partir de Power Apps et d’agents virtuels d’alimentation. Si un fabricant a partagé une application qu’il a créée dans les agents d’alimentation virtuelle et que vous avez bloqué les **applications d’agent virtuel d’alimentation partagées** pour cet utilisateur, l’utilisateur ne pourra pas voir ou installer d’applications de cette plateforme dans Teams.

Si un utilisateur est autorisé à accéder aux applications à partir d’applications Power ou d’agents virtuels d’alimentation, et si vous n’avez pas l’autorisation d’accéder à des applications à partir de l’une ou de l’autre, l’utilisateur peut toujours accéder aux applications de plateformes Microsoft qu’elles ont installées avant de bloquer l’application ou les applications. Toutefois, l’utilisateur ne peut plus voir ou installer des applications à partir de ces plates-formes **intégrées par vos collègues**.

> [!NOTE]
> Le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation sur la page [gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent interagir avec les applications personnalisées. Les paramètres de l’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent toutes les autres stratégies d’autorisation d’application attribuées aux utilisateurs. Par défaut, ce paramètre est activé. Si cette option est désactivée, les utilisateurs de votre organisation ne peuvent pas voir ou installer des applications personnalisées, notamment les applications Microsoft Power Platform. Pour en savoir plus, voir [gérer les paramètres de l’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Autoriser ou bloquer des applications Microsoft Power Platform pour votre organisation

Par défaut, les applications **d’alimentation partagées** et les **applications d’agent virtuel d’alimentation partagées** sont autorisées pour tous les utilisateurs d’équipes de votre organisation. Vous pouvez bloquer ou autoriser les utilisateurs au niveau de l’organisation dans la page [gérer les applications](manage-apps.md) du centre d’administration Microsoft Teams.  

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps. Pour accéder à la page, vous devez être administrateur général ou administrateur de service Teams.
2. Dans la liste des applications, effectuez l’une des opérations suivantes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Capture d’écran de la page gérer les applications, montrant les applications Microsoft Power Platform partagées":::

    - Pour bloquer les applications créées dans les applications Power ou les agents d’alimentation virtuelles pour tous les utilisateurs de votre organisation, recherchez des applications **d’alimentation partagées** ou des **applications d’agent virtuel d’alimentation partagées**, sélectionnez-les, puis cliquez sur **bloquer**.
    - Pour permettre à tous les utilisateurs de votre organisation de créer des applications d’alimentation ou des agents d’alimentation, recherchez des applications **d’alimentation partagées** ou des **applications d’agent virtuel d’alimentation partagées**, sélectionnez-les, puis cliquez sur **autoriser**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Autoriser ou bloquer des applications Microsoft Power Platform pour des utilisateurs spécifiques

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’accéder à des applications créées dans des applications d’alimentation ou des agents virtuels d’alimentation, créez et attribuez une ou plusieurs [stratégies d’autorisation d’application](teams-app-permission-policies.md)personnalisées. 

Par exemple, pour empêcher des utilisateurs spécifiques d’accéder à des applications créées dans des applications d’alimentation, créez une stratégie d’autorisations d’application personnalisée pour bloquer les **applications d’alimentation partagées**, puis affectez la stratégie à ces utilisateurs.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Capture d’écran d’un exemple de stratégie d’autorisation d’application personnalisée avec les applications d’alimentation partagées bloquées":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform

Vous pouvez utiliser les journaux d’audit pour les équipes pour examiner les événements dans lesquels les utilisateurs ont installé les applications Microsoft Power Platform à partir de la section **bâti par vos collègues** de la page applications dans Microsoft Teams. Pour cela, effectuez une [recherche dans le journal d’audit](https://docs.microsoft.com/microsoftteams/audit-log-events) pour l’événement teams de l' **application installé** (sous l’opération **AppInstalled** ) pour un utilisateur ou un ensemble d’utilisateurs. Pour rechercher des applications installées **par vos collègues**, recherchez la valeur **TemplatedInstance** dans la propriété **AppDistributionMode** dans les détails d’un enregistrement donné. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Capture d’écran de la valeur TemplatedInstance dans la propriété AppDistributionMode":::

> [!NOTE]
> Vous pouvez exporter des enregistrements d’audit au format CSV pour faciliter le filtrage.

## <a name="related-topics"></a>Sujets associés

- [Partager une application de zone de dessin dans les applications Power](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Partager votre bot avec d’autres utilisateurs](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gérer les applications dans le centre d’administration Microsoft teams](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Publier une application personnalisée soumise par le biais de l’API de soumission d’applications teams](submit-approve-custom-apps.md)
