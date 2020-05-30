---
title: Gestion de l’application Shifts pour votre organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
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
ms.openlocfilehash: c2ca24f2176547f83efb6bdce591ac71d516dca9
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416884"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Shifts pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> À compter du 30 juin 2020, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 30 juin 2020. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

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

#### <a name="assign-the-firstlineworker-policy-to-users"></a>Affecter la stratégie FirstlineWorker aux utilisateurs

Pour affecter la stratégie de configuration de l’application FirstlineWorker à un utilisateur :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Sous **stratégie de configuration des applications**, sélectionnez **FirstlineWorker**, puis cliquez sur **appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.
3. Cliquez sur **modifier les paramètres**, sous stratégie de configuration des **applications**, sélectionnez **FirstlineWorker**, puis cliquez sur **appliquer**.  

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration des **applications teams**  >  **Setup policies**.
2. Sélectionnez la stratégie FirstlineWorker en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, sélectionnez **appliquer**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a>Affectez la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe.

Vous pouvez affecter la stratégie de configuration de l’application FirstlineWorker aux membres des utilisateurs d’un groupe, comme un groupe de sécurité, en vous connectant au service Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](../../teams-powershell-overview.md).

Dans cet exemple, nous affectons la stratégie d’installation de l’application FirstlineWorker à tous les membres du groupe d’équipes contoso terrain.

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Obtenez les membres du groupe spécifié.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Affectez la stratégie de configuration de l’application FirstlineWorker à tous les membres de ce groupe.
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="search-the-audit-log-for-shifts-events"></a>Effectuer une recherche dans le journal d’audit pour les événements de décalage

**(version d’évaluation)**

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité de décalage au sein de votre organisation.  Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des [activités de décalage](../../audit-log-events.md#shifts-in-teams-activities) enregistrées dans le journal d’audit, voir [effectuer des recherches dans le journal d’audit pour les événements dans teams](../../audit-log-events.md).

Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com). Pour plus d’informations, voir [activer ou désactiver la recherche dans le journal d’audit](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014). Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="related-topics"></a>Voir aussi

- [Aide sur les équipes pour les travailleurs terrain](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
- [Attribuer des stratégies à vos utilisateurs dans teams](../../assign-policies.md)
