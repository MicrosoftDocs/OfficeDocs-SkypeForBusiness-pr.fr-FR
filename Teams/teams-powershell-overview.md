---
title: Vue d’ensemble de PowerShell teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/06/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
description: Découvrez comment utiliser les contrôles PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bb6a982db4ab3986a423cf958ad8e81105380c
ms.sourcegitcommit: a71ad6762e18267faaaac09533bac80a181102af
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37439582"
---
# <a name="teams-powershell-overview"></a>Vue d’ensemble de PowerShell teams

Microsoft teams est doté d’un ensemble d’outils riches pour gérer le produit par le biais du centre d’administration Microsoft Teams, des contrôles PowerShell et des API de graphique. Ce guide décrit la structure de nos cmdlets PowerShell destinées aux administrateurs informatiques et fournit des pointeurs vers d’autres documents. Notez que les différents rôles d’administrateur d’équipes ont accès à différentes cmdlets. Pour plus d’informations, reportez-vous [à utiliser les rôles d’administrateur de Microsoft teams pour gérer teams](using-admin-roles.md).

## <a name="which-modules-do-you-need-to-use"></a>Quels modules avez-vous besoin d’utiliser ?

Les contrôles PowerShell pour la gestion d’équipes se trouvent dans deux modules PowerShell différents : 
- [Module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) : le module PowerShell teams contient toutes les applets de applet nécessaires pour créer et gérer Teams.  
- [Module PowerShell Skype entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366): le module PowerShell Skype entreprise contient les applets de décision permettant de gérer les stratégies, configurations et autres outils Teams. 

La documentation de référence relative aux contrôles PowerShell indique le module qui contient l’applet de commande que vous étudiez. (Les deux modules seront combinés.)

## <a name="what-can-each-admin-role-do"></a>Que peut faire chaque rôle d’administrateur ?

Lire [utiliser les rôles d’administrateur de Microsoft teams pour gérer les équipes](using-admin-roles.md) et comprendre les applets de applet de cmdlet PowerShell qu’ils peuvent utiliser.

## <a name="creating-and-managing-teams-via-powershell"></a>Création et gestion d’équipes via PowerShell

Les applets de développement pour la création et la gestion d’équipes se trouvent dans le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/). 

Les équipes sont régularisées par les groupes Office 365, ce qui vous permet de créer un groupe lorsque vous créez une équipe. Il existe un ensemble d’applets de construction fourni pour l’utilisation de l’équipe principale et``new-team``de ``get-team``ses ``set-team``paramètres (,,,)``add-teamuser``, ``remove-teamuser``de la gestion des utilisateurs d’équipe (,), ainsi que des cmdlets ``remove-teamchannel``de gestion des canaux de l’équipe (``new-teamchannel``). Toutes ces applets de action peuvent être exécutées en tant qu’utilisateurs finaux, mais elles ne fonctionnent que sur les équipes dont vous êtes membre ou dont vous êtes membre. Si vous êtes un administrateur général ou un administrateur de service Teams, vous pouvez agir sur toutes les équipes de votre organisation.

> Le **GroupID** utilisé dans les applets de applet de module Microsoft teams PowerShell est le même que la ``Get-UnifiedGroup`` propriété **Identity** renvoyée par dans le module Exchange PowerShell.

### <a name="differences-between-preview-and-generally-available-microsoft-teams-powershell-module"></a>Différences entre l’aperçu et le module Microsoft teams PowerShell disponible en général

Lorsque nous avons distribué notre version générale de notre module PowerShell, quelques cmdlets étaient restées dans le module bêta uniquement, comme décrit dans le tableau ci-dessous.

| Applet de commande | Disponible dans Preview | Disponible dans 1,0 |
|------- | -------------------- | ------------------------------ |
| Add-TeamUser | Oui | Oui |
| Connexion-MicrosoftTeams | Oui | Oui |
| Déconnexion-MicrosoftTeams | Oui | Oui |
| Obtenir une équipe | Oui | Oui |
| Get-TeamChannel | Oui | Oui |
| Get-TeamFunSettings | Antérieure à la version de 1,0 uniquement | Non |
| Get-TeamGuestSettings | Antérieure à la version de 1,0 uniquement | Non |
| Get-TeamHelp | Oui | Oui |
| Get-TeamMemberSettings | Antérieure à la version de 1,0 uniquement | Non |
| Get-TeamMessagingSettings | Antérieure à la version de 1,0 uniquement | Non |
| Get-TeamUser | Oui | Oui |
| Nouvelle équipe | Oui | Oui |
| Nouveau-TeamChannel | Oui | Oui |
| Supprimer-équipe | Oui | Oui |
| Remove-TeamChannel | Oui | Oui |
| Remove-TeamUser | Oui | Oui |
| Ensemble d’équipes | Oui | Oui |
| Set-TeamChannel | Oui | Oui |
| Set-TeamFunSettings | Antérieure à la version de 1,0 uniquement | Non |
| Set-TeamGuestSettings | Antérieure à la version de 1,0 uniquement | Non |
| Set-TeamMemberSettings | Antérieure à la version de 1,0 uniquement | Non |
| Set-TeamMessagingSettings | Antérieure à la version de 1,0 uniquement | Non |
| Set-TeamPicture | Oui | Non, planifié |


## <a name="managing-policies-via-powershell"></a>Gestion des stratégies via PowerShell

