---
title: Gérer l’application Plannings pour votre organisation dans Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
description: Découvrez comment configurer et gérer l’application Shifts dans Teams pour les employés en ligne de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d38af9f55f1620a1f38ad5860c71366201bb9444
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039902"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Plannings pour votre organisation dans Microsoft Teams

## <a name="overview-of-shifts"></a>Vue d’ensemble de Plannings

L’application Shifts dans Microsoft Teams les employés en contact direct et synchronisés. Il est conçu en premier lieu pour une gestion et une communication rapides et efficaces pour les équipes. Les shifts viennent aider les employés en contact direct et les responsables à utiliser leurs appareils mobiles pour gérer les plannings et rester en contact.

- Les responsables créent, mettent à jour et gèrent les plannings relatifs aux roulements de équipes. Ils peuvent envoyer des messages à un membre en particulier (« du liquide s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »). Ils peuvent aussi envoyer des documents stratégiques, des bulletins d’informations et des vidéos.
- Les employés peuvent consulter leurs horaires de travail, voir qui est prévu pour la journée, demander à échanger ou offrir une shift, et demander des congés.

Il est important de savoir que Shifts ne permet pas actuellement de prendre en charge les invités. Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés à des plannings de shift ou utiliser ceux-ci lorsque l’accès invité est désactivé dans Teams.

> [!Note]
> Pour plus d’informations sur les fonctionnalités Shifts sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilité de Plannings

Plannings est disponible dans toutes les références Entreprise où Teams est disponible.

> [!NOTE]
> Shifts est disponible dans des environnements Cloud de la communauté du secteur public (Cloud de la communauté du secteur public), mais pas dans Cloud de la communauté du secteur public des environnements Élevé ou DoD.

## <a name="location-of-shifts-data"></a>Emplacement des données Plannings

Les données shifts sont actuellement stockées dans Azure dans des centres de données en Asie-Pacifique (APAC), dans l’Union européenne (UE) et en Amérique du Nord. Pour plus d’informations sur l’emplacement de stockage des données, voir [Où se trouvent mes données](http://o365datacentermap.azurewebsites.net/) ?

Pour en savoir plus sur les données Shifts, notamment le stockage, la rétention, l’extraction et le chiffrement des données Shifts, voir [FAQ sur les données Shifts](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Configurer des Plannings

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver Plannings dans votre organisation

Plannings est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Shifts, sélectionnez-la, puis  basculez le bouton bascule Statut sur **Bloqué** ou **Autorisé**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver Plannings pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Shifts, assurez-vous que Shifts est désactivé pour votre organisation sur la page [Gérer les applications](../../manage-apps.md) . Ensuite, créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](../../teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser une stratégie de configuration d’application pour épingler Shifts à Teams

Les stratégies de configuration des applications vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications que vous définissez dans une stratégie sont épinglées à la barre d’applications&mdash;, la barre se trouvant sur le côté du client Teams pour ordinateur de bureau et en bas des clients mobiles Teams&mdash; là où les utilisateurs peuvent y accéder rapidement et facilement.

Vous pouvez créer une stratégie [de configuration d’application](../../teams-app-setup-policies.md) personnalisée en ajoutant l’application Shifts, puis en [affecter](../../assign-policies-users-and-groups.md) la stratégie à vos utilisateurs. Vous pouvez également utiliser la stratégie de configuration de l’application qui fait partie des packages de stratégies Frontline Worker et Frontline Manager.

Un [package de](../../manage-policy-packages.md) stratégie dans Teams est un ensemble de stratégies et paramètres de stratégie prédéfinés que vous pouvez affecter aux utilisateurs ayant des rôles similaires dans votre organisation. L’ensemble des stratégies dans les packages de stratégies Frontline Worker et Frontline Manager incluent une stratégie de configuration d’application qui épingle l’application Shifts et d’autres applications qui supportent les activités de communication et de collaboration pour ce rôle.

Nous vous recommandons d’utiliser les packages de stratégies Frontline Worker et Frontline Manager dans le cadre de la simplification, de la simplification et de l’aide en matière de cohérence dans le cadre de la gestion des stratégies pour votre personnel en première ligne.

## <a name="search-the-audit-log-for-shifts-events"></a>Rechercher des événements de Plannings dans le journal d’audit 

**(version d’évaluation)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité shifts au niveau de votre organisation.  Pour en savoir plus sur la façon d'effectuer une recherche dans le journal d'audit et pour consulter la liste des [Activités Plannings](../../audit-log-events.md#shifts-in-teams-activities) qui sont enregistrées dans le journal d'audit, consultez [Recherche d'événements dans le journal d'audit dans Teams](../../audit-log-events.md).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://protection.office.com). Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="related-articles"></a>Articles connexes

- [Shifts pour Teams](../shifts-for-teams-landing-page.md)
- [FAQ shifts de données](shifts-data-faq.md)
- [Connecteurs Shifts](shifts-connectors.md)
- [Aide shifts pour les employés en avant-première](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs](../../policy-assignment-overview.md)
