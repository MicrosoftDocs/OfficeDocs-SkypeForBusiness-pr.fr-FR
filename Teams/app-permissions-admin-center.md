---
title: Afficher les autorisations des applications et accorder le consentement administrateur dans le Centre d’administration Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
search.appverid: MET150
description: Découvrez comment afficher les autorisations demandées par les applications et accorder le consentement administrateur aux applications dans la page Gérer les applications du Centre d’administration Microsoft Teams.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ba381d5d6806c1abd7a2766228ff74f843b156a
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837514"
---
# <a name="view-app-permissions-and-grant-admin-consent-in-the-microsoft-teams-admin-center"></a>Afficher les autorisations des applications et accorder le consentement administrateur dans le Centre d’administration Microsoft Teams

Les administrateurs affichent et gèrent toutes les applications Teams à partir de la page Gérer les applications dans le Centre d’administration Teams. Vous pouvez gérer les applications personnalisées créées au sein de votre organisation et disponibles uniquement pour vos utilisateurs finaux et gérer les applications tierces disponibles sur l’App Store Teams. Par exemple, vous pouvez voir l’état et les propriétés au niveau de l’organisation des applications, approuver ou charger de nouvelles applications personnalisées dans l’App Store de votre organisation, autoriser des applications au niveau de l’organisation ou pour des utilisateurs finaux individuels.

Ici, vous pouvez également accorder un consentement administrateur à l’échelle de l’organisation aux applications qui demandent des autorisations pour accéder aux données et afficher les autorisations de consentement spécifiques aux ressources pour les applications.

## <a name="grant-org-wide-admin-consent-to-an-app"></a>Accorder le consentement de l’administrateur à l’échelle de l’organisation pour une application

Si vous êtes administrateur général, vous pouvez examiner et accorder le consentement aux applications qui demandent des autorisations pour le compte de tous les utilisateurs de votre organisation. Vous le faites pour que les utilisateurs n’aient pas à examiner et à accepter les autorisations demandées par l’application lorsqu’ils démarrent l’application. En outre, selon les [paramètres de consentement](/azure/active-directory/manage-apps/configure-user-consent) de l’utilisateur dans Azure Active Directory (Azure AD), certains utilisateurs peuvent ne pas être autorisés à accorder le consentement aux applications qui accèdent aux données de l’entreprise.

Parmi les exemples d’autorisations demandées par les applications, citons la possibilité de lire les informations stockées dans une équipe, de lire le profil d’un utilisateur et d’envoyer un e-mail au nom des utilisateurs. Pour en savoir plus, consultez [Autorisations et consentement dans le point de terminaison Plateforme d’identités Microsoft pour développeurs](/azure/active-directory/develop/v2-permissions-and-consent).

La colonne **Autorisations** indique si une application dispose d’autorisations qui nécessitent un consentement. Vous verrez un lien **Afficher les détails** pour chaque application inscrite dans Azure Active Directory disposant d’autorisations qui nécessitent un consentement. Gardez à l’esprit que cela s’applique uniquement aux applications personnalisées et tierces. Le lien n’est pas disponible pour les applications fournies par Microsoft. En outre, les administrateurs n’ont pas besoin d’accorder le consentement pour ces applications.

Pour accorder un consentement à l’échelle de l’organisation à une application, procédez comme suit :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > [Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps).

1. Effectuez l’une des opérations suivantes :
    * Recherchez l’application souhaitée, sélectionnez le nom de l’application pour accéder à la page des détails de l’application, puis sélectionnez l’onglet **Autorisations** .
    * Triez la colonne **Autorisations** dans l’ordre décroissant pour trouver l’application, puis sélectionnez **Afficher les détails**. Cela vous permet d’accéder à l’onglet **Autorisations** de la page de détails de l’application.

1. Sous **Autorisations à l’échelle de l’organisation**, sélectionnez **Vérifier les autorisations et le consentement**.

    :::image type="content" source="media/app-perm-admin-center-org-wide.png" alt-text="Capture d’écran des autorisations à l’échelle de l’organisation sous l’onglet Autorisations d’une application":::

    Pour ce faire, vous devez être un administrateur général. Cette option n’est pas disponible pour les administrateurs du service Teams.

1. Sous l’onglet **Autorisations**, passez en revue les autorisations demandées par l’application.

    :::image type="content" source="media/app-perm-admin-center-org-wide-permissions.png" alt-text="Capture d’écran des autorisations demandées par une application":::

    > [!IMPORTANT]
    > L’octroi d’un consentement à l’échelle de l’organisation à une application permet à l’application d’accéder aux données de votre organisation. Examinez attentivement les autorisations demandées par l’application avant d’accorder votre consentement.

