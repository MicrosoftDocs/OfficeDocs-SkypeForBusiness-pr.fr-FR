---
title: Vue d’ensemble de Microsoft Teams PowerShell
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
ms.openlocfilehash: 6c2c626d61a10437fc5bb349dd128415d64448a7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569020"
---
# <a name="microsoft-teams-powershell-overview"></a>Vue d’ensemble de Microsoft Teams PowerShell

Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous aide à gérer Teams directement à partir de la ligne de commande PowerShell. Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les systèmes plus élevés sur toutes les plateformes, y compris Azure Cloud Shell.

Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md) 

> [!WARNING]
> Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell. Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.

## <a name="releases"></a>Publication


Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.

- **Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.

- **Aperçu public :** Accès en avant-première aux fonctionnalités. Peut être mis à jour plus fréquemment que GA.

Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les notes de [publication Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gérer Teams avec PowerShell

Vous utiliserez les modules Teams PowerShell pour gérer entièrement Teams :

- [Module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module Teams PowerShell contient des cmdlets pour la gestion des équipes, des discussions et des canaux.

> [!NOTE]
> La version 1.1.6 ou ultérieure de [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un module unique pour la gestion de Teams PowerShell.

- [Connecteur PowerShell Skype](https://www.microsoft.com/download/details.aspx?id=39366)Entreprise : Le connecteur PowerShell Skype Entreprise fait désormais partie du module Teams PowerShell.

Pour consulter un guide complet de la gestion de Teams à l’aide de ces modules, voir [Gérer Teams avec Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Voir aussi

[Installation de Teams PowerShell](teams-powershell-install.md)

[Gestion des équipes avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md)
