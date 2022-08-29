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
description: Découvrez comment configurer et gérer l’application Shifts dans Teams pour les employés de première ligne de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 759e0cb846b6bca404276e50ca00a1ff28d5725c
ms.sourcegitcommit: 17f4baf85e1ac6a2af5f5c6ea2d5aae763efd917
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/23/2022
ms.locfileid: "67405136"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Plannings pour votre organisation dans Microsoft Teams

## <a name="overview-of-shifts"></a>Vue d’ensemble de Plannings

L’application Shifts dans Microsoft Teams maintient les employés de première ligne connectés et synchronisés. Il est d’abord conçu pour la gestion du temps et la communication rapides et efficaces pour les équipes. Les équipes permettent aux employés de première ligne et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les planifications et rester en contact.

- Les responsables créent, mettent à jour et gèrent les plannings relatifs aux roulements de équipes. Ils peuvent envoyer des messages à un membre en particulier (« du liquide s’est renversé sur le sol ») ou à toute l’équipe (« le directeur régional arrive dans 20 minutes »). Ils peuvent aussi envoyer des documents stratégiques, des bulletins d’informations et des vidéos.
- Les employés peuvent consulter leurs horaires de travail, voir qui est prévu pour la journée, demander à échanger ou offrir une shift, et demander des congés.

Il est important de savoir que Shifts ne prend actuellement pas en charge les invités. Cela signifie que les invités d’une équipe ne peuvent pas être ajoutés à des plannings de shift ou utiliser ceux-ci lorsque l’accès invité est désactivé dans Teams.

> [!Note]
> Pour plus d’informations sur les fonctionnalités Shifts sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="availability-of-shifts"></a>Disponibilité de Plannings

Plannings est disponible dans toutes les références Entreprise où Teams est disponible.

> [!NOTE]
> Les décalages sont disponibles dans les environnements cloud de la communauté du secteur public (GCC), mais pas dans les environnements GCC High ou DoD.

## <a name="location-of-shifts-data"></a>Emplacement des données Plannings

Les données shifts sont actuellement stockées dans Azure dans des centres de données en Asie-Pacifique (APAC), dans l’Union européenne (UE) et dans Amérique du Nord. Pour plus d’informations sur l’emplacement de stockage des données, voir [Où se trouvent mes données](http://o365datacentermap.azurewebsites.net/) ?

Pour en savoir plus sur les données Shifts, notamment le stockage, la rétention, la récupération et le chiffrement des données Shifts, consultez la [FAQ sur les données Shifts](shifts-data-faq.md).

## <a name="set-up-shifts"></a>Configurer des Plannings

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver Plannings dans votre organisation

Plannings est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Shifts, sélectionnez-la, puis basculez le bouton bascule **État** sur **Bloqué** ou **Autorisé**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver Plannings pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Shifts, assurez-vous que Shifts est activé pour votre organisation sur la page [Gérer les applications](../../manage-apps.md) . Créez ensuite une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](../../teams-app-permission-policies.md).

### <a name="pin-shifts-to-teams"></a>Épingler des majs à Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-shifts-and-other-apps-to-teams"></a>Utiliser l’expérience d’application de première ligne personnalisée pour épingler Shifts et d’autres applications à Teams

L’expérience d’application de première ligne personnalisée dans Teams épingle les applications les plus pertinentes dans Teams pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt). Les applications épinglées incluent shifts, Walkie Talkie, Tasks et Approvals. Par défaut, cette fonctionnalité est activée, ce qui offre à vos employés de première ligne une expérience prêt à l’emploi adaptée à leurs besoins.

Les applications sont épinglées à la barre de l’application , la barre située sur le côté du client de bureau Teams et en bas des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement.

Pour en savoir plus, notamment sur le fonctionnement de l’expérience avec les stratégies d’application que vous définissez, consultez [Personnaliser les applications Teams pour vos employés de première ligne](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).  

#### <a name="use-an-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser une stratégie d’installation d’application pour épingler Shifts à Teams

Les stratégies d’installation d’application vous permettent de personnaliser Teams pour épingler les applications les plus importantes pour vos utilisateurs.

Vous pouvez créer une [stratégie d’installation d’application personnalisée](../../teams-app-setup-policies.md) en ajoutant l’application Shifts, puis [en affectant la stratégie](../../assign-policies-users-and-groups.md) à vos utilisateurs. Vous pouvez également utiliser la stratégie d’installation d’application qui fait partie des packages de stratégie Frontline Worker et Frontline Manager.

Un [package de stratégie](../../manage-policy-packages.md) dans Teams est une collection de stratégies et de paramètres de stratégie prédéfinis que vous pouvez attribuer aux utilisateurs qui ont des rôles similaires dans votre organisation. L’ensemble de stratégies dans les packages de stratégie Frontline Worker et Frontline Manager inclut une stratégie d’installation d’application qui épingle l’application Shifts et d’autres applications qui prennent en charge les activités de communication et de collaboration pour ce rôle.

Nous vous recommandons d’utiliser les packages de stratégie De frontline Worker et Frontline Manager, car ils simplifient, simplifient et aident à assurer la cohérence lors de la gestion des stratégies pour votre personnel de première ligne.

### <a name="enable-shift-based-tags-in-teams"></a>Activer des balises basées sur des shifts dans Teams

[Les balises](https://support.microsoft.com/office/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e) dans Teams permettent aux utilisateurs de se connecter facilement à un sous-ensemble de personnes d’une équipe. Avec les balises basées sur les shifts, les personnes reçoivent automatiquement des balises qui correspondent à leur nom de groupe de planification et de décalage dans Shifts. La balise peut être utilisée dans @mentions sur la ligne **À** dans une conversation ou dans un billet sur n’importe quel canal standard de l’équipe.

Les balises basées sur les shifts permettent à vos utilisateurs d’atteindre des personnes en déplacement en temps réel. Les notifications sont envoyées uniquement aux personnes qui sont en équipe au moment où l’étiquette est utilisée dans une conversation ou un billet de canal. Par exemple :

- Un responsable de magasin utilise la balise @Cashiers pour publier une annonce sur un canal pour tous les caissier en équipe.
- Une infirmière utilise la balise @CardiologistsOnCall pour démarrer une conversation avec tous les cardiologues de garde.

Vous pouvez activer ou désactiver la fonctionnalité dans le Centre d’administration Microsoft Teams. Pour plus d’informations, consultez [Gérer les étiquettes dans Teams](../../manage-tags.md).

## <a name="search-the-audit-log-for-shifts-events"></a>Rechercher des événements de Plannings dans le journal d’audit 

**(En préversion)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité shifts au niveau de votre organisation.  Pour en savoir plus sur la façon d'effectuer une recherche dans le journal d'audit et pour consulter la liste des [Activités Plannings](../../audit-log-events.md#shifts-in-teams-activities) qui sont enregistrées dans le journal d'audit, consultez [Recherche d'événements dans le journal d'audit dans Teams](../../audit-log-events.md).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://protection.office.com). Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="related-articles"></a>Articles connexes

- [Shifts pour Teams](/microsoft-365/frontline/shifts-for-teams-landing-page)
- [Faq sur les changements de données](shifts-data-faq.md)
- [Majs connecteurs](/microsoft-365/frontline/shifts-connectors)
- [Aide sur les shifts pour les travailleurs de première ligne](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs](../../policy-assignment-overview.md)
