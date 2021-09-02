---
title: Microsoft Teams Notes de publication de PowerShell
ms.reviewer: gothambi
author: BrandBer
ms.author: gothambi
manager: naanur
ms.date: 08/31/2021
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez les dernières modifications dans Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10a21378f6827e361868b431d2df9249cc7b0eec
ms.sourcegitcommit: 5a4108219dd1b77468b3ef4aff0500cd19473fa5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/01/2021
ms.locfileid: "58852032"
---
# <a name="microsoft-teams-powershell-release-notes"></a>Microsoft Teams Notes de publication de PowerShell

Cette page fournit le dernier Teams de modification de PowerShell pour les mises à jour générales et d’aperçu public.

## <a name="release-notes"></a>Notes de publication

> [!NOTE]
> **-preview** dans la colonne version ci-dessous représente les mises à jour Teams aperçu public PowerShell.

| Date | Version | Mises à jour |
|------- | -------------------- | ------------------------------ |
| Août 2021 | [2.5.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.5.1) |<li>La connexion au jeton Access pour Connect-MicrosoftTeams utilise désormais une matrice de jetons unifiée au lieu de paramètres distincts pour chaque jeton spécifique à une ressource. Pour plus d’informations, cliquez [ici.](/powershell/module/teams/connect-microsoftteams)</li><li>L’échec de connexion interactif Connect-MicrosoftTeams cloudshell a été corrigé. Par défaut, il utilise désormais l’identité de l’utilisateur connecté au lieu d’être invité à se ré-authentification.</li><li>Les cmdlets TeamsUnassignedNumberTreatment sont désormais disponibles.</li><li>Get-CsOnlineDialInConferencingBridge et Set-CsOnlineDialInConferencingBridge cmdlets ont été migrées de l’ancienne implémentation vers les nouvelles API.</li><li>Les versions modernes de Get-CsTenant et Get-CsOnlineUser (avec paramètre d’identité uniquement) ont été publiées. Ils ne émettent plus de propriétés amorties et ont des modifications de mise en forme par rapport à leurs équivalents de remoting.</li><li>Remarque : les New-Team mises à jour liées ont été modifiées à partir de la version 2.5.0 et la version précédente a été fournie afin d’éviter toute rupture de modification.</li>|
| Juillet 2021 | [Prévisualisation 2.4.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.1-preview) |<li>Accorder des cmdlets de changement désormais disponibles.</li><li>De nouvelles cmdlets associées à Voice sont publiées.</li><li>Suppression de l’authentification par empreinte digitale du certificat pour les cmdlets -Cs*</li><li>Correctif de journalisation pour la journalisation des fichiers de toutes les cmdlets.</li><li>Corrige les problèmes avec les cmdlets *TeamChannelUser.</li>|
| Juin 2021 | [Prévisualisation 2.4.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.4.0-preview) |<li>Version d’aperçu uniquement des versions modernes de Get-CsTenant, Get-CsOnlineUser (avec -identity parameter uniquement), Get-CsOnlineDialInConferencingLanguagesSupported et Import-CsOnlineAudioFile.</li><li>Les versions modernes de Get-CsOnlineDialInConferencingLanguagesSupported et Import-CsOnlineAudioFile devraient fonctionner de façon similaire/identique à leurs équivalents de la remoting.</li><li>Les versions modernes de Get-CsTenant et Get-CsOnlineUser (lorsqu’elles sont exécutés avec un paramètre de -identité) ne émettent pas de propriétés déprédées.</li><li>Les versions modernes de Get-CsTenant et Get-CsOnlineUser (lorsqu’elles sont exécutés avec un paramètre de -identity) ont quelques modifications de mise en forme en comparaison de leurs parties de compteur de remoting.</li><li>Releases [Get \| Set \| Grant New \| \| Remove]-CsTeamsAudioConferencingPolicy cmdlets.</li><li>Relâche et dés Get-CsOnlineAudioFile et Remove-CsOnlineAudioFile cmdlets.</li><li>Set-TeamTargetingHierarchy, Remove-TeamTargetingHierarchy, Get-TeamTargetingHierarchyStatus sont désormais disponibles pour Cloud de la communauté du secteur public clients.</li><li>Corrige le point de terminaison appelé par la commande Get-TeamTargetingHierarchyStatus point de terminaison.</li>|
| Mai 2021 | [Prévisualisation 2.3.2](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.2-preview) |<li>Prise en charge de la connexion AccessToken Connecter-MicrosoftTeams. Paramètre Ajouté -AccessTokens qui accepte le tableau de jeton. MSGraph et Teams de ressource sont requis lors de l’utilisation du paramètre AccessTokens.</li><li>Paramètres AadAccessToken et MsAccessToken supprimés.</li>|
| Mai 2021 | [2.3.1](https://www.powershellgallery.com/packages/MicrosoftTeams/2.3.1) |<li>Mettre à jour à partir de . NETCore 2.1 à 3.1</li><li>Ajout d’une cmdlet pour obtenir une région géographique multiple pour les utilisateurs et les groupes</li><li>Correctifs pour l’authentification windows intégrée pour utiliser -AccountId avec Connect-MicrosoftTeams</li><li>Les cmdlets TeamsCallHoldPolicy sont désormais disponibles</li><li>Mises à jour des paramètres d’entrée et des formats de sortie de nombreuses commandes</li><li>Corrige le problème de latence importante lors de la correction des commandes</li><li>Fonctionnalités de package personnalisé GA</li>|
| Avril 2021 | [Prévisualisation 2.2.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.2.0-preview) | <li>Correctifs pour l’authentification Windows intégrée afin d’utiliser -AccountId avec Connecter-MicrosoftTeams.</li><li>Une cmdlet a été ajoutée pour obtenir les détails du nombre total d’événements de notification de modification qui peuvent être envoyés aux utilisateurs.</li><li>Ajout d’une cmdlet pour obtenir une région géographique multiple pour les utilisateurs et les groupes.</li><li>La gestion des valeurs transmises au nom TeamsEnvironment était sensible à la cas. Ce problème a été résolu.</li><li>Principal facteur refacteur de la gestion des sessions distantes dans le module pour faciliter les tests unitaires. Les administrateurs des locataires ne doivent pas avoir à modifier les fonctionnalités.</li>|
| Avril 2021 | [Prévisualisation 2.1.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.1.0-preview) | <li>Correction de la mise en forme de sortie de quelques cmdlets de correction (par exemple, Get-CsTeamsNetworkRoamingPolicy, Get-CsTeamsMeetingPolicy, Get-CsTeamsMesspolicy, et bien plus encore).</li><li>Liste des cmdlets de gestion des stratégies mises à jour.</li>|
| Mars 2021 | [2.0.0](https://www.powershellgallery.com/packages/MicrosoftTeams/2.0.0) | <li>Utilise MSAL pour l’authentification et &'autorisation</li> <li>Connect-MicrosoftTeams point d’entrée de toutes les cmdlets.</li><li>New-csOnlineSession n’est plus disponible. Il a été remplacé par Connecter-MicrosoftTeams.</li><li>Enable-csonlinesessionforreconnection n’est plus nécessaire. La fonctionnalité a été implémentée en natif Teams module PowerShell.</li> <li>Des cmdlets de package de stratégies refacteur et ajoutent une affectation de package de groupe</li><li>Améliorations significatives des performances pour l'Get-Team de la cmdlet</li> <li>Option de journalisation et de débogage améliorée pour les cmdlets existantes </li> <li>Ajout d’une cmdlets de gestion des modèles</li> <li>Retrait du New-CsOnlineSession</li>|
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

[Microsoft Teams des cmdlet](/powershell/teams/)

[Skype Entreprise des cmdlet](/powershell/skype/intro)
