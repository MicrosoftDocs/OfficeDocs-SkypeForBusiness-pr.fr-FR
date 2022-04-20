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
ms.openlocfilehash: 830850be078da8086253bbb57bb4a29ce6d7c951
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64961237"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gérer vos applications dans le centre d’administration Microsoft Teams

En tant qu’administrateur, vous pouvez afficher et gérer toutes les applications Teams pour votre organisation. Dans la page Gérer les applications du centre d’administration Teams, vous pouvez :

- [Autoriser ou bloquer des applications au niveau de l’organisation](#allow-and-block-apps)
- [Applications bloquées par les éditeurs](#apps-blocked-by-publishers)
- [Ajouter des applications à des équipes](#add-an-app-to-a-team)
- [Approuver ou charger de nouvelles applications personnalisées dans l’App Store de votre organisation](#publish-a-custom-app-to-your-organizations-app-store)
- [Afficher les autorisations demandées par les applications](#view-resource-specific-consent-permissions)
- [Accorder le consentement aux applications](#grant-admin-consent-to-apps)
- [Service d’achat pour les applications tierces](#purchase-services-for-third-party-apps)
- [Voir l’état au niveau de l’organisation et les propriétés des applications](#view-apps)
- [Gérer les paramètres d’application à l’échelle de l’organisation](#manage-org-wide-app-settings)
- [Afficher les informations de sécurité et de conformité pour les applications certifiées Microsoft 365](#view-security-and-compliance-information-for-microsoft-365-certified-apps)

La page Gérer les applications vous donne une vue de toutes les applications disponibles, en vous fournissant les informations dont vous avez besoin pour décider quelles applications autoriser ou bloquer au sein de votre organisation. Vous pouvez ensuite utiliser des [stratégies d’autorisation d’application](teams-app-permission-policies.md), des [stratégies d’installation d’application](teams-app-setup-policies.md) et [des stratégies et paramètres d’application personnalisés](teams-custom-app-policies-and-settings.md) pour configurer l’expérience d’application pour des utilisateurs spécifiques de votre organisation.

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**. Vous devez être administrateur général ou administrateur de service Teams pour accéder à la page.

![Capture d’écran de la page Applications gérées.](media/manage-apps.png)

> [!NOTE]
> La page Gérer les applications n’est pas encore disponible dans les déploiements Microsoft 365 Cloud de la communauté du secteur public High (GCCH) ou Department of Defense (DoD) de Teams.

## <a name="view-apps"></a>Afficher les applications

Vous pouvez afficher chaque application, y compris les informations suivantes sur chaque application.

![Capture d’écran de la page de détails des applications pour une application.](media/app-detail-page.jpg)

- **Nom** : nom de l’application. Sélectionnez le nom de l’application pour accéder à la page de détails de l’application pour afficher plus d’informations sur l’application. Cela inclut une description de l’application, qu’elle soit autorisée ou bloquée, version, stratégie de confidentialité, conditions d’utilisation, catégories qui s’appliquent à l’application, état de certification, fonctionnalités prises en charge et ID d’application.
- **Certification** : si l’application a été certifiée, vous verrez **Microsoft 365 attestation certifiée** ou **Publisher**. Sélectionnez le lien pour afficher les détails de certification de l’application. Si vous voyez `--`, nous n’avons pas d’informations de certification pour l’application. Pour en savoir plus sur les applications certifiées dans Teams, lisez [Microsoft 365 programme de certification des](/microsoft-365-app-certification/overview) applications.
- **Publisher** : nom de l’éditeur.
- **État de publication** : état de publication des applications personnalisées.
- **État** : état de l’application au niveau de l’organisation, qui peut être l’un des suivants :
  - **Autorisé** : l’application est disponible pour tous les utilisateurs de votre organisation.
  - **Bloqué** : l’application est bloquée et n’est pas disponible pour les utilisateurs de votre organisation.
  - **Bloqué par l’éditeur** : l’application est bloquée par l’éditeur et est masquée par défaut par les utilisateurs finaux. Après avoir configuré l’application à l’aide des conseils de l’éditeur, vous pouvez autoriser ou bloquer l’application pour la rendre disponible pour les utilisateurs finaux.
  - **Blocage à l’échelle de l’organisation** : l’application est bloquée dans les paramètres de l’application à l’échelle de l’organisation.
      Il est important de savoir que cette colonne représente l’état autorisé et bloqué des applications qui se trouvaient auparavant dans le volet **paramètres à l’échelle de l’organisation** . Vous affichez, bloquez et autorisez les applications à l’échelle de l’organisation sur la page **Gérer les applications** .
- **Licences** : indique si une application propose un abonnement SaaS (Software as a Service) à l’achat. Cette colonne s’applique uniquement aux applications tierces. Chaque application tierce aura l’une des valeurs suivantes :
  - **Achat** : l’application offre un abonnement SaaS et est disponible à l’achat.  
  - **Acheté** : l’application offre un abonnement SaaS et vous avez acheté des licences pour celle-ci.
  - **- -** : l’application n’offre pas d’abonnement SaaS.
- **Application personnalisée** : indique si l’application est une application personnalisée.
- **Autorisations** : indique si une application tierce ou personnalisée inscrite dans Azure Active Directory (Azure AD) dispose d’autorisations qui nécessitent un consentement. Vous verrez l’une des valeurs suivantes :
  - **Afficher les détails** : l’application dispose d’autorisations qui nécessitent un consentement avant que l’application puisse accéder aux données.
  - **- :** l’application n’a pas d’autorisations qui nécessitent un consentement.
- **Catégories** : catégories qui s’appliquent à l’application.
- **Version** : version de l’application.
- **L’administrateur peut s’installer dans les réunions** : indique si une application peut être installée par les administrateurs dans les réunions d’équipe. [Pour en savoir plus](teams-app-setup-policies.md#install-apps)

Pour afficher les informations souhaitées dans le tableau, sélectionnez **Modifier la colonne** dans le coin supérieur droit pour ajouter ou supprimer des colonnes à la table.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publier une application personnalisée dans l’App Store de votre organisation

Utilisez la page Gérer les applications pour publier des applications conçues spécifiquement pour votre organisation. Une fois que vous avez publié une application personnalisée, elle est disponible pour les utilisateurs de l’App Store de votre organisation. Il existe deux façons de publier une application personnalisée dans l’App Store de votre organisation. La façon dont vous utilisez dépend de la façon dont vous obtenez l’application.

- [Approuver une application personnalisée](#approve-a-custom-app) : utilisez cette méthode si le développeur envoie l’application directement à la page Gérer les applications à l’aide de l’API de soumission d’application Teams. Vous pouvez ensuite examiner et publier (ou rejeter) l’application directement à partir de la page de détails de l’application.
- [Télécharger un package d’application](#upload-an-app-package) : utilisez cette méthode si le développeur vous envoie le package d’application au format .zip. Vous publiez l’application en chargeant le package d’application.

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
2. Sélectionnez **Ajouter à l’équipe**.
3. Dans le volet **Ajouter à l’équipe** , recherchez l’équipe à laquelle vous souhaitez ajouter l’application, sélectionnez l’équipe, puis **sélectionnez Appliquer**.

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

## <a name="view-security-and-compliance-information-for-microsoft-365-certified-apps"></a>Afficher les informations de sécurité et de conformité pour les applications certifiées Microsoft 365

Lors de l’évaluation d’une application pour leur organisation, les administrateurs peuvent utiliser des courtiers de sécurité d’accès cloud (CASB) indépendants, tels que Microsoft Cloud App Security (MCAS), pour rechercher des informations sur la sécurité et les comportements d’une application. Le centre d’administration Teams inclut des informations de sécurité et de conformité à partir de MCAS pour Microsoft 365 applications certifiées afin que vous ayez plus d’informations sur le fait que l’application réponde ou non à vos besoins.

> [!NOTE]
> Cette fonctionnalité est disponible pour tous les administrateurs, que votre organisation dispose ou non d’une licence qui prend en charge MCAS.

Pour accéder à MCAS informations, procédez comme suit :

1. Dans le centre d’administration Teams, sélectionnez **Gérer les applications** sous **Teams applications**.
1. Sélectionnez **Certification** pour trier les applications et envoyer (push) toutes les applications certifiées Microsoft 365 en haut du tableau.
1. Choisissez une application certifiée Microsoft 365.
1. Sélectionnez l’onglet **Sécurité et conformité** .

![Capture d’écran de Teams’onglet Sécurité et conformité du Centre d’administration.](media/mcas.png)

Sous cet onglet, vous trouverez des informations sur la sécurité, la conformité et la protection des données. Vous pouvez également développer chaque liste déroulante pour obtenir plus de détails sur les fonctionnalités prises en charge pour l’application sélectionnée.

## <a name="related-topics"></a>Voir aussi

- [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
