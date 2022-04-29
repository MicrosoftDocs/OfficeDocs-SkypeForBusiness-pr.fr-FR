---
title: Gérer les applications Microsoft Power Platform dans le centre d’administration Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer l’accès aux applications personnalisées basées sur Microsoft Power Platform dans le centre d’administration Microsoft Teams.
ms.openlocfilehash: 9f212cf52ec757fc4860f081fb67da2cb1b4fcd5
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65136995"
---
# <a name="manage-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gérer les applications Microsoft Power Platform dans le centre d’administration Microsoft Teams

## <a name="microsoft-power-platform-apps-in-teams"></a>Applications Microsoft Power Platform dans Teams

Cet article vous donne une vue d’ensemble de la gestion des applications [Microsoft Power Platform](https://powerplatform.microsoft.com/) dans le centre d’administration Microsoft Teams.

> [!NOTE]
> Cet article s’applique aux applications personnalisées créées par les créateurs de votre organisation à l’aide de Power Apps ou Power Virtual Agents. Ces applications personnalisées sont automatiquement ajoutées à Teams. Cet article ne s’applique pas à l’application Power Apps ou Power Virtual Agents application installée à partir de la page Applications ou épinglée à Teams via une stratégie d’installation d’application. Vous gérez ces applications comme vous le feriez pour n’importe quelle autre application dans la page [Gérer les applications](manage-apps.md) , à l’aide de [stratégies d’autorisation d’application](teams-app-permission-policies.md) et de [stratégies d’installation d’application](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) est un environnement de développement d’applications à faible code/sans code que les créateurs de votre organisation peuvent utiliser pour créer des applications personnalisées qui se connectent à vos données métier. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) est un environnement de création de bot sans code permettant aux créateurs de créer des bots puissants. Avec l’intégration d’applications Microsoft Power Platform à Teams, les organisations peuvent simplifier les processus métier, répondre plus rapidement aux besoins changeants de l’entreprise pour favoriser une meilleure collaboration et créer et partager des solutions personnalisées pour être plus productives.  

