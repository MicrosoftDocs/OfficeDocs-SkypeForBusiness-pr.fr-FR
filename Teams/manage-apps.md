---
title: Gérer vos applications dans le centre d’administration Microsoft Teams
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
description: Découvrez comment gérer vos applications Teams dans la page Gérer les applications du Centre d’administration Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: a6e6adbfbed5e1b371655ca74aa6ca6c717490c9
ms.sourcegitcommit: 06d1c50c9b55b062d61844a856676d9837fd5abe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "65030940"
---
# <a name="manage-teams-apps-in-the-microsoft-teams-admin-center"></a>Gérer Teams applications dans le Centre d’administration Microsoft Teams

Vous gérez les applications de votre organisation dans **Teams applications** du Centre d’administration. Utilisez la page [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps) pour afficher et gérer toutes les applications Teams dans le catalogue d’applications de votre organisation. La page Gérer les applications vous donne une vue de toutes les applications disponibles dans votre catalogue de locataires, en vous fournissant les informations dont vous avez besoin pour décider quelles applications autoriser ou bloquer au sein de votre organisation. Vous pouvez voir l’état et les propriétés au niveau de l’organisation des applications, bloquer ou autoriser des applications au niveau de l’organisation, charger de nouvelles applications personnalisées dans votre catalogue de locataires et gérer les paramètres d’application à l’échelle de l’organisation.

![Capture d’écran de la page Gérer les applications.](media/manage-apps.png)

Pour gérer les applications, vous utilisez les stratégies suivantes pour contrôler les autorisations pour les utilisateurs, l’installation d’applications et le chargement d’applications personnalisées créées au sein de votre organisation. Pour comprendre les stratégies, consultez [Vue d’ensemble des stratégies d’application](app-policies.md).

Pour en savoir plus sur l’obtention de rôles d’administrateur et d’autorisations, consultez [Teams rôles d’administrateur](./using-admin-roles.md).

> [!NOTE]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

> [!NOTE]
> La page Gérer les applications n’est pas disponible dans les déploiements Microsoft 365 Cloud de la communauté du secteur public High (GCCH) ou Department of Defense (DoD) de Teams.

<!--- TBD: This info belongs in the app policy overview article. Title it as mentioned in the spreadsheet.

* **App permission policy**: With it, you can control what apps are available to specific users in your organization. You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization. See [Manage app permission policies in Teams](teams-app-permission-policies.md).
* **App setup policies**: It lets you customize the app experience for your users. You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients. See [Manage app setup policies in Teams](teams-app-setup-policies.md).
* **Custom app policies and settings**: Teams allows developers in your organization to build, test, and deploy custom apps to other users. Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context. You can use app setup policies to control who in your organization can upload custom apps. You can also set org-wide settings to control whether users can interact with specific custom apps. See [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings).

The following are the important use cases you can accomplish via the the Manage apps page:

