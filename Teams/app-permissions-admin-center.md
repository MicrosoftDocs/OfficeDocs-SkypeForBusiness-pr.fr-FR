---
title: Afficher les autorisations des applications et accorder le consentement de l’administrateur dans le Microsoft Teams’administration
author: cichur
ms.author: v-cichur
ms.reviewer: vaibhava
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment afficher les autorisations demandées par les applications et accorder à l’administrateur le consentement des applications sur la page Gérer les applications du Microsoft Teams d’administration.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae8a74e03b56b841fed8cce3558fad96fe5c8680
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733344"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Afficher les autorisations des applications et accorder le consentement de l’administrateur dans le Microsoft Teams’administration

La page [Gérer les](manage-apps.md) applications du Centre Microsoft Teams d’administration est l’endroit où vous affichez et gérez toutes Teams applications pour votre organisation. Par exemple, vous pouvez voir l’état et les propriétés des applications au niveau de l’organisation, approuver ou télécharger de nouvelles applications personnalisées sur le magasin d’applications de votre organisation, bloquer ou autoriser des applications au niveau de l’organisation, et gérer les paramètres des applications à l’échelle de l’organisation.

Ici, vous pouvez également accorder à l’administrateur de l’organisation l’autorisation d’accéder aux données et d’afficher des autorisations d’autorisation spécifique aux ressources pour les applications.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Accorder l’accord de l’administrateur à l’échelle de l’organisation à une application

Si vous êtes un administrateur global, vous pouvez consulter et accorder votre consentement aux applications qui demandent des autorisations au nom de tous les utilisateurs de votre organisation. Ainsi, les utilisateurs n’ont pas à passer en revue et à accepter les autorisations demandées par l’application lorsqu’ils démarrent l’application. En outre, en fonction des paramètres de consentement de l’utilisateur dans Azure Active Directory (Azure AD), certains [utilisateurs](/azure/active-directory/manage-apps/configure-user-consent) peuvent ne pas être autorisés à accorder le consentement aux applications qui accèdent aux données de l’entreprise.

Parmi les exemples d’autorisations demandées par les applications figurent la possibilité de lire les informations stockées dans une équipe, de lire le profil d’un utilisateur et d’envoyer un courrier électronique au nom des utilisateurs. Pour en savoir plus, [consultez Autorisations et consentement dans le Plateforme d’identités Microsoft terminaison.](/azure/active-directory/develop/v2-permissions-and-consent) 

La **colonne Autorisations** indique si une application dispose d’autorisations qui ont besoin d’un consentement. Vous verrez un lien Afficher les **détails** pour chaque application enregistrée dans Azure AD qui dispose d’autorisations qui ont besoin d’un consentement. N’oubliez pas que cette règle ne s’applique qu’aux applications personnalisées et tierces. Vous ne verrez pas ce lien ou n’aurez pas besoin d’accorder l’accord de l’administrateur pour les applications publiées par Microsoft.

:::image type="content" source="media/app-perm-admin-center-permissions-column.png" alt-text="Capture d’écran de la colonne Autorisations sur la page Gérer les applications.":::

Pour accorder le consentement à l’échelle de l’organisation à une application, suivez ces étapes :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Effectuez l’une des opérations suivantes :
    - Recherchez l’application de votre choix, cliquez sur son nom pour consulter la page des détails de l’application, puis sélectionnez **l’onglet Autorisations.**
    - T **triez la colonne Autorisations** dans l’ordre décroit pour rechercher l’application, puis sélectionnez **Afficher les détails.** Vous êtes alors autorisé à vous rendre sur **l’onglet Autorisations** de la page des détails de l’application.

3. Sous **Autorisations à l’échelle de l’organisation,** **sélectionnez Examiner les autorisations et le consentement.**

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Capture d’écran des autorisations à l’échelle de l’organisation sous l’onglet Autorisations d’une application.":::

    Pour ce faire, vous devez être un administrateur global. Cette option n’est pas disponible Teams administrateurs de services.

4. Sous **l’onglet Autorisations,** examinez les autorisations demandées par l’application.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Capture d’écran des autorisations demandées par une application.":::

    > [!IMPORTANT]
    > L’octroi d’un consentement à l’échelle de l’organisation à une application permet à l’application d’accéder aux données de votre organisation. Examinez attentivement les autorisations demandées par l’application avant d’accorder votre accord.