Les applications Microsoft Power Platform créées par les créateurs de votre organisation sont automatiquement ajoutées à Teams. Les créateurs peuvent contrôler qui peut accéder à leur application à l’aide de la [fonctionnalité de partage dans Power Apps](/powerapps/maker/canvas-apps/share-app) et de la [fonctionnalité de partage dans Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Lorsqu’une application Microsoft Power Platform est créée ou partagée, les utilisateurs peuvent l’afficher et l’installer sur la page Applications en accédant à **Built for *Your Organization NameBuilt*** >  **par vos collègues**. (L’affichage de l’application ici peut prendre quelques minutes après la création ou le partage d’une application.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Captures d’écran de la page Applications, montrant les applications Microsoft Power Platform répertoriées dans Built by vos collègues":::

Un utilisateur voit une application dans **Built by vos collègues** si l’application remplit l’une des conditions suivantes.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>L’utilisateur a créé l’application.</li><li>L’application a été partagée directement avec l’utilisateur.</li><li>L’utilisateur a récemment utilisé l’application. </li></ul>| <ul><li>L’utilisateur a créé le bot.</li><li>Le bot appartient à une équipe dont l’utilisateur est membre. </li></ul>        |

Les utilisateurs installent les applications Microsoft Power Platform de la même façon qu’ils installent n’importe quelle autre application Teams. Gardez à l’esprit que les utilisateurs peuvent uniquement installer des applications dans le contexte dans lequel ils disposent d’autorisations, par exemple, une équipe dont ils sont propriétaires, une conversation dont ils font partie ou leur étendue personnelle.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-microsoft-teams-admin-center"></a>Gérer l’accès aux applications Microsoft Power Platform dans le centre d’administration Microsoft Teams

En tant qu’administrateur, vous pouvez contrôler si les applications Microsoft Power Platform sont répertoriées dans **Built by your colleagues** on the Apps page in Teams. Vous pouvez bloquer ou autoriser collectivement toutes les applications créées dans Power Apps ou toutes les applications créées dans Power Virtual Agents au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) ou pour des utilisateurs spécifiques à l’aide de [stratégies d’autorisation d’application](teams-app-permission-policies.md).

Les applications **Shared Power Apps** et **Shared Power Virtual Agent Apps** dans l’App Store de votre organisation représentent toutes les applications créées sur cette plateforme particulière. Si vous bloquez une ou les deux applications au niveau de l’organisation ou pour des utilisateurs spécifiques, ces utilisateurs ne peuvent pas voir les applications de ces plateformes dans **Built by vos collègues** et ne peuvent pas les installer dans Teams.  

Gardez à l’esprit que vous pouvez contrôler l’accès à toutes les applications créées dans Power Apps et Power Virtual Agents, mais que vous ne pouvez pas autoriser ou bloquer des applications individuelles. Les créateurs décident qui peut accéder aux applications qu’ils créent via la fonctionnalité de partage à partir de Power Apps et de Power Virtual Agents. Si un créateur a partagé une application qu’il a créée dans Power Virtual Agents avec un utilisateur et que vous avez bloqué **shared Power Virtual Agents Apps** pour cet utilisateur, l’utilisateur ne pourra pas voir ni installer d’applications à partir de cette plateforme dans Teams.

Si un utilisateur est autorisé à accéder aux applications à partir de Power Apps ou Power Virtual Agents, et que vous empêchez ensuite l’utilisateur d’accéder aux applications à partir d’une ou des deux plateformes, l’utilisateur peut toujours accéder aux applications Microsoft Power Platforms qu’il a installées et l’utiliser avant de bloquer l’application ou les applications. Toutefois, l’utilisateur ne peut plus voir ni installer d’applications à partir de ces plateformes dans **Built by vos collègues**.

> [!NOTE]
> Le paramètre **Autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation dans la page [Gérer les applications](manage-apps.md) s’applique à tous les membres de votre organisation et détermine s’ils peuvent interagir avec des applications personnalisées. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Par défaut, ce paramètre est activé. Si ce paramètre est désactivé, les utilisateurs de votre organisation ne peuvent pas voir ni installer d’applications personnalisées, y compris des applications Microsoft Power Platform. Pour plus d’informations, consultez [Gérer les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Autoriser ou bloquer des applications Microsoft Power Platform pour votre organisation

Par défaut, **les applications Shared Power Apps** et **Shared Power Virtual Agent** sont autorisées pour tous les utilisateurs Teams de votre organisation. Vous pouvez les bloquer ou les autoriser au niveau de l’organisation dans la page [Gérer les applications](manage-apps.md) du centre d’administration Microsoft Teams.  

1. Dans le volet gauche du centre d’administration Microsoft Teams, accédez à **Teams applications** **AppsManage** > . Vous devez être administrateur général ou administrateur de service Teams pour accéder à la page.
2. Dans la liste des applications, effectuez l’une des opérations suivantes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Capture d’écran de la page Gérer les applications, montrant les applications Microsoft Power Platform partagées":::

    - Pour bloquer les applications créées dans Power Apps ou Power Virtual Agents pour tous les utilisateurs de votre organisation, recherchez **Shared Power Apps** ou **Shared Power Virtual Agent Apps**, sélectionnez-la, puis cliquez sur **Bloquer**.
    - Pour autoriser les applications créées dans Power Apps ou Power Virtual Agents pour tous les utilisateurs de votre organisation, recherchez **shared Power Apps** ou **Shared Power Virtual Agent Apps**, sélectionnez-la, puis cliquez sur **Autoriser**.

### <a name="allow-or-block-microsoft-power-platform-apps-for-specific-users"></a>Autoriser ou bloquer des applications Microsoft Power Platform pour des utilisateurs spécifiques

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’accéder aux applications créées dans Power Apps ou Power Virtual Agents, créez et affectez une ou plusieurs [stratégies d’autorisation d’application personnalisées](teams-app-permission-policies.md).

Par exemple, pour empêcher des utilisateurs spécifiques d’accéder aux applications créées dans Power Apps, créez une stratégie d’autorisation d’application personnalisée pour bloquer les **Power Apps partagés**, puis attribuez la stratégie à ces utilisateurs.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Capture d’écran de l’exemple de stratégie d’autorisation d’application personnalisée avec shared Power Apps bloqué.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform

Vous pouvez utiliser les journaux d’audit pour Teams afin d’examiner les événements où les utilisateurs ont installé des applications Microsoft Power Platform à partir de la section **Built by vos collègues** de la page Applications dans Teams. Pour ce faire, [recherchez dans le journal d’audit](./audit-log-events.md) l’événement **Teams d’application installée** (sous l’opération **AppInstalled**) pour un utilisateur ou un ensemble d’utilisateurs. Pour rechercher les applications installées à partir de **Built par vos collègues**, recherchez la valeur **TemplatedInstance** dans la propriété **AppDistributionMode** dans les détails d’un enregistrement donné.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Capture d’écran de la valeur TemplatedInstance dans la propriété AppDistributionMode.":::

> [!NOTE]
> Vous pouvez exporter des enregistrements d’audit au format CSV pour faciliter le filtrage.

## <a name="related-topics"></a>Voir aussi

- [Partager une application canevas dans Power Apps](/powerapps/maker/canvas-apps/share-app)
- [Partager votre bot avec d’autres utilisateurs](/power-virtual-agents/admin-share-bots)
- [Gérer les applications dans le centre d’administration Microsoft Teams](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Publier une application personnalisée envoyée via l’API de soumission d’application Teams](submit-approve-custom-apps.md)