* [Allow or block apps at the org level](#allow-and-block-apps)
* [Apps blocked by publishers](#apps-blocked-by-publishers)
* [Add apps to teams](#add-an-app-to-a-team)
* [Approve or upload new custom apps to your organization's app store](#publish-a-custom-app-to-your-organizations-app-store)
* [View permissions requested by apps](#view-resource-specific-consent-permissions)
* [Grant consent to apps](#grant-admin-consent-to-apps)
* [Purchase service for third-party apps](#purchase-services-for-third-party-apps)
* [See org-level status and properties of apps](#view-apps)
* [Manage org-wide app settings](#manage-org-wide-app-settings)
* [View security and compliance information for Microsoft 365 Certified apps](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

<!--- TBD: Commenting for now in favor of the definition list above: 

The Manage apps page gives you a view into all available apps, providing you with the information you need to decide which apps to allow or block across your organization. You can then use [app permission policies](teams-app-permission-policies.md), [app setup policies](teams-app-setup-policies.md), and [custom app policies and settings](teams-custom-app-policies-and-settings.md) to configure the app experience for specific users in your organization.

In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**. You must be a global admin or Teams service admin to access the page.

--->

<!--- TBD: Move this view apps section to a new article about navigating and understanding TAC. It is yet to be created.

## View apps

You can view every app including the following information about each app.

![Screenshot of the apps details page for an app.](media/app-detail-page.jpg)

- **Name**: The app name. Select the app name to go to the app details page to see more information about the app. This includes a description of the app, whether it's allowed or blocked, version, privacy policy, terms of use, categories that apply to the app, certification status, supported capabilities, and app ID.
- **Certification**: If the app has gone through certification, you'll see either **Microsoft 365 certified** or **Publisher attestation**. Select the link to view certification details for the app. If you see `--`, we don't have certification information for the app. To learn more about certified apps in Teams, read [Microsoft 365 App Certification program](/microsoft-365-app-certification/overview).
- **Publisher**: Name of the publisher.
- **Publishing status**: Publishing status of custom apps.
- **Status**: Status of the app at the org level, which can be one of the following:
  - **Allowed**: The app is available for all users in your organization.
  - **Blocked**: The app is blocked and not available for any users in your organization.
  - **Blocked by publisher**: The app is blocked by the publisher and is hidden from end-users by default. After you set up the app using the publisher's guidance, you can allow or block the app to make it available to end-users.
  - **Blocked org-wide**: The app is blocked in org-wide app settings.
      It's important to know that this column represents the allowed and blocked status of apps that were formerly on the **Org-wide settings** pane. You now view, block, and allow apps at the org-wide on the **Manage apps** page.
- **Licenses**: Indicates whether an app offers a Software as a Service (SaaS) subscription for purchase. This column applies only to third-party apps. Each third-party app will have one of the following values:
  - **Purchase**: The app offers a SaaS subscription and is available to purchase.  
  - **Purchased**: The app offers a SaaS subscription and you've purchased licenses for it.
  - **- -**: The app doesn't offer a SaaS subscription.
- **Custom app**: Whether the app is a custom app.
- **Permissions**: Indicates whether a third-party or custom app that's registered in Azure Active Directory (Azure AD) has permissions that need consent. You'll see one of the following values:
  - **View details**: The app has permissions that require consent before the app can access data.
  - **- -**: The app doesn't have permissions that need consent.
- **Categories**: Categories that apply to the app.
- **Version**: App version.
- **Admin can install in meetings**: Indicates whether an app can be installed by admins in Team meetings. [Learn more](teams-app-setup-policies.md#install-apps)

To see the information that you want in the table, select **Edit Column** in the upper-right corner to add or remove columns to the table.
--->

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publier une application personnalisée dans l’App Store de votre organisation

Utilisez la page Gérer les applications pour publier des applications conçues spécifiquement pour votre organisation. Une fois que vous avez publié une application personnalisée, elle est disponible pour les utilisateurs de l’App Store de votre organisation. Il existe deux façons de publier une application personnalisée dans l’App Store de votre organisation. La façon dont vous utilisez dépend de la façon dont vous obtenez l’application.

* [Approuver une application personnalisée](#approve-a-custom-app) : utilisez cette méthode si le développeur envoie l’application directement à la page Gérer les applications à l’aide de l’API de soumission d’application Teams. Vous pouvez ensuite examiner et publier (ou rejeter) l’application directement à partir de la page de détails de l’application.
* [Télécharger un package d’application](#upload-an-app-package) : utilisez cette méthode si le développeur vous envoie le package d’application au format .zip. Vous publiez l’application en chargeant le package d’application.

### <a name="approve-a-custom-app"></a>Approuver une application personnalisée

Le widget **Approbations en attente** de la page Gérer les applications vous avertit lorsqu’un développeur envoie une application à l’aide de l’API de soumission d’application Teams. Une application nouvellement soumise est répertoriée avec **l’état Publication** **soumis** et **l’état** **Bloqué**. Accédez à la page de détails de l’application pour afficher plus d’informations sur l’application, puis pour la publier, définissez **l’état de publication** sur **Publier**.

Vous êtes également averti lorsqu’un développeur envoie une mise à jour à une application personnalisée. Vous pouvez ensuite examiner et publier (ou rejeter) la mise à jour sur la page de détails de l’application. Toutes les stratégies d’autorisation d’application et les stratégies d’installation d’application restent appliquées pour l’application mise à jour.

Pour plus d’informations, consultez [Publier une application personnalisée envoyée via l’API de soumission d’application Teams](submit-approve-custom-apps.md).

### <a name="upload-an-app-package"></a>Télécharger un package d’application

Le développeur crée un package d’application Teams à l’aide [de Teams App Studio](/microsoftteams/platform/get-started/get-started-app-studio), puis vous l’envoie au format .zip. Lorsque vous disposez du package d’application, vous pouvez le charger dans l’App Store de votre organisation.

Pour charger une nouvelle application personnalisée, sélectionnez **Télécharger** pour charger le package d’application. L’application n’est pas mise en surbrillance après son chargement. Vous devez donc rechercher la liste des applications dans la page Gérer les applications pour la trouver.

Pour mettre à jour une application après son chargement, dans la liste des applications de la page Gérer les applications, sélectionnez le nom de l’application, puis sélectionnez **Mettre à jour**. Cette opération remplace l’application existante et toutes les stratégies d’autorisation d’application et stratégies d’installation d’application restent appliquées pour l’application mise à jour.

Pour en savoir plus, consultez [Publier une application personnalisée en chargeant un package d’application](upload-custom-apps.md).

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

La page Gérer les applications est l’endroit où vous autorisez ou bloquez des applications individuelles au niveau de l’organisation. Il affiche chaque application disponible et son état actuel au niveau de l’organisation. (Le blocage et l’autorisation des applications au niveau de l’organisation sont **passés du volet paramètres de l’application à l’échelle de l’organisation** à cet emplacement.)

Pour autoriser ou bloquer une application, sélectionnez-la, puis **sélectionnez Autoriser** ou **Bloquer**. Lorsque vous bloquez une application, toutes les interactions avec cette application sont désactivées et l’application n’apparaît pas dans Teams pour les utilisateurs de votre organisation.

Lorsque vous bloquez ou autorisez une application sur la page Gérer les applications, cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation.  Lorsque vous bloquez ou autorisez une application dans une stratégie d’autorisation d’application Teams, elle est bloquée ou autorisée pour les utilisateurs auxquels cette stratégie est affectée. Pour qu’un utilisateur puisse installer et interagir avec n’importe quelle application, vous devez autoriser l’application au niveau de l’organisation sur la page Gérer les applications et dans la stratégie d’autorisation d’application affectée à l’utilisateur.

 > [!NOTE]
 > Pour désinstaller une application, cliquez avec le bouton droit sur l’application, puis cliquez sur **Désinstaller** ou utilisez le menu **Autres applications** sur le côté gauche.

## <a name="apps-blocked-by-publishers"></a>Applications bloquées par les éditeurs

Lorsqu’un éditeur de logiciels indépendant publie une application dans l’App Store global, il peut avoir besoin d’administrateurs pour configurer ou personnaliser l’expérience de l’application. L’administrateur peut le mettre à la disposition des utilisateurs finaux lorsque l’application est entièrement configurée.

Par exemple, Contoso Electronics est un éditeur de logiciels indépendants qui a créé une application de support technique pour Microsoft Teams. Contoso Electronics souhaite que ses clients configurent certaines propriétés de l’application afin que, lorsque les utilisateurs interagissent avec l’application, elle fonctionne comme prévu. Avant qu’un administrateur puisse autoriser ou bloquer l’application, elle s’affiche comme **bloquée par l’éditeur** dans le centre d’administration Teams et est masquée par défaut par les utilisateurs finaux. Après avoir suivi les instructions de l’éditeur pour configurer l’application, vous pouvez la mettre à la disposition des utilisateurs en passant à l’état **Autorisé**, ou empêcher les utilisateurs d’utiliser l’application en remplaçant l’état **par Bloqué**.

![Capture d’écran de l’état bloqué par l’éditeur dans le Centre d’administration Teams.](media/blocked-by-publisher.png)

## <a name="add-an-app-to-a-team"></a>Ajouter une application à une équipe

Vous utilisez le bouton **Ajouter à l’équipe** pour installer une application dans une équipe. Gardez à l’esprit qu’il s’agit uniquement des applications qui peuvent être installées dans une étendue d’équipe. Le bouton **Ajouter à l’équipe** n’est pas disponible pour les applications qui peuvent uniquement être installées dans l’étendue personnelle.

![Capture d’écran du bouton Ajouter à l’équipe.](media/manage-apps-add-app-team.png)

1. Recherchez l’application souhaitée, puis sélectionnez l’application en cliquant à gauche du nom de l’application.
1. Sélectionnez **Ajouter à l’équipe**.
1. Dans le volet **Ajouter à l’équipe** , recherchez l’équipe à laquelle vous souhaitez ajouter l’application, sélectionnez l’équipe, puis **sélectionnez Appliquer**.

## <a name="customize-an-app"></a>Personnaliser une application

Vous pouvez désormais personnaliser une application pour inclure une apparence spécifique en fonction des besoins de votre organisation. Voir [Personnaliser des applications dans Teams](customize-apps.md).

## <a name="purchase-services-for-third-party-apps"></a>Acheter des services pour des applications tierces

Vous pouvez rechercher et acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation directement à partir de la page Gérer les applications. La colonne **Licences** du tableau indique si une application offre un abonnement SaaS payant. Sélectionnez **Acheter maintenant** pour afficher les plans et les informations de tarification et acheter des licences pour vos utilisateurs. Pour plus d’informations, consultez [Les services d’achat pour Teams applications tierces dans le Centre d’administration Microsoft Teams](purchase-third-party-apps.md).

## <a name="grant-admin-consent-to-apps"></a>Accorder le consentement de l’administrateur aux applications

Vous pouvez examiner et accorder le consentement aux applications qui demandent des autorisations pour le compte de tous les utilisateurs de votre organisation. Pour cela, les utilisateurs n’ont pas à examiner et à accepter les autorisations demandées par l’application lorsqu’ils démarrent l’application. La colonne **Autorisations** indique si une application dispose d’autorisations qui nécessitent un consentement. Vous verrez un lien **afficher les détails** de chaque application inscrite dans Azure AD disposant d’autorisations qui nécessitent un consentement. Pour plus d’informations, consultez [Afficher les autorisations d’application et accorder le consentement de l’administrateur dans le centre d’administration Microsoft Teams](app-permissions-admin-center.md).

## <a name="view-resource-specific-consent-permissions"></a>Afficher les autorisations de consentement spécifiques aux ressources

Les autorisations de consentement spécifiques aux ressources (RSC) permettent aux propriétaires d’équipe d’accorder un consentement pour qu’une application accède aux données d’une équipe et les modifie. Les autorisations RSC sont granulaires, Teams des autorisations spécifiques qui définissent ce qu’une application peut faire dans une équipe spécifique. Vous pouvez afficher les autorisations RSC sous l’onglet **Autorisations** de la page détails de l’application pour une application. Pour plus d’informations, consultez [Afficher les autorisations d’application et accorder le consentement de l’administrateur dans le centre d’administration Microsoft Teams](app-permissions-admin-center.md).

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’organisation

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée, si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent charger ou interagir avec des applications personnalisées dans votre organisation. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Vous pouvez les utiliser pour contrôler des applications malveillantes ou problématiques.

> [!NOTE]
> Pour savoir comment utiliser les paramètres d’application à l’échelle de l’organisation dans Microsoft 365 Gouvernement - Cloud de la communauté du secteur public les déploiements de Teams du haut GCCH et du ministère de la Défense ( DoD), consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

1. Dans la page Gérer les applications, sélectionnez **Paramètres d’application à l’échelle de l’organisation**. Vous pouvez ensuite configurer les paramètres souhaités dans le volet.

    :::image type="content" source="media/manage-apps-org-wide-app-settings.png" alt-text="Capture d’écran du volet Paramètres de l’application à l’échelle de l’organisation sur la page Gérer les applications":::

1. Sous **Applications personnalisées**, désactivez ou **activez Afficher les applications personnalisées**. Lorsque ce paramètre est activé, les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) bénéficient de l’expérience d’application de première ligne personnalisée. Cette expérience épingle les applications les plus pertinentes dans Teams pour les travailleurs de première ligne. Pour en savoir plus, consultez [Tailor Teams apps pour vos employés de première ligne](pin-teams-apps-based-on-license.md).

    Cette fonctionnalité est disponible pour les licences F. D’autres types de licences seront pris en charge à l’avenir.
1. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    - **Autoriser les applications tierces** : cette commande contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactivez ce paramètre, vos utilisateurs ne seront pas en mesure d’installer ou d’utiliser des applications tierces et l’état de l’application de ces applications s’affiche comme **bloqué à l’échelle de l’organisation** dans le tableau.

        > [!NOTE]
        > Lorsque **l’option Autoriser les applications tierces** est désactivée, [les webhooks sortants sont toujours activés](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) pour tous les utilisateurs, mais vous pouvez les contrôler au niveau de l’utilisateur en autorisant ou en bloquant l’application webhook sortante via des [stratégies d’autorisation d’application](teams-app-permission-policies.md). Notez que si vous disposez de [stratégies d’autorisation d’application](teams-app-permission-policies.md) existantes pour les **applications Microsoft** qui utilisent le paramètre **Autoriser des applications spécifiques et bloquent tous les autres** paramètres, et que vous souhaitez activer les webhooks sortants pour les utilisateurs, ajoutez l’application De webhook sortant à la liste.

        > [!NOTE]
        > Les utilisateurs de Teams peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des personnes d’autres organisations. Ils peuvent également utiliser des applications partagées par des personnes d’autres organisations lorsqu’ils rejoignent des réunions ou des conversations hébergées par ces organisations. Les stratégies de données de l’organisation de l’utilisateur hôte, ainsi que les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

    - **Autoriser toute nouvelle application tierce publiée sur le magasin par défaut** : cette option contrôle la publication automatique des nouvelles applications tierces publiées dans le magasin d’applications Teams dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

1. Sous **Applications personnalisées**, désactivez ou **activez Autoriser l’interaction avec les applications personnalisées**. Ce paramètre contrôle si les utilisateurs peuvent interagir avec des applications personnalisées. Pour plus d’informations, consultez [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-custom-app-policies-and-settings.md).
1. Sélectionnez **Enregistrer** pour que les paramètres d’application à l’échelle de l’organisation prennent effet.

<!--- TBD: Commenting this info for now. Move it later to the new article about compliance program and how/where admins can find info about compliant apps.

## View security and compliance information for Microsoft 365 Certified apps

When evaluating an app for their organization, admins can use independent Cloud Access Security Brokers (CASB), such as Microsoft Cloud App Security (MCAS), to find information about security and behaviors of an app. The Teams admin center includes security and compliance information from MCAS for Microsoft 365 Certified apps so you'll have more information on whether or not the app meets your needs.

> [!NOTE]
> This feature is available to all admins, whether or not your organization has a license that supports MCAS.

To access MCAS information, follow these steps:

1. In the Teams admin center, select **Manage apps** under **Teams apps**.
1. Select **Certification** to sort apps and push all Microsoft 365 Certified apps to the top of the table.
1. Choose a Microsoft 365 Certified app.
1. Select the **Security and compliance** tab.

![Screenshot of Teams admin center security and compliance tab.](media/mcas.png)

On this tab, you'll find information on security, compliance, and data protection. You can also expand each dropdown list to get more details about which capabilities are supported for the selected application.
--->
