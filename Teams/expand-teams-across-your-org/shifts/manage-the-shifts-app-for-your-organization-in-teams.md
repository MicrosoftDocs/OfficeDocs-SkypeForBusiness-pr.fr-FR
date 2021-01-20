---
title: Gérer l’application Shifts pour votre organisation
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 218b041d83cde91a23201ab864160ce3b8b7cb6e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909088"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Shifts pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> Microsoft StaffHub a été retiré le 30 juin 2020. Nous allons développer les fonctionnalités de StaffHub dans Microsoft Teams. Aujourd’hui, Teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployer au fil du temps. StaffHub a cessé de fonctionner pour tous les utilisateurs le 30 juin 2020. Tous les autres personnes qui tentent d’ouvrir StaffHub s’afficheront un message les en dirigerant pour télécharger Teams. Pour en savoir plus, [voir Microsoft StaffHub a été retiré.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview-of-shifts"></a>Vue d’ensemble de Shifts

L’application Shifts de Microsoft Teams maintient la connexion et la synchronisation des employés en contact direct avec les employés en contact. Il est conçu en premier lieu pour une gestion et une communication rapides et efficaces pour les équipes. Shifts permet aux employés en contact direct et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en contact.

- Les responsables créent, actualent et gèrent les plannings des shifts pour les équipes. Ils peuvent envoyer des messages à une personne (« du spill s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »). Ils peuvent également envoyer des documents stratégiques, des bulletins d’informations et des vidéos. 
- Les employés voient leurs shifts à venir, voient qui d’autre est programmé pour la journée, demandent à échanger ou proposer un shift et demandent un congé. 

Il est important de savoir que Shifts ne prend pas en charge les utilisateurs invités pour le moment. Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés ou utiliser des plannings de shift lorsque l’accès invité est désactivé dans Teams. 

> [!Note]
> Pour plus d’informations sur les fonctionnalités de Shifts sur différentes plateformes, consultez [les fonctionnalités de Teams par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="availability-of-shifts"></a>Disponibilité de Shifts

Shifts est disponible dans toutes les S SKUS Entreprise où Teams est disponible.

## <a name="location-of-shifts-data"></a>Emplacement des données shifts

Les données shifts sont actuellement stockées dans Azure dans des centres de données en Amérique du Nord, en Europe de l’ouest et en Asie-Pacifique. Pour plus d’informations sur l’endroit où sont stockées les données, voir [Où se trouve mes données](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurer Shifts

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver shifts dans votre organisation

Shifts est activé par défaut pour tous les utilisateurs de Teams dans votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les](../../manage-apps.md) applications du Centre d’administration Microsoft Teams.

1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez dans les **applications Teams**  >  **Gérer les applications.**
2. Dans la liste des applications, faites l’une des actions suivantes :

    - Pour désactiver Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis choisissez **Bloquer.**
    - Pour activer Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis **sélectionnez Autoriser.**

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver les shifts pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Shifts, assurez-vous que Shifts est désactivé pour votre organisation sur la [page](../../manage-apps.md) Gérer les applications, puis créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, consultez [Gérer les stratégies d’autorisation d’application dans Teams.](../../teams-app-permission-policies.md)

### <a name="use-the-frontlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser la stratégie de configuration de l’application FrontlineWorker pour épingler Shifts à Teams

Les stratégies de configuration d’application vous permettent de personnaliser Teams pour mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications définies dans une stratégie sont épinglées à la barre de l’application sur le côté du client de bureau Teams et en bas des clients mobiles Teams où les utilisateurs peuvent y accéder rapidement et &mdash; &mdash; facilement.
 
Teams inclut une stratégie de configuration d’application FrontlineWorker intégrée que vous pouvez affecter aux employés de votre organisation qui travaillent en ligne. Par défaut, la stratégie inclut les applications Activité, Shifts, Conversation et Appel. 

Pour afficher la stratégie FrontlineWorker, dans le menu de navigation gauche du Centre d’administration Microsoft Teams, consultez les stratégies de configuration de **l’application Teams.**  >  

![Capture d’écran de la stratégie de configuration de l’application FrontlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FrontlineWorker dans le Centre d’administration Microsoft Teams")

#### <a name="assign-the-frontlineworker-app-setup-policy-to-users"></a>Affecter la stratégie de configuration de l’application FrontlineWorker aux utilisateurs

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Rechercher des événements Shifts dans le journal d’audit

**(version d’évaluation)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité Shifts au niveau de votre organisation.  Pour en savoir plus sur la recherche dans le journal d’audit et la liste des activités [Shifts enregistrées](../../audit-log-events.md#shifts-in-teams-activities) dans le journal d’audit, consultez Rechercher des événements dans Teams dans le journal d’audit. [](../../audit-log-events.md)

Avant d’effectuer une recherche dans le journal d’audit, vous devez activer l’audit dans le Centre [& conformité.](https://protection.office.com) Pour en savoir plus, voir Activer ou désactiver la recherche dans le [journal d’audit.](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014) Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du moment où vous avez désactivé l’audit.

## <a name="related-topics"></a>Sujets associés

- [Aide shifts pour les employés en avant-première](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs](../../assign-policies.md)
