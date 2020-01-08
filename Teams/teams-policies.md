---
title: Gérer les stratégies d’équipes dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer les stratégies d’équipe dans votre organisation pour contrôler ce que les utilisateurs peuvent faire dans les équipes et les canaux.
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: cd107de8b253ca2c5adfe1b23ed8484f152a5f5e
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962982"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Gérer les stratégies d’équipes dans Microsoft teams

En tant qu’administrateur, vous pouvez utiliser les stratégies d’équipe de Microsoft teams pour contrôler ce que peuvent faire les utilisateurs de votre organisation dans les équipes et les canaux. Par exemple, vous pouvez définir si les utilisateurs sont autorisés à découvrir des équipes privées dans les résultats de la recherche et dans la Galerie d’équipes et si les utilisateurs sont autorisés à créer des canaux privés.

Pour gérer les stratégies d’équipe, **accédez à** > **stratégies** teams teams dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer des stratégies personnalisées et les affecter à des utilisateurs. Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée.

Vous pouvez modifier la stratégie globale ou créer et attribuer une stratégie personnalisée. Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur. Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur. Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.

## <a name="create-a-custom-teams-policy"></a>Créer une stratégie d’équipe personnalisée

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.
2. Cliquez sur **Ajouter**.
3. Entrez le nom et la description de la stratégie.

    ![Capture d’écran des paramètres de stratégie d’équipe](media/teams-policies.png)
4. Choisissez les paramètres de votre choix :

- **Découvrir les équipes privées**:<a name="discoverteams"> </a> activez ce paramètre pour autoriser les utilisateurs à découvrir les équipes privées dans les résultats de la recherche et dans la Galerie d’équipes.
- **Créer des canaux privés**: <a name="createchannels"> </a>activez ce paramètre pour autoriser les utilisateurs à créer des canaux privés.

5. Cliquez sur **Enregistrer**.

## <a name="edit-a-teams-policy"></a>Modifier une stratégie d’équipe

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Activez ou désactivez les paramètres souhaités, puis cliquez sur **Enregistrer**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Attribuer une stratégie d’équipe personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.

### <a name="assign-a-custom-teams-policy-to-a-user"></a>Attribuer une stratégie d’équipe personnalisée à un utilisateur

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **stratégies d’équipe**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.

Pour attribuer une stratégie d’équipe personnalisée à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, **accédez à** > **stratégies teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a>Attribuer une stratégie d’équipe personnalisée aux utilisateurs d’un groupe

Vous pouvez assigner une stratégie d’équipe personnalisée à plusieurs utilisateurs que vous avez déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité. Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).

Dans cet exemple, nous affectons une stratégie équipes appelée politique équipes marketing à tous les utilisateurs du groupe marketing de contoso.  

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
Obtenez les membres du groupe spécifié.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière. Dans cet exemple, il s’agit de la stratégie d’équipes marketing.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="related-topics"></a>Voir aussi

- [Gérer la découverte des équipes privées dans Teams](manage-discovery-of-private-teams.md)
- [Canaux privés dans teams](private-channels.md)
