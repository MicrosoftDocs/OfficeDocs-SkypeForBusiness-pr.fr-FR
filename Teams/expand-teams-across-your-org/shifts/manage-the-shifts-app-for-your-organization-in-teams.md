---
title: Gérer l’application Plannings pour votre organisation dans Teams
author: serdarsoysal
ms.author: serdars
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment configurer et gérer l’application Shifts dans Teams pour les employés en ligne de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d7c1bdde4764b56e8c45a8ad9356437525f00b56
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045720"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Plannings pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> Microsoft StaffHub n’existe plus depuis le 30 juin 2020. Nous développons les fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, Teams inclut l’application Plannings pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées à l’avenir. StaffHub a cessé de fonctionner pour tous les utilisateurs le 30 juin 2020. Toute personne qui essaie d’ouvrir StaffHub s’afficher un message lui permettant de télécharger Teams. Pour en savoir plus, consultez l’article [Microsoft StaffHub n’existe plus](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Vue d’ensemble de Plannings

L’application Shifts dans Microsoft Teams les employés en contact direct et synchronisés. Il est conçu en premier lieu pour une gestion et une communication rapides et efficaces pour les équipes. Les équipes de employés en contact direct avec leurs responsables et employés peuvent utiliser leurs appareils mobiles pour gérer les plannings et rester en contact.

- Les responsables créent, mettent à jour et gèrent les plannings relatifs aux roulements de équipes. Ils peuvent envoyer des messages à un membre en particulier (« du liquide s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »). Ils peuvent aussi envoyer des documents stratégiques, des bulletins d’informations et des vidéos.
- Les employés peuvent consulter leurs horaires de travail, voir qui est prévu pour la journée, demander à échanger ou offrir une shift, et demander des congés.

Il est important de savoir que Shifts ne permet pas actuellement de prendre en charge les invités. Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés à des plannings de shift ou utiliser ceux-ci lorsque l’accès invité est désactivé dans Teams. 

> [!Note]
> Pour plus d’informations sur les fonctionnalités Shifts sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilité de Plannings

Plannings est disponible dans toutes les références Entreprise où Teams est disponible.

## <a name="location-of-shifts-data"></a>Emplacement des données Plannings

Les données Plannings sont actuellement stockées dans Azure dans des centres de données en Amérique du Nord, en Europe de l’ouest et en Asie-Pacifique. Pour plus d’informations sur l’emplacement de stockage des données, voir [Où se trouvent mes données](http://o365datacentermap.azurewebsites.net/) ?

## <a name="set-up-shifts"></a>Configurer des Plannings

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver Plannings dans votre organisation

Plannings est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, effectuez l’une des actions suivantes :

    - Pour désactiver Plannings pour votre organisation, recherchez l’application Plannings, sélectionnez-la, puis sélectionnez **Bloquer**.
    - Pour activer Plannings pour votre organisation, recherchez l’application Plannings, sélectionnez-la, puis sélectionnez **Autoriser**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver Plannings pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Shifts, assurez-vous que Shifts soit désactivé pour votre organisation sur la page [Gérer les applications.](../../manage-apps.md) Ensuite, créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Utilisez la stratégie de configuration de l’application FirstLineWorker pour épingler Shifts à Teams

Les stratégies de configuration des applications vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications que vous définissez dans une stratégie sont épinglées à la barre d’applications&mdash;, la barre se trouvant sur le côté du client Teams pour ordinateur de bureau et en bas des clients mobiles Teams&mdash; là où les utilisateurs peuvent y accéder rapidement et facilement.
 
Teams inclut une stratégie de configuration intégrée de l’application FirstLineWorker que vous pouvez affecter aux employés en ligne de votre organisation. Par défaut, la stratégie inclut les applications Activité, Plannings, Conversation et Appel.

Pour afficher la stratégie FirstLineWorker, dans le menu de navigation gauche du Centre d’administration Microsoft Teams, consultez l’Teams **de configuration**  >  **de l’application.**

:::image type="content" source="../../media/firstline-worker-app-setup-policy-new.png" alt-text="Capture d’écran de la stratégie de configuration de l’application FirstLineWorker dans le Microsoft Teams d’administration" lightbox="../../media/firstline-worker-app-setup-policy-new.png":::

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Affecter la stratégie de configuration de l’application FirstLineWorker aux utilisateurs

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Rechercher des événements de Plannings dans le journal d’audit 

**(version d’évaluation)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité shifts au niveau de votre organisation.  Pour en savoir plus sur la façon d'effectuer une recherche dans le journal d'audit et pour consulter la liste des [Activités Plannings](../../audit-log-events.md#shifts-in-teams-activities) qui sont enregistrées dans le journal d'audit, consultez [Recherche d'événements dans le journal d'audit dans Teams](../../audit-log-events.md).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://protection.office.com). Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="related-topics"></a>Rubriques connexes

- [Aide shifts pour les employés en avant-plan](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs](../../assign-policies.md)
