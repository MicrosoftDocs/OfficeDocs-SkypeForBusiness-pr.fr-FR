---
title: Afficher les autorisations d’application et accorder une autorisation d’administrateur dans le centre d’administration Microsoft teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment afficher les autorisations demandées par les applications et accorder une autorisation d’administration aux applications sur la page gérer les applications du centre d’administration Microsoft Teams.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 104dab27af75d346af990369ee78fc2fb1f0a77d
ms.sourcegitcommit: fd7d5ba09ef30cf4594e352c36f62b950e0e41a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48336841"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Afficher les autorisations d’application et accorder une autorisation d’administrateur dans le centre d’administration Microsoft teams

La page [gérer les applications](manage-apps.md) dans le centre d’administration Microsoft teams vous permet d’afficher et de gérer toutes les applications teams pour votre organisation. Par exemple, vous pouvez voir l’état de niveau de l’organisation et les propriétés des applications, approuver ou télécharger de nouvelles applications personnalisées dans le magasin d’applications de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation, et gérer les paramètres de l’application à l’échelle de l’organisation.

Vous pouvez également accorder une autorisation d’administrateur à l’échelle de l’organisation aux applications qui demandent des autorisations pour accéder aux données et afficher les autorisations d’autorisation spécifiques aux ressources pour les applications.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Accorder l’autorisation d’administrateur à l’échelle de l’organisation à une application

Si vous êtes un administrateur général, vous pouvez passer en revue et accorder une autorisation aux applications demandant des autorisations pour le compte de tous les utilisateurs de votre organisation. Vous procédez ainsi pour que les utilisateurs n’aient pas à passer en revue et à accepter les autorisations requises par l’application au démarrage de l’application. De plus, en fonction des [paramètres de consentement](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent) de l’utilisateur dans Azure Active Directory (Azure AD), certains utilisateurs peuvent ne pas être autorisés à accorder une autorisation aux applications qui accèdent à des données d’entreprise.

Les autorisations requises par les applications incluent la possibilité de lire les informations stockées dans une équipe, de lire le profil d’un utilisateur et d’envoyer un message électronique de la part des utilisateurs. Pour en savoir plus, voir [autorisations et autorisation dans le point de terminaison de la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent). 

La colonne **autorisations** indique si une application dispose d’autorisations qui nécessitent une autorisation. Vous verrez un lien d' **affichage des détails** pour chaque application inscrite dans Azure ad et disposant d’autorisations nécessaires. Gardez à l’esprit que ceci s’applique uniquement aux applications tierces et personnalisées et. Ce lien ne sera pas visible ou vous devrez accorder l’autorisation d’administrateur pour les applications publiées par Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Capture d’écran de la colonne autorisations dans la page gérer les applications":::

Pour accorder l’autorisation à l’échelle de l’organisation à une application, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps.
2. Effectuez l’une des opérations suivantes :
    - Recherchez l’application souhaitée, cliquez sur son nom pour accéder à la page Détails de l’application, puis sélectionnez l’onglet **autorisations** .
    - Triez la colonne **autorisations** dans l’ordre décroissant pour trouver l’application, puis sélectionnez **afficher les détails**. Cette opération vous permet d’accéder à l’onglet **autorisations** de la page Détails de l’application.

3. Sous **autorisations à l’échelle**de l’organisation, sélectionnez **vérifier les autorisations et l’autorisation**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Capture d’écran des autorisations à l’échelle de l’organisation sous l’onglet Autorisations pour une application":::

    Pour cela, vous devez être un administrateur général. Cette option n’est pas disponible pour les administrateurs de services d’équipes.

4. Dans l’onglet **autorisations** , passez en revue les autorisations requises par l’application.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Capture d’écran des autorisations demandées par une application":::

    > [!IMPORTANT]
    > L’octroi d’une autorisation à l’échelle de l’organisation à une application permet à l’application d’accéder aux données de votre organisation. Passez en revue les autorisations requises par l’application avant de lui accorder votre consentement.
