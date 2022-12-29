---
title: Gérer vos applications dans le Centre d’administration Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: conceptual
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.date: 09/29/2022
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.reviewer: kojika
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer les applications Teams. Découvrez comment autoriser ou bloquer des applications, vérifier l’état au niveau de l’organisation et les propriétés des applications, charger des applications personnalisées et gérer les paramètres d’application.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: c88f8c4424cb82ea1482c5f6e1b90fd792279450
ms.sourcegitcommit: 339a35e461c84ee309ade1a53299ba12231df7a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/29/2022
ms.locfileid: "69677404"
---
# <a name="overview-of-app-management-and-governance-in-teams-admin-center"></a>Vue d’ensemble de la gestion et de la gouvernance des applications dans le Centre d’administration Teams

Vous gérez les applications pour votre organisation dans la page **Applications Teams** dans le portail du Centre d’administration Teams. Utilisez la page Gérer les applications pour afficher et gérer toutes les applications Teams dans le catalogue d’applications de votre organisation, prendre en charge les cas d’usage importants pour la gestion des applications, définir l’accès aux applications à l’aide de stratégies, etc.

:::image type="content" source="media/manage-apps.png" alt-text="Capture d’écran de la page Gérer les applications." lightbox="media/manage-apps.png":::

Pour gérer les applications, vous utilisez des stratégies pour contrôler les autorisations des utilisateurs, l’installation d’applications et le chargement d’applications personnalisées créées au sein de votre organisation. Pour comprendre les stratégies, consultez [Vue d’ensemble des stratégies d’application](app-policies.md).

