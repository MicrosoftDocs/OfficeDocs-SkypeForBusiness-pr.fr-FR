---
title: Gérer vos applications dans le Centre d’administration Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
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
description: Découvrez comment gérer vos applications Teams sur la page Gérer les applications du Centre d’administration Microsoft Teams
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b3858044c52324cb52005c70c6f3afcf91e3f617
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574193"
---
# <a name="manage-your-apps-in-the-microsoft-teams-admin-center"></a>Gérer vos applications dans le Centre d’administration Microsoft Teams

En tant qu’administrateur, la page Gérer les applications du Centre d’administration Microsoft Teams est l’endroit où vous affichez et gérez toutes les applications Teams de votre organisation. Celui-ci vous permet d’afficher l’état et les propriétés des applications au niveau de l’organisation, d’approuver ou de télécharger de nouvelles applications personnalisées sur le magasin d’applications de votre organisation, de bloquer ou d’autoriser des applications au niveau de l’organisation, d’ajouter des applications aux équipes, d’acheter des services pour des applications tierces, d’afficher les autorisations demandées par les applications, d’accorder le consentement de l’administrateur aux applications et de gérer les paramètres des applications à l’échelle de l’organisation.

La page Gérer les applications vous permet d’afficher toutes les applications disponibles, et vous fournit les informations dont vous avez besoin pour décider des applications à autoriser ou bloquer dans votre organisation. Vous pouvez ensuite utiliser des stratégies [d’autorisation](teams-app-permission-policies.md)d’application, [](teams-app-setup-policies.md)des stratégies de configuration d’application et des stratégies et paramètres d’application [personnalisés](teams-custom-app-policies-and-settings.md) pour configurer l’expérience d’application pour des utilisateurs spécifiques de votre organisation.

Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**. Vous devez être un administrateur global ou un administrateur de service Teams pour accéder à la page.

> [!NOTE]
> La page Gérer les applications n’est pas encore disponible dans les déploiements Microsoft 365 Government Community Cloud (GCC) de Teams.

## <a name="view-apps"></a>Afficher les applications

Vous pouvez afficher chaque application, y compris les informations suivantes sur chaque application.

![Capture d’écran de la page Applications gérées](media/manage-apps.png)

- **Nom**: nom de l’application. Cliquez sur le nom de l’application pour consulter les détails de l’application. Ceci inclut une description de l’application (autorisée ou bloquée), sa version, sa politique de confidentialité, ses conditions d’utilisation, ses catégories qui s’appliquent à l’application, son état de certification, ses fonctionnalités pris en charge et son ID d’application. Voici un exemple :

  ![Capture d’écran de la page des détails des applications pour une application](media/manage-apps-app-details.png)
  
- **Certification**: Si l’application a été certifiée, vous verrez **Microsoft 365 certifié** **ou Publisher souhaitez vous en faire part.** Cliquez sur le lien pour afficher les détails de certification de l’application. Si vous voyez « **--** », nous n’avons pas d’informations de certification pour l’application. Pour en savoir plus sur les applications certifiées dans Teams, lisez le programme de certification des applications [Microsoft 365.](/teams-app-certification/all-apps)  
- **Publisher**: Nom de l’éditeur.
- **État de publication**: état de publication des applications personnalisées.
- **État**: État de l’application au niveau de l’organisation, qui peut être l’une des suivantes :

    - **Autorisé**: l’application est disponible pour tous les utilisateurs de votre organisation.
    
    - **Bloqué**: l’application est bloquée et n’est pas disponible pour les utilisateurs de votre organisation.
    
    - **Blocage à l’échelle de l’organisation**: l’application est bloquée dans les paramètres de l’application à l’échelle de l’organisation.
    
      Il est important de savoir que cette colonne représente l’état autorisé et bloqué des applications qui se bloquaient auparavant dans le volet **Paramètres** de l’organisation. Vous affichez, bloquez et autorisez les applications à l’échelle de l’organisation sur la page **Gérer les applications.** 
