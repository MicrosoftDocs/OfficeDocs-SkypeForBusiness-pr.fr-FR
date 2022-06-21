---
title: Consentement spécifique aux ressources dans Microsoft Teams
author: guptaashish
ms.author: guptaashish
ms.reviewer: nkramer
manager: prkosh
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez les paramètres que vous devez configurer pour contrôler si les propriétaires d’équipes de votre organisation peuvent donner leur consentement aux applications.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b5ef3f94c511dfe86ab7b153bfa8dd3ea1a04fa
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190495"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentement spécifique aux ressources dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le consentement spécifique aux ressources dans Microsoft Teams permet aux propriétaires d’équipe de donner leur consentement aux applications pour accéder aux données d’équipe. Parmi ces accès, citons la possibilité de lire des messages de canal, de créer et de supprimer des canaux, ainsi que de créer et de supprimer des onglets de canal.

En tant qu’administrateur, vous contrôlez si les propriétaires d’équipe de votre organisation peuvent donner leur consentement via les paramètres que vous configurez à l’aide du module PowerShell Azure Active Directory (Azure AD) ou du Portail Azure et du centre d’administration Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Définir si les propriétaires d’équipe peuvent donner leur consentement aux applications

Voici les paramètres que vous devez définir pour contrôler si les propriétaires d’équipe peuvent donner leur consentement aux applications. Veillez à passer en revue tous les paramètres suivants.

### <a name="settings-in-azure-ad"></a>Paramètres dans Azure AD

Les deux paramètres suivants déterminent si les propriétaires d’équipe peuvent donner leur consentement aux applications.

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu le consentement. Par exemple, si vous configurez ces paramètres pour empêcher les propriétaires d’équipe de donner leur consentement, ces modifications ne suppriment pas l’accès aux données qui a déjà été accordé.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Paramètre « Les utilisateurs peuvent donner leur consentement aux applications accédant aux données d’entreprise en leur nom »

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent donner leur consentement aux applications en leur nom. Pour permettre aux propriétaires d’équipe de donner leur consentement, ce paramètre doit être défini sur **Oui**. Pour gérer ce paramètre, procédez comme suit :

1. Dans le Portail Azure, accédez à Enterprise **paramètres utilisateur des** **applications** > .
2. Sous **Enterprise applications**, **définissez Les utilisateurs peuvent donner leur consentement aux applications qui accèdent aux données de l’entreprise en leur nom** sur **Non** ou **Oui**.

Vous pouvez également gérer ce paramètre à l’aide de PowerShell. Pour plus d’informations, consultez [Configurer le contenu utilisateur pour les applications](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Paramètre « EnableGroupSpecificConsent »

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent donner leur consentement aux applications qui accèdent aux données d’entreprise pour les groupes qu’ils possèdent. Ce paramètre doit être activé pour que les propriétaires d’équipe donnent leur consentement. Pour savoir comment gérer ce paramètre à l’aide de PowerShell, consultez [Configurer le consentement du propriétaire du groupe pour que les applications accèdent aux données de groupe](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Paramètres dans le Centre d’administration Microsoft Teams

Outre les paramètres dans Azure AD, [les paramètres d’application à l’échelle de l’organisation](manage-apps.md#manage-org-wide-app-settings) dans la page [Gérer les applications](manage-apps.md), si une application est bloquée ou autorisée dans la page [Gérer les applications](manage-apps.md#allow-and-block-apps), et la stratégie d’autorisation d’application affectée au propriétaire de l’équipe détermine si un propriétaire d’équipe peut donner son consentement.[](teams-app-permission-policies.md)

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu le consentement. Par exemple, si vous désactivez des applications tierces à l’échelle de l’organisation ou si vous bloquez des applications spécifiques pour empêcher les propriétaires d’équipe de donner leur consentement, ces modifications ne suppriment pas l’accès aux données qui a déjà été accordé.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Paramètre « Autoriser les applications tierces » dans les paramètres d’application à l’échelle de l’organisation

Ce paramètre d’application à l’échelle de l’organisation contrôle si les utilisateurs de votre organisation peuvent utiliser des applications tierces. Ce paramètre doit être activé pour permettre aux propriétaires d’équipe de donner leur consentement. Pour gérer ce paramètre, procédez comme suit :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Teams applications** > **Gérer les applications**, puis cliquez sur **Paramètres d’application à l’échelle de l’organisation**.
2. Sous **Applications tierces**, désactivez ou **activez Autoriser les applications tierces**.

    ![Capture d’écran du paramètre « Autoriser les applications tierces dans Teams »](media/resource-specific-consent-org-wide-setting.png)

Il est possible que les modifications ne prennent effet qu'après 24 heures.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Autoriser ou bloquer l’application au niveau de l’organisation

Lorsque vous bloquez ou autorisez une application sur la page [Gérer les applications](manage-apps.md#allow-and-block-apps) , cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation. Les propriétaires d’équipe ne peuvent donner leur consentement à une application que si l’application est autorisée. Pour autoriser ou bloquer une application au niveau de l’organisation, procédez comme suit :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Dans la page Gérer les applications, sélectionnez l’application, puis cliquez sur **Bloquer** pour la bloquer ou cliquez sur **Autoriser** pour l’autoriser.

    ![Capture d’écran des applications bloquées dans les paramètres à l’échelle de l’organisation.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Stratégie d’autorisation d’application affectée au propriétaire de l’équipe

Les propriétaires d’équipe peuvent uniquement donner leur consentement aux applications que leur stratégie d’autorisation d’application leur permet d’exécuter. Pour afficher et gérer la stratégie d’autorisation d’application affectée à un propriétaire d’équipe, procédez comme suit :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Utilisateurs**.
2. Double-cliquez sur le nom d’affichage du propriétaire de l’équipe, puis cliquez sur **Stratégies**.
3. La stratégie affectée au propriétaire de l’équipe est répertoriée sous stratégie **d’autorisation d’application**.
    - Pour affecter une autre stratégie, cliquez sur **Modifier**, puis sélectionnez la stratégie que vous souhaitez affecter.
    - Pour modifier les paramètres de la stratégie affectée au propriétaire de l’équipe, cliquez sur le nom de la stratégie, puis apportez les modifications souhaitées.  

## <a name="uploading-custom-apps"></a>Chargement d’applications personnalisées

Lors du chargement d’une application personnalisée (également appelée chargement indépendant) qui utilise le consentement spécifique à la ressource, l’application doit provenir du locataire sur lequel elle est installée. En d’autres termes, l’inscription d’application Azure AD doit être à partir de ce locataire. Les administrateurs généraux sont exemptés de cette restriction et peuvent charger des applications personnalisées à partir de n’importe quel locataire, directement vers une équipe (chargement indépendant) ou dans le catalogue d’applications client.

## <a name="related-topics"></a>Voir aussi

- [Autorisations RSC disponibles](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gérer vos applications dans le centre d’administration Microsoft Teams](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
