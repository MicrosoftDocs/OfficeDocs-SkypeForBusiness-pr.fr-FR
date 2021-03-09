---
title: Notes de publication de Microsoft Teams PowerShell
ms.reviewer: brandber
author: BrandBer
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez les dernières modifications dans Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24fa58e50ad42d3204fd4dc1269c8f59a3349d5e
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569396"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notes de publication de Microsoft Teams PowerShell

Cette page fournit le journal des changements de Teams PowerShell le plus récent pour les mises à jour générales et les prévisualisations publiques.

## <a name="release-notes"></a>Notes de publication

> [!NOTE]
> **-preview dans** la colonne version ci-dessous représente les mises à jour de la prévisualisation publique de Teams PowerShell.

| Date | Version | Mises à jour |
|------- | -------------------- | ------------------------------ |
| Mars 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Utilise MSAL pour l’authentification et &'autorisation</li><li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Mezzo et améliorations du lot pour l'Get-Team de la cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Ajout d’une cmdlets de gestion des modèles</li> <li>Retrait du New-CsOnlineSession</li>|
| Février 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Ajout d’une cmdlets de gestion des modèles</li><li>Mezzo et améliorations du lot pour l'Get-Team de la cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Cmdlets de package de stratégies refacteur</li>|
| Décembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Mises à jour de l’cmdlet Nouvelle équipe avec resserr et durée de veille accrues</li>|
| Décembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Mises à jour de l’intégration de Skype Entreprise Online</li><li>Corriger l’invite en double avec Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Ajoute des cmdlets de package de stratégie personnalisé</li><li>Correctifs pour les commandes de chargement de la hiérarchie de ciblage</li>|
| Novembre 2020 | [Prévisualisation 1.1.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Utilise MSAL pour l’authentification et &'autorisation</li><li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Commandes de chargement de hiérarchie de ciblage refacteur pour utiliser un modèle asynchrone</li> <li>L’utilisateur sera invité à deux reprises au cours de l’authentification initiale lorsqu’il n’utilise pas le paramètre d’informations d’identification. Les utilisateurs peuvent transmettre des informations d’identification à l’aide du paramètre -credential pour éviter une invite en double. Ce comportement sera corrigé dans la prochaine version.</li> |
| Septembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Intégration de Skype Entreprise Online Connector</li> |
| Septembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Intégration de Skype Entreprise Online Connector</li> |
| Juillet 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Ajout [d’lets d’affectation de stratégie de groupe](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group)</li> |
| Juin 2020 | [Prévisualisation 1.1.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Intégration de Skype Entreprise Online Connector<li>Get-Team optimisations<li>Fiabilité améliorée</li> |
| Juin 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Ajout d’une cmdlet en préchargement<li>Optimisations .Net Framework</li>   |
| Avril 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Signature d’assembly et authenticode<li>Ajout de Get-CsPolicyPackage<li>Ajout de Get-CsUserPolicyPackage<li>Ajout de Get-CsUserPolicyPackageRecommendation<li>Ajout de Grant-CsUserPolicyPackage<li>Ajout de New-CsBatchPolicyPackageAssignmentOperation<li>Ajout de Set-TeamArchivedState<li>Ajout de Set-TeamPicture<li>Suppression d'Get-TeamHelp</li>  |
| Mars 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Ajout de New-CsBatchPolicyAssignmentOperation</li> |
| Février 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimisations</li>  |

### <a name="cmdlet-availability"></a>Disponibilité des cmdlet

> [!NOTE]
> La liste dans le tableau ci-dessous inclut uniquement des cmdlets qui font partie en natif du module Teams PowerShell. Les cmdlets Teams dans le module S[kype for Business Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) ne s’affichent pas. Toutefois, ces cmdlets étant migrées en natif vers Teams PowerShell, nous les ajouterons à ce tableau.

| Applet de commande | Disponible en prévisualisation publique | Disponible dans GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Oui | **Non** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Oui | Oui |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Oui | **Non**|
| [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Oui | Oui |
| [Disconnect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Oui | Oui |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Oui | Oui |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Oui | **Non** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Oui | Oui |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Oui | Oui |
| [Get-Team](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Oui | Oui |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Oui | Oui|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Oui | **Non** |
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Oui | Oui |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Oui | Oui |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Oui | **Non** |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Oui | Oui |
| [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Oui | Oui |
| [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Oui | Oui |
| [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Oui | Oui |
| [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Oui | Oui |
| [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Oui | Oui |
| [New-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Oui | Oui |
| [New-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Oui | Oui |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Oui | Oui |
| [Remove-Team](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Oui | Oui |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Oui | Oui |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Oui | **Non** |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Oui | Oui |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Oui | **Non** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Oui | **Non**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Oui | Oui |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Oui | **Non** |
| [Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Oui | Oui |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Oui | Oui |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Oui | Oui |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Oui | Oui |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Oui | Oui |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Oui | **Non** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Oui | **Non** |

## <a name="related-topics"></a>Voir aussi

[Aperçu de Teams PowerShell](teams-powershell-overview.md)

[Installation de Teams PowerShell](teams-powershell-install.md)

[Gestion des équipes avec Teams PowerShell](teams-powershell-managing-teams.md)

[Référence de l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
