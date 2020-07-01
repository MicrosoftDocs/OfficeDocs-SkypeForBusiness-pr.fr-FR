---
title: Gestion de l’application Shifts pour votre organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu,gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application Shifts dans teams pour terrain travailleurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ecc64c105bb9171942dfac912ccea4f2fa1442aa
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938353"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Shifts pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> À compter du 30 juin 2020, Microsoft StaffHub a été annulé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub a cessé de fonctionner pour tous les utilisateurs du 30 juin 2020. Tout utilisateur qui tente d’ouvrir StaffHub est affiché un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la section le [retrait de Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Vue d’ensemble des équipes

L’application Shifts dans Microsoft teams permet aux utilisateurs de terrain de se connecter et de se synchroniser avec eux. Il s’agit d’abord sur un appareil mobile pour une gestion rapide et efficace du temps pour les équipes. Les Shifts permettent à terrain travailleurs et à leurs responsables d’utiliser leurs appareils mobiles pour gérer les plannings et rester en interaction.

- Les responsables créent, mettent à jour et gèrent les plannings de Shifts pour Teams. Ils peuvent envoyer des messages à une personne (« il y a un renversé sur le plancher ») ou à l’équipe entière (« le GM régional arrive dans 20 minutes »). Ils peuvent également envoyer des documents de stratégie, des bulletins d’actualité et des vidéos. 
- Les employés peuvent afficher leurs Shifts à venir, peuvent voir qui est programmé pour la journée, demander à échanger ou proposer un Shift et demander du temps. 

Il est important de savoir que les Shifts ne prennent actuellement pas en charge les utilisateurs invités. Cela signifie que les invités ne peuvent pas être ajoutés à une équipe ou utiliser les plannings de décalage lorsque l’accès invité est activé dans Teams. 

## <a name="availability-of-shifts"></a>Disponibilité des équipes

Le changement est disponible dans toutes les références de l’entreprise, où teams est disponible.

## <a name="location-of-shifts-data"></a>Emplacement des données de décalage

Les données de décalage sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord, en Europe de l’Ouest et en Asie-Pacifique. Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurer les Shifts

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver les équipes au sein de votre organisation

Les Shifts sont activés par défaut pour tous les utilisateurs d’équipes de votre organisation. Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](../../manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.
2. Dans la liste des applications, effectuez l’une des opérations suivantes :

    - Pour désactiver les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **bloquer**.
    - Pour activer les Shifts pour votre organisation, recherchez l’application Shifts, sélectionnez-la, puis cliquez sur **allow**.

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver les équipes pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des équipes, assurez-vous que les Shifts sont activés pour votre organisation dans la page [gérer les applications](../../manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler les équipes dans teams

Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications définies dans une stratégie sont épinglées à la barre de l’application &mdash; , qui se trouve sur le côté du client de bureau teams et dans la partie inférieure des clients mobiles Teams, &mdash; où les utilisateurs peuvent y accéder rapidement et facilement.
 
Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez affecter à des employés terrain dans votre organisation. Par défaut, la stratégie inclut les applications activités, équipes, discussions et appels. 

Pour afficher la stratégie FirstlineWorker, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration de l’application **teams**  >  **App setup policies**.

![Capture d’écran de la stratégie de configuration de l’application FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FirstlineWorker dans le centre d’administration Microsoft teams")

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs

[!INCLUDE [assign-policy](../../includes/assign-policy.md)]

## <a name="search-the-audit-log-for-shifts-events"></a>Effectuer une recherche dans le journal d’audit pour les événements de décalage

**(version d’évaluation)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité de décalage au sein de votre organisation.  Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des [activités de décalage](../../audit-log-events.md#shifts-in-teams-activities) enregistrées dans le journal d’audit, voir [effectuer des recherches dans le journal d’audit pour les événements dans teams](../../audit-log-events.md).

Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com). Pour plus d’informations, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="related-topics"></a>Sujets associés

- [Aide sur les équipes pour les travailleurs terrain](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs dans teams](../../assign-policies.md)
