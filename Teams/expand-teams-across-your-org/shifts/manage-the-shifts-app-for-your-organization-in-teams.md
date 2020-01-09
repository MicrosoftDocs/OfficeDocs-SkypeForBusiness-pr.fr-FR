---
title: Gérer l’application Shifts pour votre organisation dans Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application Shifts dans teams pour terrain travailleurs de votre organisation.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4ed7f4bc282686c31f2f9c2239fbe6326e5151f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992541"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Shifts pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> À compter du 31 décembre 2019, Microsoft StaffHub sera supprimé. Nous développons des fonctionnalités StaffHub dans Microsoft Teams. Aujourd’hui, teams inclut l’application Shifts pour la gestion des plannings et des fonctionnalités supplémentaires seront déployées dans le temps. StaffHub s’arrêtera de fonctionner pour tous les utilisateurs du 31 décembre 2019. Tout utilisateur essayant d’ouvrir StaffHub verra s’afficher un message lui indiquant de télécharger Teams. Pour en savoir plus, consultez la rubrique [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

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

Les Shifts sont activés par défaut pour tous les utilisateurs d’équipes de votre organisation. Vous pouvez activer ou désactiver l’application à l’échelle de l’organisation à l’aide des paramètres à l’échelle de l’organisation dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations** des **applications teams**.
2. Cliquez sur **paramètres à l’échelle de l’organisation**.
3. Dans le panneau Paramètres de l' **organisation** , sous **applications bloquées**, effectuez l’une des opérations suivantes :

    - Pour désactiver les Shifts pour votre organisation, recherchez l’application Shifts, puis cliquez sur **Ajouter** pour l’ajouter à la liste applications bloquées.
    - Pour activer les Shifts pour votre organisation, supprimez l’application Shifts de la liste des applications bloquées.
4. Cliquez sur **Enregistrer**. 

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a>Activer ou désactiver les équipes pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des équipes, assurez-vous que les Shifts sont activés pour votre organisation dans les paramètres à l’échelle de l’organisation, puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](../../teams-app-permission-policies.md).

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser la stratégie de configuration de l’application FirstlineWorker pour épingler les équipes dans teams

Les stratégies de configuration des applications vous permettent de personnaliser teams afin de mettre en évidence les applications les plus importantes pour les utilisateurs de votre organisation. Les applications définies dans une stratégie sont épinglées à la barre&mdash;de l’application, qui se trouve sur le côté du client de bureau teams et dans la&mdash;partie inférieure des clients mobiles Teams, où les utilisateurs peuvent y accéder rapidement et facilement. 
 
Teams inclut une stratégie intégrée de configuration de l’application FirstlineWorker que vous pouvez affecter à des employés terrain dans votre organisation. Par défaut, la stratégie inclut les applications activités, équipes, discussions et appels. 

Pour afficher la stratégie FirstlineWorker, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies de configuration**de l’application **teams** > .

![Capture d’écran de la stratégie de configuration de l’application FirstlineWorker](../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie de configuration de l’application FirstlineWorker dans le centre d’administration Microsoft teams")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Affecter la stratégie FirstlineWorker à des utilisateurs individuels

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies affectées**, choisissez **modifier**.
3. Sous **stratégie de configuration des applications teams**, sélectionnez **FirstlineWorker**, puis cliquez sur **Enregistrer**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>Affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs d’un groupe

Vous pouvez affecter la stratégie de configuration de l’application FirstlineWorker aux utilisateurs d’un groupe, tel qu’un groupe de sécurité, en vous connectant au service Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](../../teams-powershell-overview.md).

Dans cet exemple, nous affectons la stratégie de configuration de l’application FirstlineWorker à tous les utilisateurs du groupe d’équipes contoso terrain.

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
Assignez tous les utilisateurs du groupe à la stratégie de configuration de l’application FirstlineWorker.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="related-topics"></a>Voir aussi
- [Aide sur les équipes pour les travailleurs terrain](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
