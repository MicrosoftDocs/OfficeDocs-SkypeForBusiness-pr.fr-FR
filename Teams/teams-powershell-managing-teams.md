---
title: Gérer Teams avec Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment gérer Microsoft Teams à l’aide de Teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 09d11b2c697ba57ea161d0ce961cf5ba73794617
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852175"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gérer Teams avec Microsoft Teams PowerShell

Cet article vous explique comment utiliser Microsoft Teams PowerShell pour gérer Teams et Skype Entreprise. 

Utilisez ces recommandations conjointement avec la référence de [l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps) et la référence de l’cmdlet [Skype Entreprise.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

## <a name="create-and-manage-teams-using-powershell"></a>Créer et gérer des équipes à l’aide de PowerShell

Les cmdlets de création et de gestion des équipes sont dans le [module Microsoft Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/)

Teams est backed by Office 365 Groups, so when you create a team, you create a group. Un ensemble d’lets est fourni pour l’exploitation de l’équipe principale et de ses paramètres (, , ), la gestion des utilisateurs de l’équipe ( , ), ainsi que des ``new-team`` ``get-team``  ``set-team`` ``add-teamuser`` ``remove-teamuser`` cmdlets ``new-teamchannel`` pour la gestion des canaux de l’équipe ( , ``remove-teamchannel`` ). Toutes ces cmdlets peuvent être exécutés en tant qu’utilisateurs finaux, mais elles ne fonctionnent que sur les équipes dont vous êtes propriétaire ou dont vous êtes membre. Si vous êtes administrateur général ou administrateur de services Teams, vous serez en mesure d’agir sur toutes les équipes de votre organisation.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department"
```

> Le **GroupId utilisé** dans les cmdlets de module Microsoft Teams PowerShell est identique à la propriété **Identity** renvoyée par le module ``Get-UnifiedGroup`` Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Gérer les stratégies via PowerShell

> [!NOTE]
> - Skype Entreprise Online Connector est en cours de consolidation dans Teams PowerShell. Elle est actuellement disponible en prévisualisation publique. Dans le temps, les cmdlets Skype Entreprise Online qui s’appliquent à Teams seront disponibles en natif dans le module Teams PowerShell. Les étapes d’installation sont disponibles dans [l’article Installer Teams PowerShell.](teams-powershell-install.md)
>
> - Les cmdlets seront disponibles dans votre session PowerShell une fois que vous serez connecté à Skype Entreprise Online. Pour plus d’informations, [consultez Gérer Skype Entreprise Online avec PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

Recherchez les cmdlets de gestion des stratégies dans le [module d’cmdlet Skype Entreprise.](https://www.microsoft.com/download/details.aspx?id=39366)

Une stratégie est un groupe de paramètres qui peuvent être appliqués de façon granulaire à des utilisateurs individuels. Chaque type de stratégie possède son propre ensemble d’lets pour la création, l’affichage, la suppression et la mise à jour des stratégies proprement dits, puis l’attribution de ces stratégies aux utilisateurs. La structure générale est la :

- Commandes **GET** (par exemple,) : renvoie les documents de stratégie que vous pouvez attribuer dans votre organisation, y compris les stratégies créées par Microsoft que vous pouvez utiliser, ainsi que les stratégies personnalisées que vous avez ``Get-CsTeamsMeetingPolicy`` créées.
   - Pour rechercher uniquement les stratégies personnalisées que vous avez créées dans votre organisation, ``-Filter "tag:*"`` utilisez.

- **NOUVELLES** commandes (par exemple, ) : crée de nouvelles stratégies que votre organisation doit ``New-CsTeamsMeetingPolicy`` affecter aux utilisateurs de votre organisation. Toutes les stratégies ne supportent pas la création de stratégies personnalisées. Il s’agit souvent de vous assurer que les stratégies que vous utilisez dans votre organisation utilisent une combinaison de paramètres prise en charge.

- **Commandes SET** (par exemple, ``Set-CsTeamsMeetingPolicy`` ) : définit des valeurs spécifiques sur une stratégie donnée. Certaines stratégies ne disposent pas de commandes SET ou contiennent des paramètres qui ne peuvent pas être personnalisés dans la stratégie. Les descriptions de PowerShell vous indiquent quels paramètres ne peuvent pas être personnalisés. 
   - Pour modifier la stratégie qui sera par défaut affectée aux utilisateurs de votre organisation pour qui une stratégie personnalisée n’est pas attribuée, ``Set-Cs<PolicyName> -Identity Global`` exécutez.

- **Commandes** REMOVE (par exemple) : supprime une stratégie personnalisée créée ``Remove-CsTeamsMeetingPolicy`` dans votre client. Si vous supprimez une stratégie personnalisée affectée à au moins un utilisateur de votre organisation, cet utilisateur revenira à la stratégie globale.
   - Vous ne pouvez pas vraiment supprimer la stratégie globale de votre organisation, mais si vous voulez rétablir les paramètres par défaut fournis par Microsoft pour la stratégie globale de votre organisation, ``Remove-Cs<PolicyName> -Identity Global`` exécutez.

- **Commande GRANT** (par exemple, ``Grant-CsTeamsMeetingPolicy`` ) : affecte une stratégie à un utilisateur particulier.
   - Pour supprimer une affectation de stratégie personnalisée et faire en sorte que l’utilisateur revenir à la stratégie par défaut dans votre organisation, ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` exécutez.

> [!TIP]
> Toutes les stratégies n’autorisent pas la création de stratégies personnalisées, et certaines stratégies ont des paramètres que vous ne pouvez pas personnaliser (de sorte que vous pouvez afficher le paramètre, mais ne pouvez pas définir de valeur personnalisée pendant ``set-`` ``new-`` et). La documentation de chaque cmdlet vous demande si les paramètres peuvent être utilisés par les clients.

Paramètres courants :

- **Identité**: pour , et , le paramètre Identité fait toujours ``Get-`` référence à une instance de stratégie ``Set-`` ``New-`` ``Remove-`` spécifique.  Par ``Grant`` exemple, **le paramètre Identité** fait référence à un objet utilisateur spécifique auquel la stratégie est appliquée.

## <a name="manage-configurations-via-powershell"></a>Gérer les configurations via PowerShell

Recherchez les cmdlets pour gérer votre configuration dans le [module d’let de commande Skype Entreprise.](https://www.microsoft.com/en-us/download/details.aspx?id=39366)

Les configurations sont des compartiments de paramètres conservés dans le service qui ne peuvent pas être spécifiés au niveau de l’utilisateur. Les paramètres s’appliquent toujours à l’ensemble de l’organisation. Votre configuration globale est la seule configuration efficace au niveau de votre organisation. Chaque type de configuration est fourni avec deux cmdlets principales :

- ``Get-Cs<ConfigurationName>`` (par exemple, ``Get-CsTeamsClientConfiguration`` ) :

- Commandes SET (par exemple, ``Set-CsTeamsClientConfiguration`` ) : définissez des propriétés dans la configuration de ce type. Spécifiez les paramètres à modifier.
   > Vous pouvez référencer la configuration que vous modifiez de deux manières : en spécifiant : Identity **Global** ou en exécutant ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Que peuvent faire chaque rôle d’administrateur ?

Lisez [Utiliser les rôles d’administrateur](using-admin-roles.md) Microsoft Teams pour gérer Teams afin de comprendre quels rôles d’administrateur peuvent exécuter chaque cmdlet PowerShell.

## <a name="related-topics"></a>Sujets associés

[Installation de Teams PowerShell](teams-powershell-install.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l’cmdlet Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur pour gérer Teams](using-admin-roles.md)
