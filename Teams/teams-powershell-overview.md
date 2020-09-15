---
title: Vue d’ensemble de Microsoft teams PowerShell
ms.reviewer: ''
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les contrôles PowerShell pour gérer Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5986a730ed678d45360d89efbd35693134c2a6a
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814363"
---
# <a name="microsoft-teams-powershell-overview"></a>Vue d’ensemble de Microsoft teams PowerShell

Microsoft teams PowerShell est un ensemble d’applets de commande qui vous permet de gérer teams directement à partir de la ligne de commande PowerShell. Écrit en .NET standard, teams PowerShell fonctionne sur PowerShell 5,1 sur Windows, PowerShell 6. x et versions ultérieures sur toutes les plateformes, dont Azure Shell.

Pour pouvoir commencer à utiliser PowerShell, vous devez l' [installer](teams-powershell-install.md). 

> [!WARNING]
> Il existe des problèmes connus dans PowerShell 7 et teams PowerShell. Nous vous recommandons d’utiliser PowerShell 5,1 jusqu’à la résolution des problèmes.

## <a name="releases"></a>Versions


PowerShell teams est disponible dans la [Galerie PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) en deux types de publication.

- **Disponibilité générale (GA)**: cmdlets prêts à l’emploi, mises à jour mensuelles.

- Préversion **publique**: accès en avant-première aux fonctions. Est-il possible de mettre à jour plus fréquemment que la disponibilité.

Pour plus d’informations sur les ajouts et améliorations de fonctionnalités pour les deux versions, consultez les [notes de publication de teams PowerShell](teams-powershell-release-notes.md).


## <a name="manage-teams-with-powershell"></a>Gestion des équipes avec PowerShell

Vous utiliserez des modules PowerShell teams pour gérer entièrement teams :

- [Module Microsoft teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module PowerShell teams contient des cmdlets de gestion des équipes, des discussions et des canaux.

> [!NOTE]
> La dernière [version publique de PowerShell teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée au connecteur Skype entreprise Online et fournit un module unique pour la gestion de PowerShell Teams.

- [Skype entreprise PowerShell Connector](https://www.microsoft.com/download/details.aspx?id=39366): le Connector Skype entreprise PowerShell fait désormais partie du module PowerShell Teams.

Pour consulter un guide complet de la gestion d’équipes à l’aide de ces modules, voir [gérer les équipes grâce aux équipes PowerShell](teams-powershell-managing-teams.md).


## <a name="related-topics"></a>Voir aussi

[Installation de PowerShell teams](teams-powershell-install.md)

[Gestion des équipes avec PowerShell teams](teams-powershell-managing-teams.md)

[Notes de publication teams PowerShell](teams-powershell-release-notes.md)

[Référence sur les applets de passe Microsoft teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence sur les applets de fonction Skype entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md)
