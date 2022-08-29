---
title: Gérer vos applications dans le Centre d’administration Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
ms.custom: intro-get-started
audience: admin
ms.collection:
- M365-collaboration
- m365-frontline
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer les applications Teams. Découvrez comment autoriser ou bloquer des applications, vérifier l’état au niveau de l’organisation et les propriétés des applications, charger des applications personnalisées et gérer les paramètres d’application.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5c769a5cb8aab00265dee90bcce4b093c50e2a90
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397055"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gérer les applications Teams dans le Centre d’administration Microsoft Teams

Vous gérez les applications pour votre organisation dans la page **Applications Teams** dans le portail du Centre d’administration Teams. Utilisez la page Gérer les applications pour afficher et gérer toutes les applications Teams dans le catalogue d’applications de votre organisation, prendre en charge les cas d’usage importants pour la gestion des applications, définir l’accès aux applications à l’aide de stratégies, etc.

:::image type="content" source="media/manage-apps.png" alt-text="Capture d’écran de la page Gérer les applications." lightbox="media/manage-apps.png":::

Pour gérer les applications, vous utilisez des stratégies pour contrôler les autorisations des utilisateurs, l’installation d’applications et le chargement d’applications personnalisées créées au sein de votre organisation. Pour comprendre les stratégies, consultez [Vue d’ensemble des stratégies d’application](app-policies.md).

