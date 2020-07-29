---
title: Autorisation spécifique aux ressources dans Microsoft teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: nkramer
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: En savoir plus sur les paramètres que vous devez configurer pour contrôler si les propriétaires d’équipes au sein de votre organisation peuvent donner leur consentement aux applications.
localization_priority: Normal
ms.collection: M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ed13f1f85b0c7eccead3737c4549931f016284c
ms.sourcegitcommit: 682566e51a9e5f0fc65540535c7dcdcbd38e04c4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429376"
---
# <a name="resource-specific-consent-in-microsoft-teams"></a>Autorisation spécifique aux ressources dans Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Le consentement spécifique aux ressources dans Microsoft teams permet aux propriétaires d’équipe de donner leur consentement aux applications d’accéder aux données de l’équipe. Les exemples d’accès incluent la possibilité de lire les messages de canal, de créer et de supprimer des canaux, et de créer et de supprimer des onglets de canal.

En tant qu’administrateur, vous pouvez contrôler si les propriétaires d’équipe de votre organisation peuvent donner leur consentement via les paramètres que vous configurez via le module Azure Active Directory (Azure AD) PowerShell ou le portail Azure et le centre d’administration Microsoft Teams.  

## <a name="set-whether-team-owners-can-give-consent-to-apps"></a>Définir si les propriétaires d’équipe peuvent donner leur consentement aux applications

Voici les paramètres que vous devez définir pour contrôler si les propriétaires d’équipe peuvent donner leur consentement aux applications. Veillez à examiner tous les paramètres suivants.

### <a name="settings-in-azure-ad"></a>Paramètres d’Azure AD

Les deux paramètres suivants déterminent si les propriétaires d’équipe peuvent donner leur consentement aux applications.

> [!IMPORTANT]
> La modification de ces paramètres n’a aucun impact sur l’accès aux données pour les applications qui ont déjà reçu le consentement. Par exemple, si vous configurez ces paramètres de façon à ce que les propriétaires d’équipe n’accordent pas le consentement, ces modifications ne suppriment pas l’accès aux données déjà accordé.

#### <a name="the-users-can-consent-to-apps-accessing-company-data-on-their-behalf-setting"></a>Le paramètre « les utilisateurs peuvent consentir aux applications d’accéder aux données de l’entreprise en leur nom ».

Ce paramètre détermine si les utilisateurs de votre organisation peuvent accepter des applications en leur nom. Pour permettre aux propriétaires d’équipe de donner leur consentement, ce paramètre doit être défini sur **Oui**. Pour gérer ce paramètre, procédez comme suit :

1. Dans le portail Azure, accédez à paramètres utilisateur de l' **application applications d’entreprise**  >  **User settings**.
2. Sous **applications d’entreprise**, définissez **les utilisateurs peuvent consentir aux applications d’accéder aux données de l’entreprise en leur nom** pour **non** ou **Oui**.

Vous pouvez également gérer ce paramètre à l’aide de PowerShell. Pour en savoir plus, voir [configurer le contenu utilisateur pour les applications](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-user-consent-to-applications).

#### <a name="the-enablegroupspecificconsent-setting"></a>Paramètre « EnableGroupSpecificConsent »