- **Licences**: indique si une application propose un abonnement SaaS (Software as a Service) à l’achat. Cette colonne s’applique uniquement aux applications tierces. Chaque application tierce a l’une des valeurs suivantes :
    - **Acheter maintenant**: l’application propose un abonnement SaaS et est disponible à l’achat.  
    - **Achat :** L’application propose un abonnement SaaS et vous avez acheté des licences pour celui-ci.
    - **- :** l’application ne propose pas d’abonnement SaaS.
- **Application personnalisée :** l’application personnalisée ou non.
- **Autorisations**: indique si une application tierce ou personnalisée inscrite dans Azure Active Directory (Azure AD) dispose d’autorisations qui ont besoin d’un consentement. Vous verrez l’une des valeurs suivantes :
    - **Afficher les détails**: L’application dispose d’autorisations qui nécessitent une autorisation pour que l’application puisse accéder aux données. 
    - **- :** l’application n’a pas d’autorisations qui ont besoin d’un consentement.
- **Catégories**: catégories qui s’appliquent à l’application.
- **Version :** version de l’application.

Pour voir les informations que vous  souhaitez dans le tableau, cliquez sur Modifier la colonne dans le coin supérieur droit pour ajouter ou supprimer des colonnes au tableau.

## <a name="publish-a-custom-app-to-your-organizations-app-store"></a>Publier une application personnalisée sur le magasin d’applications de votre organisation

Utilisez la page Gérer les applications pour publier des applications spécialement conçues pour votre organisation. Après avoir publié une application personnalisée, elle est disponible pour les utilisateurs dans le magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée sur le magasin d’applications de votre organisation. La façon dont vous utilisez l’application dépend de la façon dont vous obtenez l’application.

