---
title: Gérer vos applications dans le Centre d’administration Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vaibhava
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.manageapps.overview
description: Découvrez comment gérer les applications Teams. Découvrez comment autoriser ou bloquer des applications, vérifier l’état au niveau de l’organisation et les propriétés de l’application, charger des applications personnalisées et gérer les paramètres d’application.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 25e540a7709ab12b73a97cc94b1350630c302197
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529726"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gérer les applications Teams dans le Centre d’administration Microsoft Teams

Vous gérez les applications pour votre organisation dans la page **Applications Teams** dans le portail du Centre d’administration Teams. Utilisez la page Gérer les applications pour afficher et gérer toutes les applications Teams dans le catalogue d’applications de votre organisation.

![Capture d’écran de la page Gérer les applications.](media/manage-apps.png)

Pour utiliser le Centre d’administration Teams, vous devez disposer d’un rôle d’administrateur général Administration ou d’administrateur Teams. Pour plus d’informations, consultez les articles d’aide suivants :

* [Rôles d’administrateur Teams](./using-admin-roles.md).
* [Rôles d’administrateur Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles)

Pour gérer les applications, vous utilisez des stratégies pour contrôler les autorisations des utilisateurs, l’installation d’applications et le chargement d’applications personnalisées créées au sein de votre organisation. Pour comprendre les stratégies, consultez [Vue d’ensemble des stratégies d’application](app-policies.md).

> [!NOTE]
> La page Gérer les applications n’est pas disponible dans les déploiements Microsoft 365 Government Community Cloud High (GCCH) ou Department of Defense (DoD) de Teams.

Lors de la création d’une application, les développeurs créent et ajoutent un ID d’application au fichier manifeste. Vous pouvez afficher cet ID d’application externe sur la page Gérer les applications après avoir activé la colonne `External app ID` à partir des paramètres de colonne. Vous pouvez également l’afficher sur la page des détails de l’application d’une application personnalisée. L’ID s’applique uniquement aux applications personnalisées.

## <a name="app-management-use-cases-and-the-available-interfaces"></a>Cas d’utilisation de la gestion des applications et interfaces disponibles

Les options permettant d’accomplir la plupart des cas d’utilisation de la gestion des applications sont disponibles dans le Centre d’administration Teams. En outre, certaines options sont disponibles dans d’autres portails.

