---
title: Microsoft Teams Notes de publication de PowerShell
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
ms.openlocfilehash: f319e95b4b68c7b9a20c8c6fff238f70878e7a32
ms.sourcegitcommit: a628b22c9a0ef3bcd7dee3f308a79b4c427872cc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2021
ms.locfileid: "52491801"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Notes de publication de PowerShell

Cette page fournit le dernier Teams de modification de PowerShell pour les mises à jour générales et les prévisualisations publiques.

## <a name="release-notes"></a>Notes de publication

> [!NOTE]
> **-preview** dans la colonne version ci-dessous représente les mises à jour Teams aperçu public PowerShell.

| Date | Version | Mises à jour |
|------- | -------------------- | ------------------------------ |
| Mai 2021 | [3.0.0] |<li>Mises à jour de connexion AccessToken avec Connect-MicrosoftTeams tableau de jetons unifié au lieu de paramètres de jeton d’accès spécifiques aux ressources</li><li>Toutes les références AADGraph ont été supprimées car AADGraph approche de sa fin de vie</li>|
| Mai 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Mettre à jour à partir de . NETCore 2.1 à 3.1</li><li>Ajout d’une cmdlet pour obtenir une région géographique multiple pour les utilisateurs et les groupes</li><li>Correctifs pour l’authentification windows intégrée pour utiliser -AccountId avec Connect-MicrosoftTeams</li><li>Les cmdlets TeamsCallHoldPolicy sont désormais disponibles</li><li>Mises à jour des paramètres d’entrée et des formats de sortie de nombreuses commandes</li><li>Corrige le problème de latence importante lors de la correction des commandes</li><li>Fonctionnalités de package personnalisé GA</li>|
| Avril 2021 | [Prévisualisation 2.2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Correctifs pour l’authentification Windows intégrée afin d’utiliser -AccountId avec Connecter-MicrosoftTeams.</li><li>Une cmdlet a été ajoutée pour obtenir les détails du nombre total d’événements de notification de modification qui peuvent être envoyés aux utilisateurs.</li><li>Ajout d’une cmdlet pour obtenir une région géographique multiple pour les utilisateurs et les groupes.</li><li>La gestion des valeurs transmises au nom TeamsEnvironment était sensible à la cas. Ce problème a été résolu.</li><li>Principal facteur refacteur de la gestion des sessions distantes dans le module pour faciliter les tests unitaires. Les administrateurs des locataires ne doivent pas avoir à modifier les fonctionnalités.</li>|
| Avril 2021 | [Prévisualisation 2.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Correction de la mise en forme des cmdlets existantes (par exemple, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMess premierPolicy, et bien plus encore).</li><li>Liste des cmdlets de gestion des stratégies mises à jour.</li>|
| Mars 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Utilise MSAL pour l’authentification et &'autorisation</li> <li>Connect-MicrosoftTeams point d’entrée de toutes les cmdlets.</li><li>New-csOnlineSession n’est plus disponible. Il a été remplacé par Connecter-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection n’est plus nécessaire. La fonctionnalité a été implémentée en natif Teams module PowerShell.</li> <li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Améliorations significatives des performances pour l'Get-Team de cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Ajout d’une cmdlets de gestion des modèles</li> <li>Retrait du New-CsOnlineSession</li>|
| Février 2021 | [1.1.11-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.11-preview) | <li>Ajout d’une cmdlets de gestion des modèles</li><li>Mezzo et améliorations du lot pour l'Get-Team de la cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Cmdlets de package de stratégies refacteur</li>|
| Décembre 2020 | [1.1.10-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.10-preview) | <li>Mises à jour de la cmdlet Nouvelle équipe avec resserr et durée de veille accrues</li>|
| Décembre 2020 | [1.1.9-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.9-preview) | <li>Mises à jour de l’intégration Skype Entreprise Online</li><li>Corriger l’invite en double à l'Connect-Microsoft Teams</li>|
| Novembre 2020 | [1.1.8-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.8-preview) | <li>Ajoute des cmdlets de package de stratégie personnalisé</li><li>Correctifs pour les commandes de chargement de la hiérarchie de ciblage</li>|
| Novembre 2020 | [Prévisualisation 1.1.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.7-preview) | <li>Utilise MSAL pour l’authentification et &'autorisation</li><li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Commandes de chargement de hiérarchie de ciblage refacteur pour utiliser un modèle asynchrone</li> <li>L’utilisateur sera invité à deux reprises au cours de l’authentification initiale lorsqu’il n’utilise pas le paramètre d’informations d’identification. Les utilisateurs peuvent transmettre des informations d’identification à l’aide du paramètre -credential pour éviter une invite en double. Ce comportement sera corrigé dans la prochaine version.</li> |
| Septembre 2020 | [1.1.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.6) | <li>Skype Entreprise Intégration de Online Connector</li> |
| Septembre 2020 | [1.1.5-preview](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.5-preview) | <li>Skype Entreprise Intégration de Online Connector</li> |
| Juillet 2020 | [1.1.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.4) | <li>Ajout [d’lets d’affectation de stratégie de groupe](./assign-policies.md#assign-a-policy-to-a-group)</li> |
| Juin 2020 | [Prévisualisation 1.1.3](https://www.powershellgallery.com/packages/MicrosoftTeams/1.1.3-preview) | <li>Skype Entreprise Intégration de Online Connector<li>Get-Team optimisations<li>Fiabilité améliorée</li> |
| Juin 2020 | [1.0.7](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.7) | <li>Ajout d’une cmdlet en préchargement<li>Optimisations .Net Framework</li>   |
| Avril 2020 | [1.0.6](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.6) | <li>Signature d’assembly et d’authentification authentifiés<li>Ajout de Get-CsPolicyPackage<li>Ajout de Get-CsUserPolicyPackage<li>Ajout de Get-CsUserPolicyPackageRecommendation<li>Ajout de Grant-CsUserPolicyPackage<li>Ajout de New-CsBatchPolicyPackageAssignmentOperation<li>Ajout de Set-TeamArchivedState<li>Ajout de Set-TeamPicture<li>Suppression d'Get-TeamHelp</li>  |
| Mars 2020 | [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5) |<li>Ajout de New-CsBatchPolicyAssignmentOperation</li> |
| Février 2020 | [1.0.4](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.4) | <li>Get-Team optimisations</li>  |

## <a name="related-topics"></a>Sujets associés

[Aperçu de Teams PowerShell](teams-powershell-overview.md)

[Installation Teams PowerShell](teams-powershell-install.md)

[Gestion des Teams à l’Teams PowerShell](teams-powershell-managing-teams.md)

[Microsoft Teams des cmdlet](/powershell/teams/?view=teams-ps)

[Skype Entreprise des cmdlet](/powershell/skype/intro?view=skype-ps)
