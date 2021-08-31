---
title: Consentement spécifique à une ressource dans Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez les paramètres que vous devez configurer pour contrôler si les propriétaires d’équipes de votre organisation peuvent donner leur consentement aux applications.
ms.localizationpriority: medium
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 92064eb31561f74285c338edc6d482fad0b7496f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58734143"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Consentement spécifique à une ressource dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L’accord spécifique aux ressources Microsoft Teams permet aux propriétaires d’équipe d’accorder leur consentement aux applications pour accéder aux données de l’équipe. Ces accès sont, par exemple, la possibilité de lire des messages de canal, de créer et de supprimer des canaux, et de créer et supprimer des onglets de canal.

En tant qu’administrateur, vous contrôlez si les propriétaires d’équipe de votre organisation peuvent accorder leur consentement via les paramètres que vous configurez à l’aide du module PowerShell Azure Active Directory (Azure AD), du portail Azure et du Centre d’administration Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Définir si les propriétaires d’équipe peuvent accorder leur consentement aux applications

Voici les paramètres que vous devez définir pour contrôler si les propriétaires d’équipe peuvent accorder leur consentement aux applications. N’oubliez pas de passer en revue tous les paramètres suivants.

### <a name="settings-in-azure-ad"></a>Paramètres dans Azure AD

Les deux paramètres suivants déterminent si les propriétaires d’équipe peuvent accorder leur consentement aux applications.

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu l’accord. Par exemple, si vous configurez ces paramètres pour empêcher les propriétaires d’équipe de donner leur accord, ces modifications ne suppriment pas l’accès aux données déjà accordé.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Le paramètre « Les utilisateurs peuvent consenter à des applications qui accèdent à des données d’entreprise en leur nom »

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent consenter à des applications en leur nom. Pour permettre aux propriétaires d’équipe d’accorder leur consentement, ce paramètre doit être réglé sur **Oui.** Pour gérer ce paramètre, vous pouvez :

1. Dans le portail Azure, allez à la Enterprise   >  **paramètres utilisateur de l’application.**
2. Sous **Enterprise applications,** définissez que les utilisateurs peuvent **consenter** à ce que les applications accèdent aux données de l’entreprise en leur nom sur **Non** ou **Oui.**

Vous pouvez également gérer ce paramètre à l’aide de PowerShell. Pour en savoir plus, voir [Configurer le contenu utilisateur sur des applications.](/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications)

#### <a name="the-enablegroupspecificconsent-setting"></a>Paramètre « EnableGroupSpecificConsent »

Ce paramètre contrôle si les utilisateurs de votre organisation peuvent consenter aux applications qui accèdent aux données de l’entreprise pour les groupes dont ils sont propriétaire. Ce paramètre doit être activé pour que les propriétaires d’équipe consentent. Pour savoir comment gérer ce paramètre à l’aide de PowerShell, voir Configurer le consentement du propriétaire de groupe pour les applications qui accèdent aux [données du groupe.](/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data)

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Paramètres dans le Centre Microsoft Teams’administration

Outre les paramètres d’Azure AD, les [paramètres](manage-apps.md#manage-org-wide-app-settings) d’application à l’échelle de l’organisation sur [](teams-app-permission-policies.md) la [page](manage-apps.md) Gérer les applications, le blocage ou l’autorisation d’une application sur la [page](manage-apps.md#allow-and-block-apps) Gérer les applications, la stratégie d’autorisation d’application attribuée au propriétaire de l’équipe détermine si un propriétaire d’équipe peut donner son accord.

> [!IMPORTANT]
> La modification de ces paramètres n’affecte pas l’accès aux données pour les applications qui ont déjà obtenu l’accord. Par exemple, si vous désactivez les applications tierces à l’échelle de l’organisation ou si vous bloquez des applications spécifiques pour empêcher les propriétaires d’équipe d’accorder leur consentement, ces modifications ne suppriment pas l’accès aux données déjà accordé.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Paramètre « Autoriser les applications tierces » dans les paramètres de l’application à l’échelle de l’organisation

Ce paramètre d’application à l’échelle de l’organisation contrôle si les utilisateurs de votre organisation peuvent utiliser des applications tierces. Ce paramètre doit être activé pour permettre aux propriétaires d’équipe d’accorder leur accord. Pour gérer ce paramètre, vous pouvez :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez dans Teams **Applications** Gérer les applications, puis cliquez sur Paramètres de l’application à  >  l’échelle **de l’organisation.**
2. Sous **Applications tierces,** désactiver ou activer **Autoriser les applications tierces.**

    ![Capture d’écran du paramètre « Autoriser les applications tierces Teams »](media/resource-specific-consent-org-wide-setting.png)

Il est possible que les modifications ne prennent effet qu'après 24 heures.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Autoriser ou bloquer l’application au niveau de l’organisation

Lorsque vous bloquez ou autorisez une application sur la [page](manage-apps.md#allow-and-block-apps) Gérer les applications, cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation. Les propriétaires d’équipe ne peuvent accorder leur consentement à une application que si l’application est autorisée. Pour autoriser ou bloquer une application au niveau de l’organisation, vous pouvez :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Dans la page Gérer les applications,  sélectionnez l’application, puis cliquez sur Bloquer pour la bloquer ou cliquez sur Autoriser **pour** l’autoriser.

    ![Capture d’écran des applications bloquées dans les paramètres à l’échelle de l’organisation.](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Stratégie d’autorisation d’application attribuée au propriétaire de l’équipe

Les propriétaires d’équipe peuvent uniquement accorder leur consentement aux applications que leur stratégie d’autorisation d’application leur permet d’exécuter. Pour afficher et gérer la stratégie d’autorisation d’application affectée à un propriétaire d’équipe, vous pouvez :

1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez à **Utilisateurs.**
2. Double-cliquez sur le nom d’affichage du propriétaire de l’équipe, puis cliquez sur **Stratégies.**
3. La stratégie attribuée au propriétaire de l’équipe figure sous stratégie **d’autorisation d’application.**
    - Pour affecter une autre stratégie, cliquez **sur** Modifier, puis sélectionnez la stratégie à affecter.
    - Pour modifier les paramètres de la stratégie affectée au propriétaire de l’équipe, cliquez sur le nom de la stratégie, puis a apporter les modifications que vous souhaitez.  

## <a name="uploading-custom-apps"></a>Téléchargement d’applications personnalisées

Lors du téléchargement d’une application personnalisée (également connue sous le nom de « sideloading » ) qui utilise un consentement spécifique pour une ressource, l’application doit être provenant du client sur qui elle est installée. En d’autres termes, l’inscription de l’application Azure AD doit être auprès de ce client. Les administrateurs globaux sont exemptés de cette restriction et peuvent télécharger des applications personnalisées à partir de n’importe quel client, directement dans une équipe (chargement automatique) ou dans le catalogue des applications client.

## <a name="related-topics"></a>Sujets associés

- [Autorisations RSC disponibles](/microsoftteams/platform/graph-api/rsc/resource-specific-consent)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gérer vos applications dans le Centre Microsoft Teams’administration](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)