Pour utiliser le Centre d’administration Teams, vous devez disposer d’un rôle Administrateur général ou Administrateur Teams. Pour plus d’informations, consultez [Rôles d’administrateur Teams](./using-admin-roles.md) et [Rôles d’administrateur Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La page Gérer les applications n’est pas disponible dans les déploiements Microsoft 365 Cloud de la communauté du secteur public High (GCCH) ou Department of Defense (DoD) de Teams.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Cas d’utilisation de la gestion des applications et interfaces disponibles

Les options permettant d’accomplir la plupart des cas d’utilisation de la gestion des applications sont disponibles dans le Centre d’administration Teams. En outre, certaines options sont disponibles dans d’autres portails ou dans d’autres pages du Centre d’administration Teams.

Les tâches de gestion des applications prises en charge dans le centre d’administration figurent dans le tableau ci-dessous.

| Cas d’utilisation de la gestion des applications | Lien vers l’interface | Documentation |
|:----|:----|:----|
| Contrôlez les applications disponibles pour les utilisateurs de votre organisation en autorisant et en bloquant les applications. Vous pouvez également charger et approuver des applications personnalisées. Après avoir géré les applications sur cette page, vous pouvez utiliser les stratégies d’autorisation et de configuration des applications pour configurer les applications disponibles pour des utilisateurs spécifiques dans le magasin d’applications de votre organisation. | [Gérer les applications dans le Centre d’administration Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Article actuel |
| Les stratégies d’autorisation d’application contrôlent les applications que vous souhaitez mettre à la disposition des utilisateurs Teams de votre organisation. Vous pouvez utiliser la stratégie par défaut globale (à l’échelle de l’organisation) et la personnaliser, ou vous pouvez créer une ou plusieurs stratégies pour répondre aux besoins de votre organisation. | [Stratégies d’autorisation](https://admin.teams.microsoft.com/policies/app-permission) | [Gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md) |
| Les stratégies de configuration d’application contrôlent la façon dont les applications sont mises à la disposition d’un utilisateur avec l’application Teams. Utilisez la stratégie globale (par défaut à l’échelle de l’organisation) et personnalisez-la ou créez des stratégies personnalisées et attribuez-les à un ensemble d’utilisateurs. | [Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup) | [Gérer les stratégies de configuration des applications](teams-app-setup-policies.md) |
| Vous pouvez développer et charger des applications personnalisées en tant que packages d’application et les rendre disponibles dans le magasin d’applications de votre organisation. | Paramètres d’application à l’échelle de l’organisation dans [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) | [Gérer le paramètre de stratégie pour les applications personnalisées](teams-custom-app-policies-and-settings.md) |
| Vous pouvez personnaliser le magasin d’applications Teams avec le logo, l’arrière-plan personnalisé ou la couleur de votre organisation. | [Personnaliser le magasin](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personnaliser le magasin d’applications de votre organisation](customize-your-app-store.md) |
| Le rapport d’utilisation des applications Teams fournit des informations sur les applications utilisées, les utilisateurs actifs et d’autres informations sur l’utilisation des applications. | [Rapports d’utilisation](https://admin.teams.microsoft.com/analytics/reports) | [Rapport d’utilisation des applications Teams](teams-analytics-and-reports/app-usage-report.md) |
| Vos utilisateurs peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des invités. Ils peuvent également utiliser des applications partagées par des invités lorsqu’ils rejoignent des réunions ou des conversations hébergées en externe. Les stratégies de données de l’organisation de l’utilisateur hôte et les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur sont appliquées. | [Accès externe](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportement des applications en fonction des types d’utilisateurs](non-standard-users.md) |
| Avec l’accès invité, vous pouvez fournir l’accès aux applications et à d’autres fonctionnalités Teams aux personnes extérieures à votre organisation, tout en conservant le contrôle sur vos données d’entreprise. | [Accès invité](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Accès invité dans Teams](guest-access.md) |
| Les stratégies de mise à jour Teams sont utilisées pour gérer les utilisateurs de Teams et d’Office en préversion qui peuvent voir les fonctionnalités en préversion ou en préversion dans l’application Teams. | [Stratégies de mise à jour Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Préversion publique de Teams](public-preview-doc-updates.md) |

Les tâches de gestion des applications prises en charge sur d’autres portails figurent dans le tableau ci-dessous.

| Cas d’utilisation de la gestion des applications | Lien vers l’interface | Documentation |
|:----|:----|:----|
| Gérer les licences et les abonnements d’applications tierces dans Centre d’administration Microsoft 365 | [Centre d’administration Microsoft 365](https://admin.microsoft.com/#/licenses) | [Gérer les abonnements d’applications tierces](/microsoft-365/commerce/manage-saas-apps) |
| Auditez les événements d’application Teams sur le portail de conformité Microsoft Purview. | [Audit](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Activités Teams](audit-app-management-activities.md) |
| Les applications peuvent recevoir des autorisations pour votre organisation et ses données par trois méthodes : un administrateur donne son consentement à l’application pour tous les utilisateurs, un utilisateur accorde son consentement à l’application, ou un administrateur intègre une application et permet un accès en libre-service ou assigne des utilisateurs directement à l’application. Vérifiez les autorisations Graph pour les applications. Vérifiez les autorisations fournies par les utilisateurs ou déléguées par les administrateurs. | [Portail Azure AD](https://aad.portal.azure.com/) | [Passer en revue les autorisations accordées aux applications](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

En tant qu’administrateur, vous contrôlez l’accès à tous les types d’applications utilisées dans tous les contextes par tous vos utilisateurs. Teams fournit des contrôles granulaires pour configurer l’accès pour chaque application et pour chaque utilisateur.

Pour autoriser une application, tous les paramètres suivants doivent être effectués. Pour bloquer une application, bloquez-la via l’un des paramètres suivants.

* [Paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings) : utilisez ce paramètre pour autoriser l’utilisation des applications dans votre organisation. Vous décidez quelles applications spécifiques sont utilisées.
* [Autoriser une application individuelle](manage-apps.md#allow-and-block-apps) : utilisez ce paramètre pour autoriser une application spécifique dans votre organisation. Vous décidez quels utilisateurs peuvent utiliser l’application.
* [Stratégie d’autorisation d’application](teams-app-permission-policies.md) : utilisez des stratégies pour autoriser tous les utilisateurs ou des utilisateurs spécifiques à utiliser une application. Vous décidez de l’accès par utilisateur et par application.

La page Gérer les applications est l’endroit où vous autorisez ou bloquez des applications individuelles au niveau de l’organisation. La page affiche l’ensemble de l’application disponible et l’état actuel de l’application au niveau de l’organisation. Pour autoriser ou bloquer une application, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Recherchez une application et sélectionnez-la.
1. Sélectionnez l’option **Autoriser** ou **Bloquer**.

Pour autoriser une application pour des utilisateurs spécifiques, consultez Stratégies [d’autorisation d’application](teams-app-permission-policies.md).

Lorsqu’un développeur publie une application dans le magasin Teams, certaines applications peuvent avoir besoin d’un administrateur pour configurer l’application. Avant qu’un administrateur n’autorise une telle application, elle s’affiche comme `Blocked by publisher` dans le centre d’administration. Après avoir suivi les instructions de l’éditeur pour configurer l’application, vous pouvez la mettre à la disposition des utilisateurs en l’autorisant.

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’organisation

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée, si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent charger ou interagir avec des applications personnalisées dans votre organisation.

> [!NOTE]
> Pour savoir comment utiliser les paramètres d’application à l’échelle de l’organisation dans Microsoft 365 Government : les déploiements de Teams Cloud de la communauté du secteur public High (GCCH) et Department of Defense (DoD), consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

1. Dans **[la page Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)** , sélectionnez **Paramètres de l’application à l’échelle de l’organisation**. Vous pouvez ensuite configurer les paramètres souhaités dans le volet.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Capture d’écran du volet Paramètres de l’application à l’échelle de l’organisation sur la page Gérer les applications":::

1. Sous **Applications personnalisées**, désactivez ou activez **Afficher les applications personnalisées**. Lorsque ce paramètre est activé, les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée. Cette expérience épingle les applications les plus pertinentes dans Teams pour les employés de première ligne. Pour en savoir plus, consultez [Personnaliser les applications Teams pour vos employés de première ligne](pin-teams-apps-based-on-license.md).

    Cette fonctionnalité est disponible pour les licences F. D’autres types de licences seront pris en charge à l’avenir.
1. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    * **Autoriser les applications tierces** : cette commande contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactivez ce paramètre, vos utilisateurs ne seront pas en mesure d’installer ou d’utiliser des applications tierces et l’état de l’application de ces applications s’affiche comme **Bloquée à l’échelle de l’organisation** dans le tableau.

        > [!NOTE]
        > Lorsque l’option **Autoriser les applications tierces** est désactivée, les [Webhooks sortants](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) sont toujours activés pour tous les utilisateurs, mais vous pouvez les contrôler au niveau de l’utilisateur en autorisant ou en bloquant l’application Webhooks sortants via des [stratégies d’autorisation d’application](teams-app-permission-policies.md). Notez que si vous disposez de [stratégies d’autorisation d’application](teams-app-permission-policies.md) existantes pour les **applications Microsoft** qui utilisent le paramètre **Autoriser des applications spécifiques et bloquent tous les autres** et que vous souhaitez activer les Webhooks sortants pour les utilisateurs, ajoutez l’application Webhook sortant à la liste.

        > [!NOTE]
        > Les utilisateurs de Teams peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des personnes d’autres organisations. Ils peuvent également utiliser des applications partagées par des personnes d’autres organisations lorsqu’ils rejoignent des réunions ou des conversations hébergées par ces organisations. Les stratégies de données de l’organisation de l’utilisateur hôte, ainsi que les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

    * **Autoriser toute nouvelle application tierce publiée sur le magasin par défaut** : cette option contrôle la publication automatique des nouvelles applications tierces publiées dans le magasin d’applications Teams dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

1. Sous **Applications personnalisées**, désactivez ou activez **Autoriser l’interaction avec les applications personnalisées**. Ce paramètre contrôle si les utilisateurs peuvent interagir avec des applications personnalisées. Pour en savoir plus, consultez [Gérer les stratégies et les paramètres des applications personnalisées](teams-custom-app-policies-and-settings.md).

1. Sélectionnez **Enregistrer**. Les paramètres prennent effet au bout de quelques heures.

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Gérer les paramètres d’application à l’échelle de l’organisation pour Microsoft 365 secteur public  

Dans un déploiement Microsoft 365 Government – GCC, GCCH et DoD de Teams, toutes les applications tierces sont bloquées par défaut. Dans les clouds GCCH et DOD, les applications tierces ne sont pas disponibles. De plus, dans GCC, vous voyez la note suivante sur la gestion des applications tierces sur la page des stratégies d'autorisation des applications dans le centre d'administration Microsoft Teams.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Capture d'écran de la politique d'autorisation des applications dans GCCH et DoD." lightbox="media/app-permission-policies-gcc.png":::

Utilisez les paramètres de l’application à l’échelle de l’organisation pour contrôler si les utilisateurs peuvent installer des applications tierces. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs.

<!---1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. 
--->

### <a name="for-gcc-clouds"></a>Pour les clouds GCC

1. Dans la page **Gérer les applications** **Teams,** >  sélectionnez **Paramètres de l’application à l’échelle de l’organisation**. Vous pouvez ensuite configurer les paramètres voulus dans le panneau.

   :::image type="content" source="media/app-permission-policies-gcc-org-wide.png" alt-text="Capture d’écran montrant les paramètres de l’application à l’échelle de l’organisation dans GCC.":::

1. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    * **Autoriser les applications tierces** : cette option contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous avez désactiver ce paramètre, vos utilisateurs ne pourront pas installer ou utiliser des applications tierces. Dans un déploiement Microsoft 365 Government – GCCH et DoD de Teams, ce paramètre est désactivé par défaut.
    * **Autoriser les nouvelles applications tierces publiées dans le magasin par défaut** : cette option contrôle si les nouvelles applications tierces publiées dans la boutique d'applications Teams deviennent automatiquement disponibles dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

1. Sous **Applications bloquées**, ajoutez les applications que vous voulez bloquer au sein de votre organisation. Dans un déploiement Microsoft 365 Government – GCCH et DoD de Teams, toutes les applications tierces sont ajoutées à cette liste par défaut. Pour une application tierce que vous voulez autoriser dans votre organisation, supprimez l’application de cette liste d’applications bloquées. Lorsque vous bloquez une application à l'échelle de l'organisation, l'application est automatiquement bloquée pour tous vos utilisateurs, qu'elle soit ou non autorisée dans les stratégies d'autorisation d'application.

1. Sélectionnez **Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

Pour autoriser les applications tierces, modifiez et utilisez la stratégie globale (par défaut à l’échelle de l’organisation) ou créez et affectez une stratégie créée par l’administrateur.

### <a name="for-gcch-and-dod-clouds"></a>Pour les clouds GCCH et DoD

1. Connectez-vous au Centre d’administration Teams et accédez aux **stratégies d’autorisation** **des applications** >  Teams.

1. Sélectionnez **Paramètres de l’application à l’échelle de l’organisation**. Sous **Applications bloquées**, ajoutez les applications que vous voulez bloquer au sein de votre organisation. Dans un déploiement Microsoft 365 Government – GCCH et DoD de Teams, toutes les applications tierces sont ajoutées à cette liste par défaut. Lorsque vous bloquez une application à l'échelle de l'organisation, l'application est automatiquement bloquée pour tous vos utilisateurs, qu'elle soit ou non autorisée dans les stratégies d'autorisation d'application.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Capture d'écran des paramètres d'application à l'échelle de l'organisation dans GCCH et DoD.":::

1. Sélectionnez **Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

## <a name="related-article"></a>Article connexe

* [Gérer les demandes des utilisateurs pour autoriser les applications](user-requests-approve-apps.md).