| Cas d’utilisation de la gestion des applications | Lien vers l’interface | Documentation |
|:----|:----|:----|
| **Dans le Centre d’administration Teams** | | |
| Contrôlez les applications disponibles pour les utilisateurs de votre organisation en autorisant et en bloquant les applications. Vous pouvez également charger et approuver des applications personnalisées. Après avoir géré les applications sur cette page, vous pouvez utiliser les stratégies d’autorisation d’application et de configuration des applications pour configurer les applications disponibles pour des utilisateurs spécifiques dans l’App Store de votre organisation. | [Gérer les applications dans le Centre d’administration Teams](https://admin.teams.microsoft.com/policies/manage-apps) | Article actuel |
| Les stratégies d’autorisation d’application contrôlent les applications que vous souhaitez mettre à la disposition des utilisateurs Teams de votre organisation. Vous pouvez utiliser la stratégie par défaut globale (à l’échelle de l’organisation) et la personnaliser, ou vous pouvez créer une ou plusieurs stratégies pour répondre aux besoins de votre organisation. | [Stratégies d’autorisation](https://admin.teams.microsoft.com/policies/app-permission) | [Gérer les stratégies d’autorisation d’application](teams-app-permission-policies.md) |
| Les stratégies d’installation d’application contrôlent la façon dont les applications sont mises à la disposition d’un utilisateur avec l’application Teams. Utilisez la stratégie globale (par défaut à l’échelle de l’organisation) et personnalisez-la ou créez des stratégies personnalisées et attribuez-les à un ensemble d’utilisateurs. | [Stratégies d’installation](https://admin.teams.microsoft.com/policies/app-setup) | [Gérer les stratégies d’installation d’application](teams-app-setup-policies.md) |
| Vous pouvez développer et charger des applications personnalisées en tant que packages d’application et les rendre disponibles dans l’App Store de votre organisation. | Paramètres d’application à l’échelle de l’organisation dans [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) | [Gérer les stratégies d’application personnalisées](teams-custom-app-policies-and-settings.md) |
| Vous pouvez personnaliser l’App Store Teams avec le logo, l’arrière-plan personnalisé ou la couleur de votre organisation. | [Personnaliser le magasin](https://admin.teams.microsoft.com/policies/customize-appstore) | [Personnaliser l’App Store de votre organisation](customize-your-app-store.md) |
| Le rapport d’utilisation des applications Teams fournit des informations sur les applications en cours d’utilisation, les utilisateurs actifs et d’autres informations sur l’utilisation des applications. | [Rapports d’utilisation](https://admin.teams.microsoft.com/analytics/reports) | [Rapport d’utilisation des applications Teams](teams-analytics-and-reports/app-usage-report.md) |
| Vos utilisateurs peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des invités. Ils peuvent également utiliser des applications partagées par des invités lorsqu’ils rejoignent des réunions ou des conversations hébergées en externe. Les stratégies de données de l’organisation de l’utilisateur hôte et les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur sont appliquées. | [Accès externe](https://admin.teams.microsoft.com/company-wide-settings/external-communications) | [Comportement de l’application en fonction des types d’utilisateurs](non-standard-users.md) |
| Avec l’accès invité, vous pouvez fournir l’accès aux applications et à d’autres fonctionnalités Teams aux personnes extérieures à votre organisation, tout en conservant le contrôle sur vos données d’entreprise. | [Accès invité](https://admin.teams.microsoft.com/company-wide-settings/guest-configuration) | [Accès invité dans Teams](guest-access.md) |
| Les stratégies de mise à jour sont utilisées pour gérer les utilisateurs teams et Office en préversion qui verront les fonctionnalités de préversion ou de préversion dans l’application Teams.  | [Stratégies de mise à jour Teams](https://admin.teams.microsoft.com/policies/updatemanagement) | [Préversion publique de Teams](public-preview-doc-updates.md) |
| **En dehors du Centre d’administration Teams** | | |
| Gérer les licences et les abonnements d’applications tierces dans Centre d'administration Microsoft 365 | [Centre d'administration Microsoft 365](https://admin.microsoft.com/#/licenses) | [Gérer les abonnements d’applications tierces](/microsoft-365/commerce/manage-saas-apps) |
| Auditez les événements d’application Teams sur portail de conformité Microsoft Purview. | [Audit](https://compliance.microsoft.com/auditlogsearch?viewid=Async%20Search) | [Activités Teams](audit-log-events.md#teams-activities) |
| Les applications peuvent se voir accorder des autorisations pour votre organisation et ses données par trois méthodes : un administrateur donne son consentement à l’application pour tous les utilisateurs, un utilisateur accorde le consentement à l’application, ou un administrateur qui intègre une application et qui active l’accès en libre-service ou attribue des utilisateurs directement à l’application. Vérifiez les autorisations Graph pour les applications. Vérifiez les autorisations fournies par les utilisateurs ou déléguées par les administrateurs. | [Portail Azure AD](https://aad.portal.azure.com/) | [Passer en revue les autorisations accordées aux applications](/azure/active-directory/manage-apps/manage-application-permissions) |

<!---
| xxx | [Manage users](https://admin.teams.microsoft.com/users) | [Add users and assign licenses](/microsoft-365/admin/add-users/add-users?view=o365-worldwide) |  
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publier une application personnalisée dans l’App Store de votre organisation

Utilisez la page Gérer les applications pour publier des applications conçues spécifiquement pour votre organisation. Une fois que vous avez publié une application personnalisée, elle est disponible pour les utilisateurs de l’App Store de votre organisation. Il existe deux façons de publier une application personnalisée dans l’App Store de votre organisation. La façon dont vous utilisez dépend de la façon dont vous obtenez l’application.

* [Approuver une application personnalisée](#approve-a-custom-app) : utilisez cette méthode si le développeur envoie l’application directement à la page Gérer les applications à l’aide de l’API De soumission d’applications Teams. Vous pouvez ensuite examiner et publier (ou rejeter) l’application directement à partir de la page de détails de l’application.
* [Charger un package d’application](#upload-an-app-package) : utilisez cette méthode si le développeur vous envoie le package d’application au format .zip. Vous publiez l’application en chargeant le package d’application.

### <a name="approve-a-custom-app"></a>Approuver une application personnalisée

Le widget **Approbations en attente** de la page Gérer les applications vous avertit lorsqu’un développeur envoie une application à l’aide de l’API De soumission d’application Teams. Une application nouvellement soumise est répertoriée avec **l’état Publication** **soumis** et **l’état** **Bloqué**. Accédez à la page de détails de l’application pour afficher plus d’informations sur l’application, puis pour la publier, définissez **l’état de publication** sur **Publier**.

Vous êtes également averti lorsqu’un développeur envoie une mise à jour à une application personnalisée. Vous pouvez ensuite examiner et publier (ou rejeter) la mise à jour sur la page de détails de l’application. Toutes les stratégies d’autorisation d’application et les stratégies d’installation d’application restent appliquées pour l’application mise à jour.

Pour plus d’informations, consultez [Publier une application personnalisée envoyée via l’API de soumission d’application Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Charger un package d’application

Le développeur crée un package d’application Teams à l’aide de [Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio), puis vous l’envoie au format .zip. Lorsque vous disposez du package d’application, vous pouvez le charger dans l’App Store de votre organisation.

Pour charger une nouvelle application personnalisée, **sélectionnez Charger** pour charger le package d’application. L’application n’est pas mise en surbrillance après son chargement. Vous devez donc rechercher la liste des applications dans la page Gérer les applications pour la trouver.

Pour mettre à jour une application après son chargement, dans la liste des applications de la page Gérer les applications, sélectionnez le nom de l’application, puis sélectionnez **Mettre à jour**. L’exécution d’une mise à jour remplace l’application existante et toutes les stratégies d’autorisation d’application et stratégies d’installation d’application restent appliquées pour l’application mise à jour.

Pour en savoir plus, consultez [Publier une application personnalisée en chargeant un package d’application](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

La page Gérer les applications est l’endroit où vous autorisez ou bloquez des applications individuelles au niveau de l’organisation. Il affiche chaque application disponible et son état actuel au niveau de l’organisation.

Pour autoriser ou bloquer une application :

1. Accédez au Centre d’administration Teams > applications Teams > Gérer les applications.
1. Sélectionnez une application dans la liste des applications.
1. Sélectionnez **Autoriser** ou **Bloquer**.

Lorsque vous bloquez ou autorisez une application sur la page Gérer les applications, cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation.  Lorsque vous bloquez ou autorisez une application dans une stratégie d’autorisation d’application Teams, elle est bloquée ou autorisée pour les utilisateurs auxquels cette stratégie est affectée. Pour qu’un utilisateur puisse installer et interagir avec n’importe quelle application, vous devez autoriser l’application au niveau de l’organisation sur la page Gérer les applications et dans la stratégie d’autorisation d’application affectée à l’utilisateur.

 > [!NOTE]
 > Pour désinstaller une application, cliquez avec le bouton droit sur l’application, puis cliquez sur **Désinstaller** ou utilisez le menu **Autres applications** sur le côté gauche.

## <a name="manage-user-requests-to-unblock-apps"></a>Gérer les demandes des utilisateurs pour débloquer des applications

Vous pouvez afficher les demandes de mise à disposition d’une application bloquée. La demande est envoyée à l’administrateur informatique, qui peut afficher et gérer les demandes des utilisateurs dans le Centre d’administration Teams.

  :::image type="content" source="media/user-request.png" alt-text="Déposer une demande d’approbation d’applications bloquées":::

### <a name="view-a-request"></a>Afficher une demande

 1. Connectez-vous au Centre d’administration Teams et [sélectionnez Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)

    :::image type="content" source="media/requested-apps1.png" alt-text="Demande des utilisateurs" lightbox="media/requested-apps.png" border="true":::

 1. Pour afficher et vérifier le nombre de demandes pour chaque application, triez les demandes dans la colonne **Demandes par utilisateur** .
 1. Sélectionnez le nom de l’application que vous souhaitez débloquer et ouvre la page de détails de l’application.
 1. Sélectionnez **Gérer les demandes** et effectuez les étapes affichées dans la boîte de dialogue contextuelle. Les étapes d’approbation d’une application varient en fonction de la méthode utilisée pour la bloquer.

    * Si l’application est bloquée à l’aide de stratégies d’autorisation, autorisez l’application en modifiant les [stratégies d’autorisation](teams-app-permission-policies.md).
    * Si l’application est bloquée pour tous les utilisateurs, [autorisez l’application](#allow-and-block-apps).
    * Si toutes les applications sont bloquées pour tous les utilisateurs, modifiez [les paramètres à l’échelle de l’organisation](#manage-org-wide-app-settings).

 Si un administrateur autorise une application, il n’informe pas l’utilisateur final que sa demande est effectuée. L’utilisateur doit visiter l’application dans le Windows Store pour vérifier si l’application est débloquée ou non.

### <a name="dismiss-a-user-request"></a>Ignorer une demande d’utilisateur

 1. Sélectionnez le nom de l’application pour laquelle vous souhaitez ignorer les demandes de l’utilisateur.
 1. Sélectionnez **Gérer les demandes** et **sélectionnez Ignorer toutes les demandes** dans la boîte de dialogue.
 1. Lorsqu’une demande est ignorée, elle réinitialise les demandes de l’utilisateur à zéro.

  :::image type="content" source="media/reject.png" alt-text="a bloqué le rejet des applications."border="true":::

Si un administrateur rejette une demande, il n’informe pas l’utilisateur final que sa demande est exécutée. L’utilisateur doit visiter l’application dans le Windows Store pour vérifier si l’application est débloquée ou non.

## <a name="apps-blocked-by-publishers"></a>Applications bloquées par les éditeurs

Lorsqu’un éditeur de logiciels indépendant publie une application dans l’App Store global, il peut avoir besoin d’administrateurs pour configurer ou personnaliser l’expérience de l’application. L’administrateur peut la mettre à la disposition des utilisateurs finaux lorsque l’application est configurée.

Par exemple, Contoso Electronics est un éditeur de logiciels indépendant qui a créé une application de support technique pour Microsoft Teams. Contoso Electronics souhaite que ses clients configurent certaines propriétés de l’application afin que, lorsque les utilisateurs interagissent avec l’application, elle fonctionne comme prévu. Avant qu’un administrateur puisse autoriser ou bloquer l’application, elle s’affiche comme **bloquée par l’éditeur** dans le Centre d’administration Teams et est masquée par défaut par les utilisateurs finaux. Après avoir suivi les instructions de l’éditeur pour configurer l’application, vous pouvez la mettre à la disposition des utilisateurs en définissant l’état **Sur Autorisé**, ou empêcher les utilisateurs d’utiliser l’application en remplaçant l’état **par Bloqué**.

<!--- 
![Screenshot of blocked by publisher status in teams admin center.](media/blocked-by-publisher.png)
--->

## <a name="add-an-app-to-a-team"></a>Ajouter une application à une équipe

Vous utilisez le bouton **Ajouter à l’équipe** pour installer une application dans une équipe. Cette option est disponible uniquement pour les applications qui peuvent être installées dans une étendue d’équipe. L’option n’est pas disponible pour les applications qui peuvent uniquement être installées dans l’étendue personnelle.

1. Recherchez une application par son nom et sélectionnez l’application. N’ouvrez pas la page des détails de l’application.
1. Sélectionnez **Ajouter à l’équipe**.

   :::image type="content" source="media/manage-apps-add-app-team-trimmed.png" alt-text="Capture d’écran de l’option Ajouter à l’équipe pour l’application qui peut être ajoutée à l’étendue de l’équipe." lightbox="media/manage-apps-add-app-team.png":::

1. Dans le volet **Ajouter à l’équipe** , recherchez l’équipe à laquelle vous souhaitez ajouter l’application, sélectionnez l’équipe, puis **sélectionnez Appliquer**.

## <a name="customize-an-app"></a>Personnaliser une application

Vous pouvez désormais personnaliser une application pour inclure une apparence spécifique en fonction des besoins de votre organisation. Consultez [Personnaliser les applications dans Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Acheter des services pour des applications tierces

Vous pouvez rechercher et acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation directement à partir de la page Gérer les applications. La colonne **Licences** du tableau indique si une application offre un abonnement SaaS payant. Sélectionnez **Acheter maintenant** pour afficher les plans et les informations de tarification et acheter des licences pour vos utilisateurs. Pour en savoir plus, consultez [Acheter des services pour les applications tierces Teams dans le Centre d’administration Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-permissions-and-consent-to-apps-to-use-end-user-information"></a>Accorder des autorisations et donner son consentement aux applications pour utiliser les informations de l’utilisateur final

Vous pouvez examiner et accorder le consentement aux applications qui demandent des autorisations pour le compte de tous les utilisateurs de votre organisation. Pour cela, les utilisateurs n’ont pas à examiner et à accepter les autorisations demandées par l’application lorsqu’ils démarrent l’application. La colonne **Autorisations** indique si une application dispose d’autorisations qui nécessitent un consentement. Vous verrez un lien **Afficher les détails** pour chaque application inscrite dans Azure AD disposant d’autorisations qui nécessitent un consentement. Pour plus d’informations, consultez [Afficher les autorisations d’application et accorder le consentement de l’administrateur dans le Centre d’administration Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Afficher les autorisations de consentement spécifiques aux ressources

Les autorisations de consentement spécifiques aux ressources (RSC) permettent aux propriétaires d’équipe d’accorder un consentement pour qu’une application accède aux données d’une équipe et les modifie. Les autorisations RSC sont des autorisations granulaires spécifiques à Teams qui définissent ce qu’une application peut faire dans une équipe spécifique. Vous pouvez afficher les autorisations RSC sous l’onglet **Autorisations** de la page détails de l’application pour une application. Pour plus d’informations, consultez [Afficher les autorisations d’application et accorder le consentement de l’administrateur dans le Centre d’administration Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’organisation

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée, si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent charger ou interagir avec des applications personnalisées dans votre organisation. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Vous pouvez les utiliser pour contrôler des applications malveillantes ou problématiques.

> [!NOTE]
> Pour savoir comment utiliser les paramètres d’application à l’échelle de l’organisation dans les déploiements Microsoft 365 Government - Government Community Cloud High GCCH et Department of Defense (DoD) de Teams, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

1. Dans la page Gérer les applications, sélectionnez **Paramètres d’application à l’échelle de l’organisation**. Vous pouvez ensuite configurer les paramètres souhaités dans le volet.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Capture d’écran du volet Paramètres de l’application à l’échelle de l’organisation sur la page Gérer les applications":::

1. Sous **Applications personnalisées**, désactivez ou **activez Afficher les applications personnalisées**. Lorsque ce paramètre est activé, les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée. Cette expérience épingle les applications les plus pertinentes dans Teams pour les travailleurs de première ligne. Pour plus d’informations, consultez [Les applications Tailor Teams pour vos employés de première ligne](pin-teams-apps-based-on-license.md).

    Cette fonctionnalité est disponible pour les licences F. D’autres types de licences seront pris en charge à l’avenir.
1. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    * **Autoriser les applications tierces** : cette commande contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactivez ce paramètre, vos utilisateurs ne seront pas en mesure d’installer ou d’utiliser des applications tierces et l’état de l’application de ces applications s’affiche comme **bloqué à l’échelle de l’organisation** dans le tableau.

        > [!NOTE]
        > Lorsque **l’option Autoriser les applications tierces** est désactivée, [les webhooks sortants sont toujours activés](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) pour tous les utilisateurs, mais vous pouvez les contrôler au niveau de l’utilisateur en autorisant ou en bloquant l’application webhook sortante via des [stratégies d’autorisation d’application](teams-app-permission-policies.md). Notez que si vous disposez de [stratégies d’autorisation d’application](teams-app-permission-policies.md) existantes pour les **applications Microsoft** qui utilisent le paramètre **Autoriser des applications spécifiques et bloquent tous les autres** paramètres, et que vous souhaitez activer les webhooks sortants pour les utilisateurs, ajoutez l’application De webhook sortant à la liste.

        > [!NOTE]
        > Les utilisateurs de Teams peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des personnes d’autres organisations. Ils peuvent également utiliser des applications partagées par des personnes d’autres organisations lorsqu’ils rejoignent des réunions ou des conversations hébergées par ces organisations. Les stratégies de données de l’organisation de l’utilisateur hôte, ainsi que les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

    * **Autoriser toute nouvelle application tierce publiée sur le magasin par défaut** : cette option contrôle la publication automatique des nouvelles applications tierces publiées dans le magasin d’applications Teams dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

1. Sous **Applications personnalisées**, désactivez ou **activez Autoriser l’interaction avec les applications personnalisées**. Ce paramètre contrôle si les utilisateurs peuvent interagir avec des applications personnalisées. Pour plus d’informations, consultez [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-custom-app-policies-and-settings.md).
1. Sélectionnez **Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

## <a name="see-also"></a>Voir aussi

* [Gérer Teams pendant la transition à partir du centre d’administration Skype Entreprise](manage-teams-skypeforbusiness-admin-center.md)