1. Si vous acceptez les autorisations demandées par l’application, sélectionnez **Accepter** pour accorder le consentement. Une bannière s’affiche temporairement en haut de la page pour vous informer que les autorisations demandées ont été accordées pour l’application. L’application a désormais accès aux ressources spécifiées pour tous les utilisateurs de votre organisation et personne d’autre ne sera invité à passer en revue les autorisations.

Une fois les autorisations acceptées, un message s’affiche sous **Autorisations à l’échelle de l’organisation** sur la page des détails de l’application pour vous informer que le consentement a été accordé. Pour afficher des détails sur les autorisations de l’application, sélectionnez le lien **Azure Active Directory** pour accéder à la page de l’application dans le portail Azure AD.

:::image type="content" source="media/app-perm-admin-center-org-wide-accepted-new.png" alt-text="Capture d’écran du message affiché lorsque le consentement est accordé":::

Si les utilisateurs de votre organisation sont autorisés à accorder le consentement et si un ou plusieurs utilisateurs ont accordé le consentement à une application particulière, vous verrez également le même message pour vous informer que le consentement a été accordé et le lien Azure Active Directory vers la page de l’application dans le portail Azure Active Directory.

> [!NOTE]
> Bien que l’option **Examiner les autorisations et le consentement** ne soit pas disponible pour les administrateurs de service Teams et qu’ils ne puissent pas accorder le consentement administrateur à l’échelle de l’organisation aux applications, les administrateurs de service Teams peuvent afficher le contenu sous l’onglet **Autorisations** d’une application. Par exemple, un administrateur de service Teams peut cliquer sur le lien **Azure Active Directory** pour afficher les détails des autorisations d’application dans le portail Azure Active Directory.

## <a name="view-resource-specific-consent-permissions-of-an-app"></a>Afficher les autorisations de consentement spécifiques aux ressources d’une application

Les autorisations RSC permettent aux propriétaires d’équipe d’accorder un consentement pour qu’une application accède aux données d’une équipe et les modifie. Les autorisations RSC sont des autorisations granulaires spécifiques à Teams qui définissent ce qu’une application peut faire dans une équipe spécifique. Parmi les exemples d’autorisations RSC, citons la possibilité de créer et de supprimer des canaux, d’obtenir les paramètres d’une équipe et de créer et de supprimer des onglets de canal.

Les autorisations RSC sont définies dans le manifeste de l’application et non dans Azure Active Directory. Vous accordez le consentement aux autorisations RSC lorsque vous ajoutez l’application à une équipe. Pour plus d’informations, consultez [le consentement spécifique à la ressource (RSC).](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)

Les administrateurs généraux et l’administrateur du service Teams peuvent afficher les autorisations RSC pour une application sous l’onglet **Autorisations** de la page de détails de l’application.

Pour afficher les autorisations RSC pour une application, procédez comme suit :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
1. Recherchez l’application souhaitée, sélectionnez le nom de l’application pour accéder à la page des détails de l’application, puis sélectionnez l’onglet **Autorisations** .
1. Sous **autorisations RSC (Microsoft Graph Resource-specific Consent),** passez en revue les autorisations RSC demandées par l’application.

    :::image type="content" source="media/app-perm-admin-center-rsc-new.png" alt-text="Capture d’écran des autorisations RSC pour une application":::

## <a name="known-issues"></a>Problèmes connus

### <a name="the-view-details-link-isnt-displayed-in-the-permissions-column-for-some-third-party-apps-that-request-permissions"></a>Le lien « Afficher les détails » n’est pas affiché dans la colonne Autorisations pour certaines applications tierces qui demandent des autorisations.

La possibilité d’examiner des autorisations et d’accorder un consentement n’est pas disponible pour toutes les applications tierces. En règle générale, les applications tierces sont inscrites dans Azure Active Directory lorsque les applications demandent des autorisations. Au lieu du lien **Afficher les détails**, vous le verrez `--` dans la colonne **Autorisations** .

## <a name="related-articles"></a>Articles connexes

* Vous gérez les applications pour votre organisation dans les [applications Teams au sein du centre d’administration Microsoft Teams](manage-apps.md).
* [Autorisations et consentement dans le point de terminaison Plateforme d’identités Microsoft pour développeurs](/azure/active-directory/develop/v2-permissions-and-consent)
* [Consentement spécifique aux ressources dans Teams](resource-specific-consent.md)
* [Consentement spécifique à la ressource (RSC)](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Naviguer dans le cycle de vie de l’application Teams](https://aka.ms/PR132) (session Ignite 2020)
