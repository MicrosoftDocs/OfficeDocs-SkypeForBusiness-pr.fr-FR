---
title: Gérer les applications Microsoft Power Platform dans le centre d'administration Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/27/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment gérer l'accès aux applications personnalisées créées à l'aide de Microsoft Power Platform dans le centre d'administration Teams.
ms.openlocfilehash: c4ac0bd3551bb53da06de3301447c6bf4842540c
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912583"
---
# <a name="manage-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gérer les applications Microsoft Power Platform dans le centre d'administration Teams

Cet article vous donne une vue d’ensemble de la gestion des applications personnalisées créées à l’aide des applications [Microsoft Power Platform](https://powerplatform.microsoft.com/) dans le Centre d’administration Microsoft Teams. Les applications personnalisées sont créées par les développeurs au sein de votre organisation pour les utilisateurs internes.

> [!NOTE]
> Cet article ne s'applique pas à l'application Power Apps ou à l'application Power Virtual Agents qui sont installées à partir de la page Applications ou épinglées à Teams via une stratégie de configuration d'application. Vous pouvez gérer les applications du Store à l’aide de [stratégies d’autorisation d’application](teams-app-permission-policies.md) et de [stratégies d’installation d’application](teams-app-setup-policies.md).

[Power Apps](https://powerapps.microsoft.com) est un environnement de développement d'applications low-code ou no-code que les créateurs d'applications de votre organisation peuvent utiliser pour créer des applications personnalisées qui se connectent à vos données d'entreprise. [Power Virtual Agents](/power-virtual-agents/fundamentals-what-is-power-virtual-agents) est un environnement de création de robots sans code permettant aux développeurs d'applications de créer des robots puissants. Avec l'intégration des applications Microsoft Power Platform dans Teams, les organisations peuvent rationaliser les processus métier, répondre plus rapidement aux besoins changeants de l'entreprise pour favoriser une plus grande collaboration, et créer et partager des solutions personnalisées pour être plus productives.  

Les applications Microsoft Power Platform créées par les développeurs de votre organisation sont automatiquement ajoutées à Teams. Les développeurs peuvent contrôler qui peut accéder à leur application en utilisant la [fonctionnalité de partage dans Power Apps](/powerapps/maker/canvas-apps/share-app) et de la [fonctionnalité de partage dans Power Virtual Agents](/power-virtual-agents/admin-share-bots).

Lorsqu'une application Microsoft Power Platform est créée ou partagée, les utilisateurs peuvent l'afficher et l'installer sur la page Applications en accédant à **Construit avec Power Platform**. (Cela peut prendre quelques minutes après la création ou le partage d'une application pour que l'application apparaisse ici.)

:::image type="content" source="media/manage-power-platform-apps-apps-page.png" alt-text="Captures d'écran de la page Applications, montrant les applications Microsoft Power Platform répertoriées dans Construit avec Power Platform.":::

Les utilisateurs finaux voient une application dans **Construit avec Power Platform** si l'application remplit l'une des conditions suivantes.

|Power Apps |Power Virtual Agents  |
|---------|---------|
|<ul><li>L’utilisateur a créé l’application.</li><li>L’application a été partagée directement avec l’utilisateur.</li><li>L’utilisateur a récemment utilisé l’application. </li></ul>| <ul><li>L’utilisateur a créé le bot.</li><li>Le bot appartient à une équipe dont l’utilisateur est membre. </li></ul>        |

Les utilisateurs installent les applications Microsoft Power Platform de la même manière qu'ils installent n'importe quelle autre application Teams. Gardez à l'esprit que les utilisateurs ne peuvent installer des applications que dans le contexte pour lequel ils disposent d'autorisations. Par exemple, une équipe appartenant à un utilisateur, une conversation dont l'utilisateur fait partie ou sa portée personnelle.

## <a name="manage-access-to-microsoft-power-platform-apps-in-the-teams-admin-center"></a>Gérer l'accès aux applications Microsoft Power Platform dans le centre d'administration Teams

En tant qu'administrateur, vous pouvez contrôler si les applications Microsoft Power Platform sont répertoriées dans **Construit avec Power Platform** sur la page Applications dans Teams. Vous pouvez bloquer ou autoriser collectivement toutes les applications créées dans Power Apps ou toutes les applications créées dans Power Virtual Agents au niveau de l'organisation sur la page [Gérer les applications](manage-apps.md) ou pour des utilisateurs spécifiques à l'aide des [stratégies d'autorisation d'application](teams-app-permission-policies.md).

Les applications **Shared Power Apps** et **Shared Power Virtual Agent Apps** dans la boutique d'applications de votre organisation représentent toutes les applications créées sur cette plate-forme particulière. Si vous bloquez l’une de ces applications ou les deux pour l’ensemble de l’organisation ou pour des utilisateurs spécifiques, les utilisateurs ne peuvent pas les installer dans Teams. Les utilisateurs ne peuvent pas demander l’approbation de l’administrateur pour autoriser les applications.

N'oubliez pas que vous pouvez contrôler l'accès à toutes les applications créées dans Power Apps et Power Virtual Agents, mais vous ne pouvez pas autoriser ou bloquer des applications individuelles. Le créateur de l'application décide qui peut accéder aux applications qu'il crée via la fonctionnalité de partage depuis Power Apps et Power Virtual Agents. Si un créateur a partagé une application qu'il a créée dans Power Virtual Agents avec un utilisateur et que vous avez bloqué les **applications Power Virtual Agents partagées** pour cet utilisateur, l'utilisateur ne pourra pas voir ni installer d'applications à partir de cette plate-forme dans Teams.

Si un utilisateur est autorisé à accéder aux applications à partir de Power Apps ou de Power Virtual Agents, et que vous l'empêchez ensuite d'accéder aux applications à partir de l'une ou des deux plateformes, l'utilisateur peut toujours accéder et utiliser les applications Microsoft Power Platforms qu'il a installées avant que vous ne bloquiez le application ou applications. Cependant, l'utilisateur ne peut plus installer d'applications à partir de ces plates-formes dans **Built with Power Platform**.

> [!NOTE]
> Le paramètre **Autoriser l’interaction avec les applications personnalisées** à l'échelle de l'organisation sur la page [Gérer les applications](manage-apps.md) s'applique à tous les membres de votre organisation et détermine s'ils peuvent interagir avec les applications personnalisées. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Si ce paramètre est désactivé, les utilisateurs de votre organisation ne peuvent installer aucune application personnalisée, y compris les applications Microsoft Power Platform. Pour plus d’informations, consultez [Gérer les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings).

### <a name="allow-or-block-microsoft-power-platform-apps-for-your-organization"></a>Autoriser ou bloquer les applications Microsoft Power Platform pour votre organisation

Par défaut, **Shared Power Apps** et **Shared Power Virtual Agent Apps** sont autorisés pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.  

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)** Vous devez être administrateur général ou administrateur de service Teams pour accéder à la page.
1. Dans la liste des applications, effectuez l’une des opérations suivantes.

    :::image type="content" source="media/manage-power-platform-apps-manage-apps.png" alt-text="Capture d’écran de la page Gérer les applications, montrant les applications Microsoft Power Platform partagées.":::

    * Pour bloquer les applications créées dans Power Apps ou Power Virtual Agents pour tous les utilisateurs de votre organisation, recherchez **Shared Power Apps** ou **Shared Power Virtual Agent Apps**, sélectionnez-le, puis sélectionnez **Block**.
    * Pour autoriser les applications créées dans Power Apps ou Power Virtual Agents pour tous les utilisateurs de votre organisation, recherchez **Shared Power Apps** ou **Shared Power Virtual Agent Apps**, sélectionnez-le, puis sélectionnez **Autoriser**.

### <a name="allow-microsoft-power-platform-apps-for-specific-users"></a>Autoriser les applications Microsoft Power Platform pour des utilisateurs spécifiques

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d'accéder aux applications créées dans Power Apps ou Power Virtual Agents, créez et attribuez une ou plusieurs [stratégies d'autorisation d'application](teams-app-permission-policies.md) personnalisées.

Par exemple, pour empêcher des utilisateurs spécifiques d’accéder aux applications créées dans Power Apps, créez une stratégie personnalisée pour les autorisations d’application afin de bloquer **Les applications Power Apps partagées**, puis affectez la stratégie à ces utilisateurs.

:::image type="content" source="media/manage-power-platform-apps-app-permission-policy.png" alt-text="Capture d’écran d’un exemple de stratégie personnalisée pour les autorisations d’application avec Shared Power Apps bloqué.":::

### <a name="use-audit-logs-to-investigate-microsoft-power-platform-installation-activity"></a>Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform

Vous pouvez utiliser les journaux d'audit pour Teams afin d'enquêter sur les événements où les utilisateurs ont installé des applications Microsoft Power Platform à partir de la section **Built with Power Platform** de la page Applications dans Teams. Pour ce faire, [rechercher dans le journal d'audit](./audit-log-events.md) l'événement **Installed app** Teams (sous l'opération **AppInstalled**) pour un utilisateur ou un ensemble d'utilisateurs. Pour rechercher des applications installées à partir de **Built with Power Platform**, recherchez la valeur **TemplatedInstance** dans la propriété **AppDistributionMode** dans les détails d'un enregistrement donné.

:::image type="content" source="media/manage-power-platform-apps-audit.png" alt-text="Capture d'écran de la valeur TemplatedInstance dans la propriété AppDistributionMode." lightbox="media/manage-power-platform-apps-audit.png":::

> [!NOTE]
> Vous pouvez exporter les enregistrements d'audit au format CSV pour faciliter le filtrage.

## <a name="related-articles"></a>Articles connexes

* [Partager une application canevas dans Power Apps](/powerapps/maker/canvas-apps/share-app)
* [Partager votre bot avec d'autres utilisateurs](/power-virtual-agents/admin-share-bots)
* [Gérer les applications dans le centre d'administration Microsoft Teams](manage-apps.md)
* [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
* [Publier une application personnalisée envoyée par le biais de l’API d’envoi d’applications Teams](submit-approve-custom-apps.md)
