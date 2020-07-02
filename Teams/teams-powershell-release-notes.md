---
title: Notes de publication de Microsoft teams PowerShell
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
description: En savoir plus sur les dernières modifications dans teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cda7c9db774632317cb568a6b448b4fc04b3b5ff
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944098"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notes de publication de Microsoft teams PowerShell

Cette page fournit le journal des modifications PowerShell d’teams pour les versions générales et d’aperçu public.

## <a name="release-notes"></a>Notes de publication

> [!NOTE]
> **-preview** dans la colonne version ci-dessous représente mises à jour d’équipes PowerShell public preview.

| Date | Version | Mises à jour |
|------- | -------------------- | ------------------------------ |
| 2020 juin | [1.1.0-Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.0-preview) | <li>Intégration de connecteur Skype entreprise Online<li>Optimisations de la mise en équipe<li>Fiabilité améliorée</li> |
| 2020 juin | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Ajout d’une cmdlet de préchargement<li>Optimisations de .NET Framework</li>   |
| 2020 avril | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Authenticode et signature de l’assembly<li>Get-CsPolicyPackage ajoutées<li>Get-CsUserPolicyPackage ajoutées<li>Get-CsUserPolicyPackageRecommendation ajoutées<li>Octroi-CsUserPolicyPackage<li>Ajout de nouveau-CsBatchPolicyPackageAssignmentOperation<li>Ajout de jeu-TeamArchivedState<li>Ajout de jeu-TeamPicture<li>Suppression de Get-TeamHelp</li>  |
| 2020 mars | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Ajout de nouveau-CsBatchPolicyAssignmentOperation</li> |
| 2020 fév | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Optimisations de la mise en équipe</li>  |

### <a name="cmdlet-availability"></a>Disponibilité des cmdlets

> [!NOTE]
> La liste figurant dans le tableau ci-dessous inclut uniquement les applets de applet qui s’exécutent en mode natif dans le module PowerShell Teams. Les applets de connexion teams dans le[module S kype entreprise Online Connector](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps) ne sont pas affichées. Toutefois, étant donné que les applets de cmdlet sont migrées en mode natif dans teams PowerShell, nous les ajoutons à cette table.

| Applet de commande | Disponible en préversion publique | Disponible en GA |
| -| -- | --|
| [Add-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/add-teamchanneluser?view=teams-ps) | Oui | **Non** |
| [Add-TeamUser](https://docs.microsoft.com/powershell/module/teams/add-teamuser?view=teams-ps) | Oui | Oui |
| [Add-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/add-teamsappinstallation?view=teams-ps) | Oui | **Non**|
| [Connexion-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) | Oui | Oui |
| [Déconnexion-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/disconnect-microsoftteams?view=teams-ps) | Oui | Oui |
| [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation?view=teams-ps) | Oui | Oui |
| [Get-CsGroupPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignmentoperation?view=teams-ps) | Oui | **Non** |
| [Get-CsOnlinePowerShellEndpoint](https://docs.microsoft.com/powershell/module/teams/get-csonlinepowershellendpoint?view=teams-ps) | Oui | **Non** |
| [Get-CsPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-cspolicypackage?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackage?view=teams-ps) | Oui | Oui |
| [Get-CsUserPolicyPackageRecommendation](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicypackagerecommendation?view=teams-ps) | Oui | Oui |
| [Obtenir une équipe](https://docs.microsoft.com/powershell/module/teams/get-team?view=teams-ps) | Oui | Oui |
| [Get-TeamChannel](https://docs.microsoft.com/powershell/module/teams/get-teamchannel?view=teams-ps) | Oui | Oui|
| [Get-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/get-teamchanneluser?view=teams-ps) | Oui | Oui|
| [Get-TeamUser](https://docs.microsoft.com/powershell/module/teams/get-teamuser?view=teams-ps) | Oui | Oui |
| [Get-TeamsApp](https://docs.microsoft.com/powershell/module/teams/get-teamsapp?view=teams-ps) | Oui | Oui |
| [Get-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/get-teamsappinstallation?view=teams-ps) | Oui | Oui |
| [Grant-CsUserPolicyPackage](https://docs.microsoft.com/powershell/module/teams/grant-csuserpolicypackage?view=teams-ps) | Oui | Oui |
| [Nouveau-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) | Oui | Oui |
| [Nouveau-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps) | Oui | **Non** |
| [Nouveau-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation?view=teams-ps) | Oui | Oui |
| [Nouveau-CsOnlineSession](https://docs.microsoft.com/powershell/module/teams/new-csonlinesession?view=teams-ps) | Oui | **Non** |
| [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/new-team?view=teams-ps) | Oui | Oui |
| [Nouveau-TeamChannel](https://docs.microsoft.com/powershell/module/teams/new-channel?view=teams-ps) | Oui | Oui |
| [Nouveau-TeamsApp](https://docs.microsoft.com/powershell/module/teams/new-teamsapp?view=teams-ps) | Oui | Oui |
| [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment?view=teams-ps) | Oui | **Non** |
| [Supprimer-équipe](https://docs.microsoft.com/powershell/module/teams/remove-team?view=teams-ps) | Oui | Oui |
| [Remove-TeamChannel](https://docs.microsoft.com/powershell/module/teams/remove-teamchannel?view=teams-ps) | Oui | Oui |
| [Remove-TeamChannelUser](https://docs.microsoft.com/powershell/module/teams/remove-teamchanneluser?view=teams-ps) | Oui | Oui |
| [Remove-TeamsApp](https://docs.microsoft.com/powershell/module/teams/remove-teamsapp?view=teams-ps) | Oui | Oui |
| [Remove-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/remove-teamsappinstallation?view=teams-ps) | Oui | **Non** |
| [Remove-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/remove-teamtargetinghierarchy?view=teams-ps) | Oui | **Non**|
| [Remove-TeamUser](https://docs.microsoft.com/powershell/module/teams/remove-teamuser?view=teams-ps) | Oui | Oui |
| [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment?view=teams-ps) | Oui | **Non** |
| [Ensemble d’équipes](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps) | Oui | Oui |
| [Set-TeamArchivedState](https://docs.microsoft.com/powershell/module/teams/set-teamarchivedstate?view=teams-ps) | Oui | Oui |
| [Set-TeamChannel](https://docs.microsoft.com/powershell/module/teams/set-teamchannel?view=teams-ps) | Oui | Oui |
| [Set-TeamPicture](https://docs.microsoft.com/powershell/module/teams/set-teampicture?view=teams-ps) | Oui | Oui |
| [Set-TeamsApp](https://docs.microsoft.com/powershell/module/teams/set-teamapp?view=teams-ps) | Oui | Oui |
| [Set-TeamTargetingHierarchy](https://docs.microsoft.com/powershell/module/teams/set-teamtargetinghierarchy?view=teams-ps) | Oui | **Non** |
| [Update-TeamsAppInstallation](https://docs.microsoft.com/powershell/module/teams/update-teamappinstallation?view=teams-ps) | Oui | **Non** |

## <a name="related-topics"></a>Sujets associés

[Aperçu de Teams PowerShell](teams-powershell-overview.md)

[Installation de PowerShell teams](teams-powershell-install.md)

[Gestion des équipes avec PowerShell teams](teams-powershell-managing-teams.md)

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