5. Si vous acceptez les autorisations requises par l’application, cliquez sur **accepter** pour accorder l’autorisation. Une bannière apparaît temporairement en haut de la page pour vous informer que les autorisations demandées ont été accordées pour l’application. L’application a désormais accès aux ressources spécifiées pour tous les utilisateurs de votre organisation et personne d’autre ne sera invité à vérifier les autorisations.

Après avoir accepté les autorisations, un message s’affiche sous les **autorisations** à l’échelle de l’organisation dans la page Détails de l’application pour vous signaler que l’autorisation a été accordée. Pour afficher des détails sur les autorisations de l’application, cliquez sur le lien **Azure Active Directory** pour accéder à la page de l’application dans le portail Azure ad.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Capture d’écran du message affiché lors de la réception d’une autorisation":::

Si les utilisateurs de votre organisation ont l’autorisation d’accorder une autorisation et si un ou plusieurs utilisateurs vous ont accordé un consentement pour une application particulière, vous verrez également le même message vous informant que le consentement a été accordé et le lien Azure Active Directory vers la page de l’application dans le portail Azure AD.

> [!NOTE]
> Même si l’option d' **examen des autorisations et de consentement** n’est pas disponible pour les administrateurs de service teams et qu’ils ne peuvent pas accorder de consentement d’administrateur à l’échelle de l’organisation aux applications, les administrateurs de service teams peuvent afficher le contenu sous l’onglet **autorisations** pour une application. Par exemple, un administrateur de service teams peut cliquer sur le lien **Azure Active Directory** pour afficher les détails des autorisations de l’application dans le portail Azure ad. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Afficher les autorisations de consentement spécifiques aux ressources d’une application

Autorisations RSC permettre aux propriétaires d’équipe d’accorder l’autorisation d’accès et de modification des données d’une équipe à une application. Les autorisations RSC s’appliquent aux autorisations spécifiques aux équipes qui définissent ce qu’une application peut faire au sein d’une équipe spécifique. Les exemples d’autorisations RSC incluent la possibilité de créer et de supprimer des canaux, d’obtenir les paramètres d’une équipe et de créer et de supprimer des onglets de canal. 

Les autorisations RSC sont définies dans le manifeste de l’application, et non dans Azure AD. Vous accordez l’autorisation aux autorisations RSC lorsque vous ajoutez l’application à une équipe. Pour en savoir plus, voir [autorisation spécifique aux ressources (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

Les administrateurs généraux et l’administrateur de service teams peuvent afficher les autorisations RSC pour une application sous l’onglet **autorisations** de la page Détails de l’application. 

Pour afficher les autorisations RSC pour une application, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps.
2. Recherchez l’application souhaitée, cliquez sur son nom pour accéder à la page Détails de l’application, puis sélectionnez l’onglet **autorisations** .
3. Sous **autorisations de consentement spécifiques de ressources Microsoft Graph (RSC)**, passez en revue les autorisations RSC requises par l’application.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Capture d’écran des autorisations RSC pour une application":::

## <a name="known-issues"></a>Problèmes connus

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Le lien « Afficher les détails » n’apparaît pas dans la colonne autorisations pour certaines applications tierces demandant des autorisations

Pour l’instant, la possibilité de réviser les autorisations et de consentement n’est pas disponible pour toutes les applications tierces inscrites dans Azure AD qui demandent des autorisations. À la place du lien **afficher les détails** , vous verrez **--** dans la colonne **autorisations** . Nous travaillons avec les éditeurs de logiciels indépendants pour activer cette fonctionnalité pour leurs applications.

## <a name="related-topics"></a>Sujets associés

- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)
- [Autorisations et consentement dans le point de terminaison de la plateforme d’identité Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)
- [Autorisation spécifique aux ressources dans teams](resource-specific-consent.md)
- [Autorisation spécifique aux ressources (RSC)](https://docs.microsoft.com/microsoftteams/platform/graph-api/rsc/resource-specific-consent)