Les applets de décision pour la gestion des stratégies se trouvent dans le [module cmdlet Skype entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

> [!NOTE]
> Les applets de connexion seront disponibles dans votre session PowerShell une fois que vous vous connectez à Skype entreprise online. Pour plus d’informations, reportez-vous à la rubrique [gestion de Skype entreprise Online avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell). 

Une stratégie est un ensemble de paramètres qui peuvent être appliqués de façon granulaire aux utilisateurs individuels. Chaque type de stratégie dispose de son propre ensemble d’applets de jeu permettant de créer, d’afficher, de supprimer et de mettre à jour les stratégies, puis de les affecter aux utilisateurs. La structure générale est la suivante :

- OBTENIR des commandes (par exemple ``Get-CsTeamsMeetingPolicy``,) : renvoi des documents de stratégie que vous pouvez affecter au sein de votre organisation, les stratégies créées par Microsoft à utiliser et les stratégies personnalisées que vous avez créées.
   > Si vous souhaitez rechercher uniquement les stratégies personnalisées que vous avez créées au sein de votre organisation, ``-Filter "tag:*"``vous pouvez utiliser.

- De nouvelles commandes (par exemple ``New-CsTeamsMeetingPolicy``,) : vous permettent de créer de nouvelles stratégies pour votre organisation, qui sont ensuite disponibles pour être affectées aux utilisateurs de votre organisation. Toutes les stratégies ne prennent pas en charge la création de stratégies personnalisées. En règle générale, il s’agit de veiller à ce que les stratégies que vous utilisez au sein de votre organisation possèdent une combinaison de paramètres prise en charge.

- Les commandes SET (par exemple ``Set-CsTeamsMeetingPolicy``,) : vous permettent de définir des valeurs particulières sur une stratégie donnée. Certaines stratégies n’ont pas de commandes définies disponibles ou contiennent des paramètres qui ne peuvent pas être personnalisés dans la stratégie. Chaque description PowerShell sera appelée quels sont les paramètres qui ne peuvent pas être personnalisés. 
   > Pour modifier la stratégie qui sera affectée par défaut aux utilisateurs de votre organisation pour lesquels aucune stratégie personnalisée n’est affectée, exécutez ``Set-Cs<PolicyName> -Identity Global``.

- SUPPRIMER des commandes (par exemple ``Remove-CsTeamsMeetingPolicy``,) : vous pouvez utiliser cette applet de commande pour supprimer une stratégie personnalisée qui a été créée dans votre client. Si vous supprimez une stratégie personnalisée qui a été attribuée à au moins un utilisateur au sein de votre organisation, cet utilisateur sera renvoyé à la stratégie globale.
   > Vous ne pouvez pas supprimer réellement la politique globale de votre organisation, mais si vous voulez rétablir les paramètres par défaut fournis par Microsoft dans votre organisation, vous pouvez exécuter ``Remove-Cs<PolicyName> -Identity Global``.

- Commande d’attribution (par exemple ``Grant-CsTeamsMeetingPolicy``,) : vous permet d’affecter une stratégie à un utilisateur particulier.
   > Pour supprimer une affectation de stratégie personnalisée et permettre à l’utilisateur de revenir à la stratégie par défaut de votre ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null``organisation, exécutez.

> [!TIP]
> Toutes les stratégies n’autorisent pas la création de stratégies personnalisées, et certaines stratégies ne peuvent pas être personnalisées (de sorte que vous ne pouvez pas définir de ``set-`` valeur ``new-``personnalisée pendant et). La documentation de l’applet de connexion spécifique peut faire l’objet d’un appel si des paramètres ne sont pas disponibles pour les clients.

Paramètres courants :

- **Identity**: ``Get-``pour ``Set-``, ``New-``, et ``Remove-``, le paramètre **Identity** fera toujours référence à une instance de stratégie spécifique. Pour ``Grant``le paramètre **Identity** , fait référence à un objet utilisateur spécifique auquel la stratégie est appliquée.

<!--more info here?-->

## <a name="managing-configurations-via-powershell"></a>Gestion des configurations via PowerShell

Les applets de configuration de la gestion de votre configuration se trouvent dans le [module cmdlet Skype entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Les configurations sont des compartiments des paramètres conservés dans le service qui ne peuvent pas être spécifiés à un niveau utilisateur. Les paramètres s’appliquent toujours à l’ensemble de l’organisation. Votre configuration globale est la seule configuration efficace au sein de votre organisation. Chaque type de configuration est fourni avec deux cmdlets principales :

- ``Get-Cs<ConfigurationName>``(par exemple, ``Get-CsTeamsClientConfiguration``) : 

- Définissez les commandes (par exemple ``Set-CsTeamsClientConfiguration``,) : définissez les propriétés dans la configuration de ce type. Spécifiez les paramètres que vous voulez modifier.
   > Vous pouvez faire référence à la configuration que vous modifiez de l’une des deux manières suivantes : en spécifiant-**Identity global**ou en exécutant ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>``.

## <a name="other-powershell-tools"></a>Autres outils PowerShell

Vous trouverez des instructions détaillées sur l’utilisation de tous les contrôles PowerShell pour la gestion de Microsoft teams et de Skype entreprise, notamment la description détaillée des paramètres de chaque stratégie dans les informations de référence sur l’applet de commande [Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) et [Skype pour Référence sur les applets de décision](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="learn-more"></a>En savoir plus

- [Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)
- [Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
- [Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md)