Ce paramètre détermine si les utilisateurs de votre organisation peuvent consentir aux applications d’accéder aux données de société pour les groupes qu’ils possèdent. Ce paramètre doit être activé pour permettre aux propriétaires d’équipe de donner leur consentement. Pour savoir comment gérer ce paramètre à l’aide de PowerShell, voir [configurer l’autorisation du propriétaire du groupe pour les applications qui accèdent aux données de groupe](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-user-consent#configure-group-owner-consent-to-apps-accessing-group-data).

### <a name="settings-in-the-microsoft-teams-admin-center"></a>Paramètres dans le centre d’administration Microsoft teams

En plus des paramètres des [paramètres d’application](manage-apps.md#manage-org-wide-app-settings) Azure ad et de l’organisation à l’échelle de l’organisation dans la page gérer les [applications](manage-apps.md) , si une application est bloquée ou autorisée sur la page gérer les [applications](manage-apps.md#allow-and-block-apps) , et la stratégie d' [autorisation d’application](teams-app-permission-policies.md) attribuée au propriétaire de l’équipe, déterminez si un propriétaire d’équipe peut donner son consentement.

> [!IMPORTANT]
> La modification de ces paramètres n’a aucun impact sur l’accès aux données pour les applications qui ont déjà reçu le consentement. Par exemple, si vous désactivez les applications tierces au niveau de l’organisation, ou si vous bloquez des applications spécifiques pour empêcher les propriétaires d’équipe d’accorder du consentement, ces modifications ne suppriment pas l’accès aux données déjà reçu.  

#### <a name="the-allow-third-party-apps-setting-in-org-wide-app-settings"></a>Paramètre « autoriser les applications tierces » dans les paramètres de l’application à l’échelle de l’Organisation

Ce paramètre d’application à l’échelle de l’organisation contrôle si les utilisateurs de votre organisation peuvent utiliser des applications tierces. Ce paramètre doit être activé pour permettre aux propriétaires d’équipe de donner leur consentement. Pour gérer ce paramètre, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage Apps**, puis cliquez sur **paramètres de l’application à l’échelle**de l’organisation.
2. Sous **applications tierces**, désactivez ou activez l’option **autoriser les applications**tierces.

    ![Capture d’écran du paramètre « autoriser les applications tierces dans teams »](media/resource-specific-consent-org-wide-setting.png)

Il est possible que les modifications ne prennent effet qu'après 24 heures.

#### <a name="allow-or-block-the-app-at-the-org-level"></a>Autoriser ou bloquer l’application au niveau de l’Organisation

Lorsque vous bloquez ou autorisez une application dans la page [gérer les applications](manage-apps.md#allow-and-block-apps) , cette application est bloquée ou autorisée pour tous les utilisateurs de votre organisation. Les propriétaires d’équipe peuvent uniquement accorder l’autorisation d’une application s’il est autorisé. Pour autoriser ou bloquer une application au niveau de l’organisation, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps.
2. Dans la page gérer les applications, sélectionnez l’application, puis cliquez sur **bloquer** pour la bloquer ou cliquez sur **autoriser** pour l’autoriser.

    ![Capture d’écran des applications bloquées dans les paramètres à l’échelle de l’Organisation](media/resource-specific-consent-allow-block-apps.png)

#### <a name="app-permission-policy-assigned-to-the-team-owner"></a>Stratégie d’autorisation d’application attribuée au propriétaire de l’équipe

Les propriétaires d’équipe peuvent uniquement accorder l’autorisation aux applications que leur stratégie d’autorisation d’application leur permet d’s’exécuter. Pour afficher et gérer la stratégie d’autorisation d’application affectée au propriétaire d’une équipe, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Double-cliquez sur le nom d’affichage du propriétaire de l’équipe, puis sur **stratégies**.
3. La stratégie attribuée au propriétaire de l’équipe figure sous **stratégie d’autorisation d’applications**.
    - Pour affecter une autre stratégie, cliquez sur **modifier**, puis sélectionnez la stratégie que vous voulez attribuer.
    - Pour modifier les paramètres de la stratégie attribuée au propriétaire de l’équipe, cliquez sur le nom de la stratégie, puis apportez les modifications souhaitées.  

## <a name="uploading-custom-apps"></a>Téléchargement d’applications personnalisées

Lorsque vous téléchargez une application personnalisée (également connue sous le nom de chargement indépendant) qui utilise l’autorisation spécifique aux ressources, l’application doit provenir du client sur lequel elle est installée. En d’autres termes, l’inscription de l’application Azure AD doit être de ce client. Les administrateurs globaux sont exemptés de cette restriction et peuvent télécharger des applications personnalisées à partir de n’importe quel client, directement dans une équipe (chargement indépendant) ou dans le catalogue d’applications du client.

## <a name="related-topics"></a>Voir aussi

- [Autorisations RSC disponibles](https://aka.ms/teams-rsc)
- [Microsoft Graph](https://developer.microsoft.com/graph)
- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
