---
title: Microsoft Teams Vue d’ensemble de PowerShell
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
description: Découvrez comment utiliser les contrôles PowerShell pour gérer les Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 448658fb844052815e14b85e0c70a33cb737b72d
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768353"
---
# <a name="microsoft-teams-powershell-overview"></a>Microsoft Teams Vue d’ensemble de PowerShell

Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous Teams gérer vos commandes directement à partir de la ligne de commande PowerShell. Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les plateformes supérieures, y compris Azure Cloud Shell.

Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md) 

> [!WARNING]
> Certains problèmes connus sur PowerShell 7 et Teams PowerShell sont connus. Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.

## <a name="releases"></a>Publication


Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.

- **Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.

- **Aperçu public :** Accès en avant-première aux fonctionnalités. Peut être mis à jour plus fréquemment que GA.

Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les Teams de [publication de PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gérer Teams avec PowerShell

Vous utiliserez les modules PowerShell Teams pour gérer entièrement les Teams :

- [Microsoft Teams module PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module PowerShell Teams des cmdlets pour la gestion des équipes, des discussions et des canaux.

> [!NOTE]
> La Teams version publique [de PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 2.0 ou version supérieure inclut toutes les cmdlets Skype Entreprise Online Connector, fournissant un seul module pour la gestion Teams PowerShell.

- [Skype Entreprise Connecteur PowerShell :](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)le connecteur PowerShell Skype Entreprise fait désormais partie d’Teams module PowerShell.

Pour consulter un guide complet de gestion Teams l’aide de ces modules, voir Gérer les Teams [avec Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Sujets associés

[Installation Teams PowerShell](teams-powershell-install.md)

[Gestion des Teams à l’Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notes de publication de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams des cmdlet](/powershell/teams/?view=teams-ps)

[Skype Entreprise des cmdlet](/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md)
