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
ms.openlocfilehash: 9687dcdca15507caad0c52ef13feb2c12fb61e9a
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768336"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Notes de publication de Microsoft Teams PowerShell

Cette page fournit le journal des changements de Teams PowerShell le plus récent pour les mises à jour générales et les prévisualisations publiques.

## <a name="release-notes"></a>Notes de publication

> [!NOTE]
> **-preview dans** la colonne Version ci-dessous représente les mises à jour de la prévisualisation publique de Teams PowerShell.

| Date | Version | Mises à jour |
|------- | -------------------- | ------------------------------ |
| Avril 2021 | [Prévisualisation 2.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Correction de la mise en forme des cmdlets existantes (par exemple, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMesspolicy, et bien plus encore).</li><li>Liste des cmdlets de gestion des stratégies mises à jour.</li>|
| Mars 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Utilise MSAL pour l'authentification et &'autorisation</li> <li>Connect-MicrosoftTeams point d'entrée de toutes les cmdlets.</li><li>New-csOnlineSession n'est plus disponible. Il a été remplacé par Connect-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection n'est plus nécessaire. La fonctionnalité a été implémentée en natif dans le module Teams PowerShell.</li> <li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Améliorations significatives des performances pour l'Get-Team de cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Ajout d'une cmdlets de gestion des modèles</li> <li>Retrait du New-CsOnlineSession</li>|
| Février 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Ajout d'une cmdlets de gestion des modèles</li><li>Mezzo et améliorations du lot pour l'Get-Team de la cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Cmdlets de package de stratégies refacteur</li>|
| Décembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Mises à jour de la cmdlet Nouvelle équipe avec resserr et durée de veille accrues</li>|
| Décembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Mises à jour de l'intégration de Skype Entreprise Online</li><li>Corriger l'invite en double avec Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Ajoute des cmdlets de package de stratégie personnalisé</li><li>Correctifs pour les commandes de chargement de la hiérarchie de ciblage</li>|
| Novembre 2020 | [1.1.7-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Utilise MSAL pour l'authentification et &'autorisation</li><li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Commandes de chargement de hiérarchie de ciblage refacteur pour utiliser un modèle asynchrone</li> <li>L'utilisateur sera invité à deux reprises au cours de l'authentification initiale lorsqu'il n'utilise pas le paramètre d'informations d'identification. Les utilisateurs peuvent transmettre des informations d'identification à l'aide du paramètre -credential pour éviter une invite en double. Ce comportement sera corrigé dans la prochaine version.</li> |
| Septembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Intégration de Skype Entreprise Online Connector</li> |
| Septembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Intégration de Skype Entreprise Online Connector</li> |
| Juillet 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Ajout [d'lets d'affectation de stratégie de groupe](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Juin 2020 | [1.1.3-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Intégration de Skype Entreprise Online Connector<li>Get-Team optimisations<li>Fiabilité améliorée</li> |
| Juin 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Ajout d'une cmdlet en préchargement<li>Optimisations .Net Framework</li>   |
| Avril 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Signature d'assembly et authenticode<li>Ajout de Get-CsPolicyPackage<li>Ajout de Get-CsUserPolicyPackage<li>Ajout de Get-CsUserPolicyPackageRecommendation<li>Ajout de Grant-CsUserPolicyPackage<li>Ajout de New-CsBatchPolicyPackageAssignmentOperation<li>Ajout de Set-TeamArchivedState<li>Ajout de Set-TeamPicture<li>Suppression d'Get-TeamHelp</li>  |
| Mars 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Ajout de New-CsBatchPolicyAssignmentOperation</li> |
| Février 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimisations</li>  |

## <a name="related-topics"></a>Sujets associés

[Aperçu de Teams PowerShell](teams-powershell-overview.md)

[Installation de Teams PowerShell](teams-powershell-install.md)

[Gestion des équipes avec Teams PowerShell](teams-powershell-managing-teams.md)

[Référence de l'cmdlet Microsoft Teams](/powershell/teams/?view=teams-ps)

[Référence de l'cmdlet Skype Entreprise](/powershell/skype/intro?view=skype-ps)
