---
title: Gérer les applications Microsoft Power Platform dans le Centre d’administration Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Découvrez comment gérer l’accès aux applications personnalisées intégrées à la plateforme Microsoft Power dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: b44bd77a6415be9c9c9454fd96028fdbb8c608c4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831294"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gérer les applications Microsoft Power Platform dans le Centre d’administration Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Applications Microsoft Power Platform dans Teams

Cet article vous donne une vue d’ensemble de la gestion des applications [Microsoft Power Platform](https://powerplatform.microsoft.com/) dans le Centre d’administration Microsoft Teams.

> [!NOTE]
> Cet article s’applique aux applications personnalisées créées par les créateurs de votre organisation à l’aide de Power Apps ou d’agents virtuels Power. Ces applications personnalisées sont ajoutées automatiquement à Teams. Cet article ne s’applique pas à l’application Power Apps ou à l’application Agents virtuels Power qui sont installées à partir de la page Applications ou épinglées à Teams via une stratégie de configuration d’application. Vous gérez ces applications comme vous le feriez pour toute autre application sur la [page](manage-apps.md) Gérer les applications, à l’aide de stratégies d’autorisation d’application [et](teams-app-permission-policies.md)de stratégies [de configuration d’applications.](teams-app-setup-policies.md)

[Power Apps est](https://powerapps.microsoft.com) un environnement de développement d’application peu code/sans code que les créateurs de votre organisation peuvent utiliser pour créer des applications personnalisées qui se connectent à vos données professionnelles. [Les agents virtuels Power Virtual](https://docs.microsoft.com/power-virtual-agents/fundamentals-what-is-power-virtual-agents) sont un environnement de création de bots sans code qui permet aux créateurs de créer des robots puissants. Grâce à l’intégration des applications de la plateforme Microsoft Power Platform à Teams, les organisations peuvent rationaliser les processus d’entreprise, répondre aux besoins de l’entreprise plus rapidement afin d’optimiser la collaboration, et créer et partager des solutions personnalisées pour être plus productives.  

Les applications Microsoft Power Platform créées par les créateurs de votre organisation sont automatiquement ajoutées à Teams. Les créateurs peuvent contrôler les personnes qui peuvent accéder à leur application à l’aide de la fonctionnalité de partage dans [Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app) et de la fonctionnalité de partage dans Power [Virtual Agents.](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)

Lorsqu’une application Microsoft Power Platform est créée ou partagée, les utilisateurs peuvent l’afficher et l’installer sur la page Applications en allant à Built for Your Organization Name Built by your organization ***Built***  >  **by your colleagues**. (La création ou le partage d’une application peut prendre quelques minutes avant d’apparaître ici.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Captures d’écran de la page Applications, montrant les applications Microsoft Power Platform répertoriées dans La liste a été conçue par vos collègues":::

Un utilisateur verra une application intégrée par **vos collègues** si celle-ci répond à l’une des conditions suivantes.

|Power Apps |Agents virtuels de Power  |
|---------|---------|
|<ul><li>L’utilisateur a créé l’application.</li><li>L’application a été partagée directement avec l’utilisateur.</li><li>L’utilisateur a récemment utilisé l’application. </li></ul>| <ul><li>L’utilisateur a créé le robot.</li><li>Le robot appartient à une équipe dont l’utilisateur est membre. </li></ul>        |

Les utilisateurs installent les applications Microsoft Power Platform de la même façon qu’une autre application Teams. Gardez à l’esprit que les utilisateurs peuvent seulement installer des applications dans le contexte dans lequel ils ont des autorisations, par exemple, une équipe dont ils sont propriétaire, une conversation dont ils font partie ou l’étendue de leur vie personnelle.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gérer l’accès aux applications microsoft Power Platform dans le Centre d’administration Microsoft Teams

En tant qu’administrateur, vous pouvez déterminer si  les applications de la plateforme Microsoft Power Platform sont répertoriées dans La page Applications de Vos collègues dans Teams. Vous pouvez bloquer ou autoriser collectivement toutes les applications créées dans Power Apps ou toutes les applications créées dans les agents virtuels Power au niveau de l’organisation sur la [page](manage-apps.md) Gérer les applications ou pour des utilisateurs spécifiques utilisant des stratégies d’autorisation [d’application.](teams-app-permission-policies.md)

Les **applications Power Apps partagées** et Les applications De l’Agent virtuel power dans le magasin d’applications de votre organisation représentent toutes les applications créées sur cette plateforme spécifique.  Si vous bloquez l’une ou l’autre de ces applications au niveau de l’organisation ou pour des utilisateurs spécifiques, ces utilisateurs ne peuvent pas voir les applications de ces plateformes dans la plateforme intégrée par vos collègues et ne peuvent pas les installer dans Teams.   

Gardez à l’esprit que vous pouvez contrôler l’accès à toutes les applications créées dans Power Apps et les agents virtuels Power, mais que vous ne pouvez pas autoriser ou bloquer des applications individuelles. Les créateurs déterminent qui peut accéder aux applications qu’ils créent à l’aide de la fonctionnalité de partage à partir de Power Apps et des agents virtuels Power. Si un fabricant a partagé une application qu’il  a créée dans les agents virtuels Power avec un utilisateur et que vous avez bloqué les applications Agents virtuels power partagés pour cet utilisateur, l’utilisateur ne pourra pas voir ou installer d’applications à partir de cette plateforme dans Teams.

Si un utilisateur est autorisé à accéder à des applications à partir de Power Apps ou des agents virtuels Power, et que vous l’empêcherez ensuite d’accéder à des applications à partir d’une de ces plateformes ou des deux, l’utilisateur peut toujours accéder aux applications Microsoft Power Platforms qu’il a installées et les utiliser avant de bloquer l’application ou les applications. Toutefois, l’utilisateur ne peut plus voir ou installer d’applications à partir de ces plateformes dans la plateforme **intégrée par vos collègues.**

> [!NOTE]
> Le **paramètre autoriser l’interaction** avec les applications personnalisées à l’échelle de l’organisation sur la [page](manage-apps.md) Gérer les applications s’applique à tous les membres de votre organisation et décide s’ils peuvent interagir avec les applications personnalisées. Les paramètres d’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent toute autre stratégie d’autorisation d’application attribuée aux utilisateurs. Par défaut, ce paramètre est activé. Si ce paramètre est désactivé, les utilisateurs de votre organisation ne peuvent pas voir ou installer les applications personnalisées, y compris les applications de la plateforme Microsoft Power Platform. Pour plus d’informations, voir Gérer les paramètres des [applications à l’échelle de l’organisation.](manage-apps.md#manage-org-wide-app-settings)

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Autoriser ou bloquer les applications Microsoft Power Platform pour votre organisation

Par défaut, **les applications Power Apps partagées** et les applications De **l’agent** virtuel power sont autorisées pour tous les utilisateurs de Teams dans votre organisation. Vous pouvez les bloquer ou les autoriser au niveau de l’organisation sur la page [Gérer les](manage-apps.md) applications du Centre d’administration Microsoft Teams.  

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **l’application Teams** Gérer  >  **les applications.** Vous devez être un administrateur global ou un administrateur de service Teams pour accéder à la page.
2. Dans la liste des applications, faites l’une des choses suivantes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Capture d’écran de la page Gérer les applications, affichant les applications partagées de Microsoft Power Platform":::

    - Pour bloquer les applications créées dans Power Apps ou les agents virtuels Power pour tous les utilisateurs de votre organisation, recherchez Les applications **Power Apps** partagées ou les applications partagées de l’agent virtuel **Power,** sélectionnez-les, puis cliquez sur **Bloquer.**
    - Pour autoriser les applications créées dans Power Apps ou les agents virtuels Power pour tous les utilisateurs de votre organisation, recherchez Les applications **Power Apps** partagées ou Les applications partagées de l’agent virtuel **Power,** sélectionnez-les, puis cliquez sur **Autoriser.**

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Autoriser ou bloquer les applications Microsoft Power Platform pour des utilisateurs spécifiques

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’accéder à des applications créées dans Power Apps ou des agents virtuels Power, créez et affectez une ou plusieurs stratégies d’autorisation [d’application personnalisées.](teams-app-permission-policies.md) 

Par exemple, pour empêcher des utilisateurs spécifiques d’accéder aux applications créées dans Power Apps, créez une stratégie d’autorisation d’application personnalisée pour bloquer les applications **partagées Power Apps,** puis affectez la stratégie à ces utilisateurs.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Capture d’écran d’un exemple de stratégie d’autorisation d’application personnalisée avec Les applications Power Apps partagées bloquées":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform

Les journaux d’audit pour Teams vous permettent d’examiner les événements dans lequel des utilisateurs ont installé des applications Microsoft Power Platform à partir de la **section** Pré-créé par vos collègues de la page Applications dans Teams. Pour ce faire, recherchez dans le journal [d’audit](https://docs.microsoft.com/microsoftteams/audit-log-events) l’événement **Teams** de l’application installée (sous l’opération **AppInstalled)** d’un utilisateur ou d’un ensemble d’utilisateurs. Pour rechercher les applications installées à partir de **Built by your colleagues**(Prédél. par vos collègues), recherchez la valeur **TemplatedInstance** dans la propriété **AppDistributionMode** dans les détails d’un enregistrement donné. 

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Capture d’écran de la valeur TemplatedInstance dans la propriété AppDistributionMode":::

> [!NOTE]
> Vous pouvez exporter des enregistrements d’audit au format CSV pour simplifier le filtrage.

## <a name="related-topics"></a>Sujets associés

- [Partager une application de zone de dessin dans Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)
- [Partager votre robot avec d’autres utilisateurs](https://docs.microsoft.com/power-virtual-agents/admin-share-bots)
- [Gérer les applications dans le Centre d’administration Microsoft Teams](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Publier une application personnalisée envoyée via l’API De soumission d’application Teams](submit-approve-custom-apps.md)