- [Approuver une application personnalisée](#approve-a-custom-app): utilisez cette méthode si le développeur envoie l’application directement à la page Gérer les applications à l’aide de l’API De soumission d’application Teams. Vous pouvez ensuite consulter et publier (ou refuser) l’application directement à partir de la page des détails de l’application.
- [Télécharger un package d’application](#upload-an-app-package): utilisez cette méthode si le développeur vous envoie le package d’application au format .zip. Vous publiez l’application en chargeant le package d’application.

###  <a name="approve-a-custom-app"></a>Approuver une application personnalisée

Le widget **Approbations en** attente dans la page Gérer les applications vous avertit lorsqu’un développeur envoie une application à l’aide de l’API Soumission d’application Teams. Une application nouvellement envoyée est répertoriée avec l’état **de publication** **Soumis** et **le statut** **Bloqué.** Allez sur la page des détails de l’application pour voir plus d’informations sur l’application, puis pour la publier, définissez l’état de **publication** **sur Publier.**

Vous êtes également averti lorsqu’un développeur envoie une mise à jour à une application personnalisée. Vous pouvez ensuite consulter et publier (ou refuser) la mise à jour sur la page des détails de l’application. Toutes les stratégies d’autorisation d’application et stratégies de configuration d’application demeurent appliquées pour l’application mise à jour.

Pour en savoir plus, [consultez Publier une application personnalisée envoyée via l’API Soumission d’application Teams.](submit-approve-custom-apps.md)

### <a name="upload-an-app-package"></a>Télécharger un package d’application

Le développeur crée un package d’application Teams à l’aide [de Teams App Studio,](/microsoftteams/platform/get-started/get-started-app-studio)puis vous l’envoie au format .zip. Lorsque vous avez le package d’application, vous pouvez le télécharger dans le magasin d’applications de votre organisation.

Pour télécharger une nouvelle application personnalisée, **sélectionnez Télécharger** pour télécharger le package d’application. L’application n’est pas mise en évidence une fois téléchargée. Vous devrez donc effectuer une recherche dans la liste des applications de la page Gérer les applications pour la trouver.

Pour mettre à jour une application une fois qu’elle a été téléchargée, dans la liste des applications de la page Gérer les applications, cliquez sur le nom de l’application, puis sur Mettre **à jour.** Cette procédure remplace l’application existante, et toutes les stratégies d’autorisation d’application et stratégies de configuration de l’application restent appliquées pour l’application mise à jour.

Pour plus d’informations, [voir Publier une application personnalisée en téléchargeant un package d’application.](upload-custom-apps.md)

## <a name="allow-and-block-apps"></a>Autoriser et bloquer des applications

La page Gérer les applications est l’endroit où vous autorisez ou bloquez des applications individuelles au niveau de l’organisation. Il affiche chaque application disponible et son état actuel au niveau de l’organisation. (Le blocage et l’accès aux applications au niveau de l’organisation ont été déplacés du volet Des **paramètres** d’application à l’échelle de l’organisation vers cet espace.)

Pour autoriser ou bloquer une application, sélectionnez-la, puis cliquez **sur Autoriser** ou **Bloquer.** Lorsque vous bloquez une application, toutes les interactions avec cette application sont désactivées et l’application n’apparaît pas dans Teams pour les utilisateurs de votre organisation.

Lorsque vous bloquez ou autorisez une application sur la page Gérer les applications, cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation.  Lorsque vous bloquez ou autorisez une application dans une stratégie d’autorisation d’application Teams, elle est bloquée ou autorisée pour les utilisateurs affectés à cette stratégie. Pour qu’un utilisateur puisse installer et interagir avec une application, vous devez autoriser l’application au niveau de l’organisation sur la page Gérer les applications et dans la stratégie d’autorisation d’application affectée à l’utilisateur.

 > [!NOTE]
 > Pour désinstaller une application, cliquez dessus avec le bouton droit, puis cliquez sur **Désinstaller** ou utilisez le **menu** Autres applications sur le côté gauche.

## <a name="add-an-app-to-a-team"></a>Ajouter une application à une équipe

Vous utilisez le **bouton Ajouter à une équipe** pour installer une application à une équipe. N’oubliez pas que cette application s’agit uniquement des applications qui peuvent être installées dans une étendue d’équipe. Le **bouton Ajouter à l’équipe** n’est pas disponible pour les applications qui ne peuvent être installées que dans l’étendue personnelle.

![Capture d’écran du bouton Ajouter à l’équipe](media/manage-apps-add-app-team.png)

1. Recherchez l’application de votre choix, puis sélectionnez-la en cliquant à gauche du nom de l’application.
2. Sélectionnez **Ajouter à l’équipe.**
3. Dans le **volet Ajouter à l’équipe,** recherchez l’équipe à qui vous voulez ajouter l’application, sélectionnez l’équipe, puis sélectionnez **Appliquer.**

## <a name="customize-an-app-in-preview"></a>Personnaliser une application (en prévisualisation)

Vous pouvez désormais personnaliser une application afin d’inclure une apparence spécifique en fonction des besoins de votre organisation. Consultez [Personnaliser les applications dans Teams.](customize-apps.md)

## <a name="purchase-services-for-third-party-apps"></a>Acheter des services pour les applications tierces

Vous pouvez rechercher et acheter des licences pour les services offerts par des applications tierces pour les utilisateurs de votre organisation directement à partir de la page Gérer les applications. La **colonne Licences** du tableau indique si une application propose un abonnement SaaS payant. Cliquez **sur Acheter maintenant** pour afficher les plans et les informations tarifaires, et acheter des licences pour vos utilisateurs. Pour plus d’informations, voir Acheter des services pour les applications tierces [Teams dans le Centre d’administration Microsoft Teams.](purchase-third-party-apps.md)

## <a name="grant-admin-consent-to-apps"></a>Accorder l’autorisation d’accès des administrateurs aux applications

Vous pouvez consulter et accorder votre consentement aux applications qui demandent des autorisations au nom de tous les utilisateurs de votre organisation. Ainsi, les utilisateurs n’ont pas à passer en revue et à accepter les autorisations demandées par l’application lorsqu’ils démarrent l’application. La **colonne Autorisations** indique si une application dispose d’autorisations qui ont besoin d’un consentement. Vous verrez un lien Afficher les **détails** pour chaque application enregistrée dans Azure AD qui dispose d’autorisations qui ont besoin d’un consentement. Pour en savoir plus, consultez [les autorisations d’application et accordez l’administrateur dans le Centre d’administration Microsoft Teams.](app-permissions-admin-center.md)

## <a name="view-resource-specific-consent-permissions"></a>Afficher les autorisations de consentement spécifiques aux ressources

Les autorisations de consentement spécifique aux ressources autorisent les propriétaires d’équipe à accorder leur consentement pour qu’une application accède aux données d’une équipe et les modifie. Les autorisations RSC sont précises et spécifiques à Teams qui définissent ce qu’une application peut faire dans une équipe spécifique. Vous pouvez afficher les autorisations RSC sous l’onglet **Autorisations** de la page des détails de l’application pour une application. Pour en savoir plus, consultez [les autorisations d’application et accordez l’administrateur dans le Centre d’administration Microsoft Teams.](app-permissions-admin-center.md)

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres des applications à l’échelle de l’organisation

Utilisez les paramètres d’application à l’échelle de l’organisation pour contrôler si les utilisateurs peuvent installer des applications tierces et si les utilisateurs peuvent télécharger ou interagir avec des applications personnalisées dans votre organisation. Les paramètres de l’application à l’échelle de l’organisation contrôlent le comportement de tous les utilisateurs et remplacent les autres stratégies d’autorisation d’application attribuées à des utilisateurs. Vous pouvez les utiliser pour contrôler des applications malveillantes ou problématiques.

> [!NOTE]
> Pour découvrir comment utiliser les paramètres d’application à l’échelle de l’organisation dans les déploiements Microsoft 365 Government - GCC de Teams, voir Gérer les stratégies d’autorisation d’application [dans Teams.](teams-app-permission-policies.md)

1. Dans la page Gérer les applications, sélectionnez **Paramètres de l’application à l’échelle de l’organisation.** Vous pouvez ensuite configurer les paramètres voulus dans le panneau.

    ![Capture d’écran des paramètres de l’application à l’échelle de l’organisation](media/manage-apps-org-wide-app-settings.png)
    
2. Sous **Applications tierces**, désactiver ou activer ces paramètres pour contrôler l’accès à des applications tierces :

    - **Autoriser les applications tierces** : cette commande contrôle si les utilisateurs peuvent utiliser des applications tierces. Si vous désactiver ce paramètre, vos utilisateurs ne pourront pas installer ou utiliser des applications tierces et l’état de ces applications s’affiche comme bloqué à l’échelle de l’organisation dans le tableau. 

        > [!NOTE]
        > Lorsque **l’autoriser est** désactivé, les sites web sortants sont [désactivés,](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors) ce qui signifie que les utilisateurs ne peuvent pas les créer. Lorsque ce paramètre est activé, les sites web sortants sont activés pour tous les utilisateurs et vous pouvez les contrôler au niveau de l’utilisateur en permettant ou en bloquant l’application Web de groupe sortante via des stratégies d’autorisation [d’application.](teams-app-permission-policies.md) <br><br>Notez que si [](teams-app-permission-policies.md) vous avez des stratégies  d’autorisation d’application existantes pour les applications **Microsoft** qui utilisent le paramètre Autoriser des applications spécifiques et bloquez tous les autres paramètres, et que vous voulez activer les sites web sortants pour les utilisateurs, ajoutez l’application Web de groupe sortant à la liste.
    - **Autoriser toute nouvelle application tierce publiée sur le magasin par défaut** : cette option contrôle la publication automatique des nouvelles applications tierces publiées dans le magasin d’applications Teams dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

3. Sous **Applications personnalisées,** désactiver ou activer **l’application Autoriser l’interaction avec les applications personnalisées.** Ce paramètre contrôle si les utilisateurs peuvent interagir avec les applications personnalisées. Pour plus d’informations, consultez [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-custom-app-policies-and-settings.md).
4. Cliquez sur **Enregistrer** pour que les paramètres de l’application à l’échelle de l’organisation prennent effet.

## <a name="related-topics"></a>Sujets associés

- [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)