5. Si vous êtes d’accord avec les autorisations demandées par l’application, cliquez sur **Accepter** pour accorder votre accord. Une bannière apparaît temporairement en haut de la page pour vous faire savoir que les autorisations demandées ont été accordées à l’application. L’application a désormais accès aux ressources spécifiées pour tous les utilisateurs de votre organisation et personne d’autre n’est invité à examiner les autorisations.

Une fois les autorisations acceptées, un message s’agit de la page des détails de l’application qui s’insérez sous **Autorisations** à l’échelle de l’organisation pour vous faire savoir que le consentement a été accordé. Pour afficher des détails sur les autorisations de l’application, cliquez sur Azure Active Directory lien vers la page de l’application dans le portail Azure AD. 

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted.png" alt-text="Capture d’écran du message affiché lors du consentement accordé.":::

Si les utilisateurs de votre organisation sont autorisés à accorder le consentement et si un ou plusieurs utilisateurs ont accordé leur consentement à une application particulière, vous verrez également le même message pour vous faire savoir que le consentement a été accordé et le lien Azure Active Directory vers la page de l’application dans le portail Azure AD.

> [!NOTE]
> Bien que l’option Examiner les **autorisations** et le consentement ne soit pas disponible pour les administrateurs de services Teams et ne peuvent pas accorder de consentement à l’échelle de l’organisation à des applications, les administrateurs de service Teams peuvent afficher le contenu sous l’onglet **Autorisations** d’une application. Par exemple, un administrateur Teams service  peut cliquer sur le Azure Active Directory de connexion pour afficher les détails des autorisations d’application dans le portail Azure AD. 

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Afficher les autorisations de consentement spécifiques aux ressources d’une application

Les autorisations RSC autorisent les propriétaires d’équipe à autoriser une application à accéder aux données d’une équipe et à les modifier. Les autorisations RSC sont précises Teams autorisations spécifiques qui définissent ce qu’une application peut faire dans une équipe spécifique. Parmi les exemples d’autorisations RSC, citons la possibilité de créer et supprimer des canaux, d’obtenir les paramètres d’une équipe, et de créer et supprimer des onglets de canal. 

Les autorisations RSC sont définies dans le manifeste de l’application et non dans Azure AD. Vous accordez l’accord aux autorisations RSC lorsque vous ajoutez l’application à une équipe. Pour en savoir plus, consultez le consentement spécifique [à la ressource.](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Les administrateurs globaux et Teams de service peuvent afficher les autorisations RSC pour une application sous l’onglet **Autorisations** de la page des détails de l’application. 

Pour afficher les autorisations RSC d’une application, suivez ces étapes :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Recherchez l’application de votre choix, cliquez sur son nom pour consulter la page des détails de l’application, puis sélectionnez **l’onglet Autorisations.**
3. Sous **Microsoft Graph autorisations** de consentement spécifique aux ressources, examinez les autorisations RSC demandées par l’application.

    :::image type="content" source="media/app-perm-admin-center-rsc.png" alt-text="Capture d’écran des autorisations RSC pour une application.":::

## <a name="known-issues"></a>Problèmes connus

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Le lien « Afficher les détails » n’est pas affiché dans la colonne Autorisations pour certaines applications tierces qui demandent des autorisations

Actuellement, la possibilité de passer en revue les autorisations et d’accorder le consentement n’est pas disponible pour toutes les applications tierces inscrites dans Azure AD qui demandent des autorisations. Au lieu du lien **Afficher les détails,** vous verrez dans **--** la colonne **Autorisations.** Nous travaillons avec des téléviseurs pour activer cette fonctionnalité pour leurs applications.

## <a name="related-topics"></a>Sujets associés

- [Gérer vos applications dans le Centre Microsoft Teams’administration](manage-apps.md)
- [Autorisations et consentement dans le point de terminaison Plateforme d’identités Microsoft’utilisateur](/azure/active-directory/develop/v2-permissions-and-consent)
- [Consentement spécifique à une ressource dans Teams](resource-specific-consent.md)
- [Consentement spécifique à une ressource](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Navigation dans le cycle Teams de l’application](https://aka.ms/PR132) (session Ignite 2020)