Pour utiliser le Centre d’administration Teams, vous devez disposer d’un rôle Administrateur général ou Administrateur Teams. Pour plus d’informations, consultez [Rôles d’administrateur Teams](./using-admin-roles.md) et [Rôles d’administrateur Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La page Gérer les applications n’est pas disponible dans les déploiements Microsoft 365 Cloud de la communauté du secteur public High (GCCH) ou Department of Defense (DoD) de Teams.

Lors de la création d’une application, les développeurs créent et ajoutent un ID d’application au fichier manifeste. Vous pouvez afficher cet ID d’application externe sur la page Gérer les applications après avoir activé la colonne `External app ID` à partir des paramètres de colonne. Vous pouvez également l’afficher sur la page des détails de l’application d’une application personnalisée. L’ID s’applique uniquement aux applications personnalisées.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Cas d’utilisation de la gestion des applications et interfaces disponibles

Les options permettant d’accomplir la plupart des cas d’utilisation de la gestion des applications sont disponibles dans le Centre d’administration Teams. En outre, certaines options sont disponibles dans d’autres portails ou dans d’autres pages du Centre d’administration Teams.

Les tâches de gestion des applications prises en charge dans le Centre d’administration se trouvent dans le tableau ci-dessous.

| Cas d’utilisation de la gestion des applications | Lien vers l’interface | Documentation |
|:----|:----|:----|
| Contrôlez les applications disponibles pour les utilisateurs de votre organisation en autorisant et en bloquant les applications. Vous pouvez également charger et approuver des applications personnalisées. Après avoir géré les applications sur cette page, vous pouvez utiliser les stratégies d’autorisation et de configuration des applications pour configurer les applications disponibles pour des utilisateurs spécifiques dans le magasin d’applications de votre organisation. | [Gérer les applications dans le Centre d’administration Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Article actuel |
| Les stratégies d’autorisation d’application contrôlent les applications que vous souhaitez mettre à la disposition des utilisateurs Teams de votre organisation. Vous pouvez utiliser la stratégie par défaut globale (à l’échelle de l’organisation) et la personnaliser, ou vous pouvez créer une ou plusieurs stratégies pour répondre aux besoins de votre organisation. | [Stratégies d’autorisation](https://admin.teams.microsoft.com/policies/app-permission) | [Gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md) |
| Les stratégies de configuration d’application contrôlent la façon dont les applications sont mises à la disposition d’un utilisateur avec l’application Teams. Utilisez la stratégie globale (par défaut à l’échelle de l’organisation) et personnalisez-la ou créez des stratégies personnalisées et attribuez-les à un ensemble d’utilisateurs. | [Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup) | [Gérer les stratégies de configuration des applications](teams-app-setup-policies.md) |
| Vous pouvez développer et charger des applications personnalisées en tant que packages d’application et les rendre disponibles dans le magasin d’applications de votre organisation. | Paramètres d’application à l’échelle de l’organisation dans [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) | [Gérer les stratégies d’application personnalisées](teams-custom-app-policies-and-settings.md) |
| Vous pouvez personnaliser le magasin d’applications Teams avec le logo, l’arrière-plan personnalisé ou la couleur de votre organisation. | [Personnaliser le magasin](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personnaliser le magasin d’applications de votre organisation](customize-your-app-store.md) |
| Le rapport d’utilisation des applications Teams fournit des informations sur les applications utilisées, les utilisateurs actifs et d’autres informations sur l’utilisation des applications. | [Rapports d’utilisation](https://admin.teams.microsoft.com/analytics/reports) | [Rapport d’utilisation des applications Teams](teams-analytics-and-reports/app-usage-report.md) |
| Vos utilisateurs peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des invités. Ils peuvent également utiliser des applications partagées par des invités lorsqu’ils rejoignent des réunions ou des conversations hébergées en externe. Les stratégies de données de l’organisation de l’utilisateur hôte et les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur sont appliquées. | [Accès externe](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportement des applications en fonction des types d’utilisateurs](non-standard-users.md) |
| Avec l’accès invité, vous pouvez fournir l’accès aux applications et à d’autres fonctionnalités Teams aux personnes extérieures à votre organisation, tout en conservant le contrôle sur vos données d’entreprise. | [Accès invité](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Accès invité dans Teams](guest-access.md) |
| Les stratégies de mise à jour Teams sont utilisées pour gérer les utilisateurs teams et Office en préversion qui peuvent voir les fonctionnalités de préversion ou de préversion dans l’application Teams. | [Stratégies de mise à jour Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Préversion publique de Teams](public-preview-doc-updates.md) |

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

La page Gérer les applications est l’endroit où vous autorisez ou bloquez des applications individuelles au niveau de l’organisation. La page affiche l’ensemble de l’application disponible et l’état actuel de l’application au niveau de l’organisation. La liste des applications inclut les applications fournies par Microsoft, par des développeurs tiers et par des développeurs au sein de votre organisation.

Pour autoriser ou bloquer une application :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**
1. Sélectionnez une application dans la liste des applications. Vous pouvez effectuer une recherche par le nom de l’application.
1. Sélectionnez l’option **Autoriser** ou **Bloquer**.

Lorsque vous autorisez (ou bloquez) une application sur la page [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) dans le Centre d’administration Teams, l’application particulière est autorisée (ou bloquée) pour tous les utilisateurs de votre organisation. Cette méthode diffère de la stratégie d’autorisation d’application dans le contexte où l’autorisation (ou le blocage) d’une application via une stratégie d’autorisation a un impact uniquement sur les utilisateurs spécifiques auxquels la stratégie est affectée.

Un utilisateur peut installer et utiliser une application uniquement lorsque l’application est autorisée via le paramètre à l’échelle du client et autorisée pour l’utilisateur via une stratégie d’autorisation.

## <a name="manage-user-requests-to-allow-apps"></a>Gérer les demandes des utilisateurs pour autoriser les applications

Les utilisateurs finaux peuvent afficher, mais pas utiliser, les applications bloquées dans Teams Store. Pour les applications bloquées, une option est disponible pour demander l’approbation de l’administrateur. Ces demandes sont assemblées dans le Centre d’administration Teams et les administrateurs peuvent afficher et gérer les demandes quand ils le souhaitent. Nous vous recommandons vivement d’effectuer régulièrement un tri pour vérifier les demandes des utilisateurs finaux.

  :::image type="content" source="media/user-request-blocked-apps.png" alt-text="Demandez à un administrateur d’approuver une application bloquée en sélectionnant l’option d’approbation de demande dans Teams Store.":::

### <a name="view-a-request"></a>Afficher une demande

 1. Connectez-vous au Centre d’administration Teams et accédez aux **[applications De gestion des applications](https://admin.teams.microsoft.com/policies/manage-apps)** **Teams** > .

    :::image type="content" source="media/requested-apps1.png" alt-text="Les demandes des utilisateurs finaux pour les applications bloquées sont affichées dans le Centre d’administration Teams dans la colonne intitulée Demandes des utilisateurs." lightbox="media/requested-apps.png":::

 1. Pour afficher et vérifier le nombre de demandes pour chaque application, triez les demandes dans la colonne **Demandes par utilisateur** . Vous ne pouvez pas afficher le nom des utilisateurs qui ont demandé une application.
 1. Pour autoriser une application, sélectionnez le nom de l’application, ce qui ouvre la page des détails de l’application.
 1. Sélectionnez **Gérer les demandes** et effectuez les étapes affichées dans la boîte de dialogue contextuelle. Selon la méthode utilisée pour bloquer une application, une ou plusieurs des étapes suivantes sont nécessaires pour la débloquer :

    * Si l’application est bloquée à l’aide de stratégies d’autorisation, autorisez l’application en modifiant les [stratégies d’autorisation](teams-app-permission-policies.md).
    * Si l’application est bloquée pour tous les utilisateurs, [autorisez l’application](#allow-and-block-apps).
    * Si toutes les applications sont bloquées pour tous les utilisateurs, modifiez les [paramètres à l’échelle de l’organisation](#manage-org-wide-app-settings).

 Si un administrateur autorise une application, Teams n’informe pas l’utilisateur final que sa demande est prise en compte. L’utilisateur peut afficher l’application dans Teams Store pour vérifier s’il peut ou non ajouter l’application à son client Teams. Si l’application est approuvée par un administrateur, les utilisateurs peuvent l’ajouter. Si l’administrateur n’approuve pas la demande et la rejette, les utilisateurs finaux pourront la demander à nouveau.

### <a name="dismiss-a-user-request"></a>Ignorer une demande d’utilisateur

 1. Sélectionnez le nom de l’application pour laquelle vous souhaitez ignorer les demandes de l’utilisateur.
 1. Sélectionnez **Gérer les demandes** , puis **Ignorer toutes les demandes** dans la boîte de dialogue.
 1. Lorsqu’une demande est ignorée, elle réinitialise les demandes de l’utilisateur à zéro.

  :::image type="content" source="media/reject.png" alt-text="Les administrateurs peuvent approuver une demande utilisateur en autorisant une application, ou peuvent rejeter la demande en n’effectuant aucune action.":::

Si un administrateur ignore une demande, cela n’informe pas l’utilisateur final que sa demande a été prise en compte. Une fois qu’un administrateur a ignoré une demande, l’utilisateur final peut à nouveau faire la demande de l’application.

## <a name="allow-the-apps-that-are-blocked-by-the-developers"></a>Autoriser les applications bloquées par les développeurs

Lorsqu’un développeur publie une application dans Teams Store, certaines applications peuvent nécessiter une configuration de la part d’un administrateur. Les administrateurs rendent l’application disponible pour les utilisateurs finaux lors de la configuration de l’application.

Par exemple, Contoso Electronics est un développeur d’applications qui a créé une application de support technique pour Microsoft Teams. Contoso Electronics souhaite que ses clients configurent certaines propriétés de l’application afin que, lorsque les utilisateurs interagissent avec l’application, elle fonctionne comme prévu. Avant qu’un administrateur autorise l’application, elle s’affiche comme **Bloquée par l’éditeur** dans le Centre d’administration Teams et est masquée par défaut aux utilisateurs finaux. Après avoir suivi les instructions de l’éditeur pour configurer l’application, vous pouvez la mettre à la disposition des utilisateurs en définissant l’état sur **Autorisé**.

:::image type="content" source="media/blocked-by-publisher.png" alt-text="Capture d’écran de l’état « Bloquée par l’éditeur » dans le centre d’administration de Teams.":::

Pour plus d’informations sur la façon dont les développeurs bloquent une application par défaut, consultez [Masquer l’application jusqu’à ce que l’administrateur approuve](/microsoftteams/platform/concepts/design/enable-app-customization#hide-teams-app-until-admin-approves).

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’organisation

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée, si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent charger ou interagir avec des applications personnalisées dans votre organisation. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs.

> [!NOTE]
> Pour savoir comment utiliser les paramètres d’application à l’échelle de l’organisation dans Microsoft 365 Government : les déploiements de Teams Cloud de la communauté du secteur public High (GCCH) et Department of Defense (DoD), consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

1. Dans la page **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)** , sélectionnez **Paramètres d’application à l’échelle de l’organisation**. Vous pouvez ensuite configurer les paramètres souhaités dans le volet.

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

1. Sous **Applications personnalisées**, désactivez ou activez **Autoriser l’interaction avec les applications personnalisées**. Ce paramètre contrôle si les utilisateurs peuvent interagir avec des applications personnalisées. Pour plus d’informations, consultez [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-custom-app-policies-and-settings.md).
1. Sélectionnez **Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

## <a name="related-article"></a>Article connexe

* [Gérer Teams pendant la transition à partir du Centre d’administration Skype Entreprise](manage-teams-skypeforbusiness-admin-center.md)
