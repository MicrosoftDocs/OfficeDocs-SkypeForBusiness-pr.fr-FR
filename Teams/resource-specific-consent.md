---
title: Consentement spécifique à la ressource dans Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
ms.subservice: teams-apps
ms.date: 09/26/2022
search.appverid: MET150
description: Découvrez les paramètres que vous devez configurer pour contrôler si les propriétaires d’équipes de votre organisation peuvent donner leur consentement aux applications.
ms.localizationpriority: high
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb7e4a4487a5411386978fb91a70c485bfa0ddc6
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912593"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentement spécifique à la ressource dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le consentement spécifique aux ressources (RSC) est une intégration Microsoft Teams et Microsoft API Graph qui permet aux applications d’utiliser des points de terminaison d’API pour gérer des ressources spécifiques d’une équipe au sein de votre organisation. Les autorisations RSC permettent aux propriétaires d’équipe d’accorder le consentement à une application pour accéder aux données d’une équipe et les modifier. Le consentement spécifique aux ressources dans Microsoft Teams permet aux propriétaires d’équipe de donner leur consentement aux applications pour accéder aux données d’équipe. Ces accès incluent par exemple la possibilité de lire des messages de canal, de créer et de supprimer des canaux, ainsi que de créer et supprimer des onglets de canal.

En tant qu’administrateur, vous contrôlez si les propriétaires d’équipe de votre organisation peuvent donner leur consentement via les paramètres que vous configurez à l’aide du module PowerShell Azure Active Directory (Azure AD) ou du Portail Azure et du Centre d’administration Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Définir si les propriétaires d’équipe peuvent donner leur consentement aux applications

Voici les paramètres que vous devez définir pour contrôler si les propriétaires d’équipe peuvent donner leur consentement aux applications. Veillez à passer en revue tous les paramètres suivants.

### <a name="settings-in-azure-active-directory-portal"></a>Paramètres dans le portail Azure Active Directory

Les deux paramètres suivants déterminent si les propriétaires d’équipe peuvent donner leur consentement aux applications.

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu le consentement. Par exemple, si vous configurez ces paramètres pour empêcher les propriétaires d’équipe de donner leur consentement, ces modifications ne suppriment pas l’accès aux données qui a déjà été accordé.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Les utilisateurs peuvent donner leur consentement aux applications qui accèdent aux données de l’entreprise en leur nom

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent donner leur consentement aux applications en leur nom. Pour permettre aux propriétaires d’équipe de donner leur consentement, ce paramètre doit être défini sur **Oui**. Pour gérer ce paramètre, procédez comme suit :

1. Dans le Portail Azure, accédez aux **Applications d’entreprise** > **Paramètres utilisateur**.
2. Sous **Applications d’entreprise**, définissez **Les utilisateurs peuvent donner leur consentement aux applications qui accèdent aux données de l’entreprise en leur nom** sur **Non** ou **Oui**.

Vous pouvez également gérer ce paramètre à l’aide de PowerShell. Pour plus d’informations, consultez [Configurer le contenu utilisateur pour les applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Paramètre « EnableGroupSpecificConsent »

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent donner leur consentement aux applications qui accèdent aux données d’entreprise pour les groupes qu’ils possèdent. Ce paramètre doit être activé pour que les propriétaires d’équipe donnent leur consentement. Pour savoir comment gérer ce paramètre à l’aide de PowerShell, consultez [Configurer le consentement du propriétaire du groupe pour que les applications accèdent aux données de groupe](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Paramètres dans le Centre d’administration Microsoft Teams

Outre les paramètres dans Azure AD, [les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings) dans la page [Gérer des applications](manage-apps.md), si une application est bloquée ou autorisée dans la page [Gérer des applications](manage-apps.md#allow-and-block-apps), et la [stratégie d’autorisation d’application](teams-app-permission-policies.md) affectée au propriétaire de l’équipe détermine si un propriétaire d’équipe peut donner son consentement.

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu le consentement. Par exemple, si vous désactivez des applications tierces à l’échelle de l’organisation ou si vous bloquez des applications spécifiques pour empêcher les propriétaires d’équipe de donner leur consentement, ces modifications ne suppriment pas l’accès aux données qui a déjà été accordé.  

#### <a name="the-allow-third-party-apps-option-in-org-wide-app-settings"></a>L’option Autoriser les applications tierces dans les paramètres de l’application à l’échelle de l’organisation

Ce paramètre d’application à l’échelle de l’organisation contrôle si les utilisateurs de votre organisation peuvent utiliser des applications tierces. Ce paramètre doit être activé pour permettre aux propriétaires d’équipe de donner leur consentement. Pour gérer ce paramètre, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Sélectionnez **Paramètres d’application à l’échelle de l’organisation** et, sous **Applications tierces**, désactivez ou activez **Autoriser les applications tierces**.

   :::image type="content" source="media/resource-specific-consent-org-wide-setting.png" alt-text="Capture d’écran montrant le paramètre Autoriser les applications tierces dans Teams.":::

L’application de vos modifications peut prendre jusqu’à 24 heures.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Autoriser ou bloquer l’application au niveau de l’organisation

Lorsque vous bloquez ou autorisez une application sur la page [Gérer les applications](manage-apps.md#allow-and-block-apps), cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation. Les propriétaires d’équipe ne peuvent donner leur consentement à une application que si l’application est autorisée. Pour autoriser ou bloquer une application au niveau de l’organisation, procédez comme suit :

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Dans la page Gérer les applications, sélectionnez l’application, puis sélectionnez **Bloquer** pour la bloquer ou sélectionnez **Autoriser** pour l’autoriser.

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Stratégie d’autorisation d’application affectée au propriétaire de l’équipe

Les propriétaires d’équipe peuvent uniquement donner leur consentement aux applications que leur stratégie d’autorisation d’application leur permet d’exécuter. Pour afficher et gérer la stratégie d’autorisation d’application affectée à un propriétaire d’équipe, procédez comme suit :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**.
1. Double-cliquez sur le nom complet du propriétaire de l’équipe, puis sélectionnez **Stratégies**.
1. La stratégie affectée au propriétaire de l’équipe est répertoriée sous **Stratégie d’autorisation d’application**.

    * Pour affecter une autre stratégie, sélectionnez **Modifier**, puis sélectionnez la stratégie que vous souhaitez attribuer.
    * Pour modifier les paramètres de la stratégie affectée au propriétaire de l’équipe, sélectionnez le nom de la stratégie, puis apportez les modifications souhaitées.  

## <a name="upload-custom-apps"></a>Charger des applications personnalisées

Lors du téléchargement d'une application personnalisée (également connu sous le nom de sideloading) qui utilise un consentement spécifique aux ressources, l'application doit provenir du locataire sur lequel elle est installée. En d’autres termes, l’inscription d’application Azure AD doit être à partir de ce locataire. Les administrateurs généraux sont exemptés de cette restriction et peuvent charger des applications personnalisées à partir de n’importe quel locataire, directement vers une équipe (chargement indépendant) ou dans le catalogue d’applications client.

## <a name="related-articles"></a>Articles connexes

* [Autorisations RSC pour utiliser les données de Teams dans Microsoft Graph](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
* [Microsoft Graph](https://developer.microsoft.com/graph)
* Vous gérez les applications pour votre organisation dans les [applications Teams au sein du centre d’administration Microsoft Teams](manage-apps.md).
* [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
