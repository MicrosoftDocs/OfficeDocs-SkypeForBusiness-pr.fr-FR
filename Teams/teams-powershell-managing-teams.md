---
title: Gérer teams avec Microsoft teams PowerShell
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
description: Apprenez à gérer Microsoft teams avec teams PowerShell.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c217cea4a9ad800c1f31f8dcfae9c88ee281188c
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944099"
---
# <a name="manage-teams-with-microsoft-teams-powershell"></a>Gérer teams avec Microsoft teams PowerShell

Cet article vous montre comment utiliser Microsoft teams PowerShell pour gérer teams et Skype entreprise. 

Servez-vous de ces instructions conjointement avec les informations de [référence](https://docs.microsoft.com/powershell/teams/?view=teams-ps) sur les applets de décision et les références de [cmdlet Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).

## <a name="create-and-manage-teams-using-powershell"></a>Création et gestion d’équipes à l’aide de PowerShell

Les applets de développement pour la création et la gestion d’équipes se trouvent dans le [module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/).

Les équipes sont régularisées par les groupes Office 365, de sorte que lorsque vous créez une équipe, vous créez un groupe. Il existe un ensemble d’applets de construction fourni pour l’utilisation de l’équipe principale et de ses paramètres ( ``new-team`` , ``get-team`` ,, ``set-team`` ), de la gestion des utilisateurs d’équipe ( ``add-teamuser`` , ``remove-teamuser`` ), ainsi que des cmdlets de gestion des canaux de l’équipe ( ``new-teamchannel`` ``remove-teamchannel`` ). Toutes ces applets de action peuvent être exécutées en tant qu’utilisateurs finaux, mais elles ne fonctionnent que sur les équipes dont vous êtes membre ou dont vous êtes membre. Si vous êtes un administrateur général ou un administrateur de service Teams, vous pouvez agir sur toutes les équipes de votre organisation.

```powershell
New-Team -Name "Contoso Marketing" -Description "Collaboration space for Contoso's Marketing department
```

> Le **GroupID** utilisé dans les applets de applet de module Microsoft teams PowerShell est le même que la propriété **Identity** renvoyée par ``Get-UnifiedGroup`` dans le module Exchange PowerShell.

## <a name="manage-policies-via-powershell"></a>Gérer les stratégies via PowerShell

> [!NOTE]
> - Le connecteur Skype entreprise Online est actuellement intégré dans teams PowerShell. Ce service est actuellement disponible en version préliminaire publique. Dans le temps, les applets de connexion Skype entreprise Online qui s’appliquent aux équipes seront disponibles en mode natif dans le module PowerShell Teams. Des étapes d’installation sont disponibles dans l’article [installer teams PowerShell](teams-powershell-install.md) .
>
> - Les applets de connexion seront disponibles dans votre session PowerShell une fois que vous vous connectez à Skype entreprise online. Pour plus d’informations, reportez-vous à la rubrique [gestion de Skype entreprise Online avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

Recherchez les cmdlets de gestion des stratégies dans le [module de cmdlet Skype entreprise](https://www.microsoft.com/download/details.aspx?id=39366).

Une stratégie est un ensemble de paramètres qui peuvent être appliqués de façon granulaire aux utilisateurs individuels. Chaque type de stratégie dispose de son propre ensemble d’applets de jeu permettant de créer, d’afficher, de supprimer et de mettre à jour les stratégies, puis de les affecter aux utilisateurs. La structure générale est la suivante :

- **Obtenir** les commandes (par exemple, ``Get-CsTeamsMeetingPolicy`` ) : renvoie les documents de stratégie que vous pouvez affecter au sein de votre organisation, y compris les stratégies créées par Microsoft, que vous avez créées.
   - Pour rechercher uniquement les stratégies personnalisées que vous avez créées au sein de votre organisation, utilisez ``-Filter "tag:*"`` .

- Les **nouvelles** commandes (par exemple, ``New-CsTeamsMeetingPolicy`` ) : créent de nouvelles stratégies à attribuer aux utilisateurs de votre organisation. Toutes les stratégies ne prennent pas en charge la création de stratégies personnalisées. En règle générale, il s’agit de veiller à ce que les stratégies que vous utilisez au sein de votre organisation possèdent une combinaison de paramètres prise en charge.

- **Définir** des commandes (par exemple, ``Set-CsTeamsMeetingPolicy`` ) : définit des valeurs particulières sur une stratégie donnée. Certaines stratégies n’ont pas de commandes définies disponibles ou contiennent des paramètres qui ne peuvent pas être personnalisés dans la stratégie. Les descriptions PowerShell vous indiquent quels paramètres ne peuvent pas être personnalisés. 
   - Pour modifier la stratégie qui sera affectée par défaut aux utilisateurs de votre organisation pour lesquels aucune stratégie personnalisée n’est affectée, exécutez ``Set-Cs<PolicyName> -Identity Global`` .

- **Supprimer** des commandes (par exemple, ``Remove-CsTeamsMeetingPolicy`` ) : supprimer une stratégie personnalisée qui a été créée dans votre client. Si vous supprimez une stratégie personnalisée qui a été attribuée à au moins un utilisateur au sein de votre organisation, cet utilisateur sera renvoyé à la stratégie globale.
   - Vous ne pouvez pas supprimer réellement la politique globale de votre organisation, mais si vous voulez rétablir les paramètres par défaut fournis par Microsoft dans votre organisation, exécutez ``Remove-Cs<PolicyName> -Identity Global`` .

- Commande d' **attribution** (par exemple, ``Grant-CsTeamsMeetingPolicy`` ) : affecte une stratégie à un utilisateur particulier.
   - Pour supprimer une affectation de stratégie personnalisée et permettre à l’utilisateur de revenir à la stratégie par défaut de votre organisation, exécutez ``Grant-Cs<PolicyName> -Identity <User Identity> -PolicyName $null`` .

> [!TIP]
> Toutes les stratégies n’autorisent pas la création de stratégies personnalisées, et certaines stratégies ne peuvent pas être personnalisées (de sorte que vous ne pouvez pas définir de valeur personnalisée pendant ``set-`` et ``new-`` ). La documentation de chaque cmdlet appelle le fait que les paramètres soient disponibles pour les clients.

Paramètres courants :

- **Identity**: pour ``Get-`` ,, ``Set-`` ``New-`` et ``Remove-`` , le paramètre **Identity** fera toujours référence à une instance de stratégie spécifique. Pour ``Grant`` le paramètre **Identity** , fait référence à un objet utilisateur spécifique auquel la stratégie est appliquée.

## <a name="manage-configurations-via-powershell"></a>Gestion des configurations via PowerShell

Recherchez les applets de configuration pour la gestion de votre configuration dans le [module de cmdlet Skype entreprise](https://www.microsoft.com/en-us/download/details.aspx?id=39366).

Les configurations sont des compartiments des paramètres conservés dans le service qui ne peuvent pas être spécifiés à un niveau utilisateur. Les paramètres s’appliquent toujours à l’ensemble de l’organisation. Votre configuration globale est la seule configuration efficace au sein de votre organisation. Chaque type de configuration est fourni avec deux cmdlets principales :

- ``Get-Cs<ConfigurationName>``(par exemple, ``Get-CsTeamsClientConfiguration`` ) :

- Définissez les commandes (par exemple, ``Set-CsTeamsClientConfiguration`` ) : définissez les propriétés dans la configuration de ce type. Spécifiez les paramètres que vous voulez modifier.
   > Vous pouvez faire référence à la configuration que vous modifiez de l’une des deux manières suivantes : en spécifiant-**Identity global**ou en exécutant ``Get-Cs<ConfigurationName>``  |  ``Set-Cs<ConfigurationName>`` .

## <a name="what-can-each-admin-role-do"></a>Que peut faire chaque rôle d’administrateur ?

Lire [Utilisez les rôles d’administrateur de Microsoft teams pour gérer les équipes](using-admin-roles.md) et comprendre quels rôles d’administrateur peuvent exécuter chaque cmdlet PowerShell.

## <a name="related-topics"></a>Sujets associés

[Installation de PowerShell teams](teams-powershell-install.md)

[Notes de publication teams PowerShell](teams-powershell-release-notes.md)

[Référence sur les applets de fonction teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur pour gérer Teams](using-admin-roles.md)