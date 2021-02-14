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
ms.openlocfilehash: 12360110df90fb5de2e3e4547534c8569cc5537a
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852155"
---
# <a name="microsoft-teams-powershell-overview"></a>Vue d’ensemble de Microsoft Teams PowerShell

Microsoft Teams PowerShell est un ensemble d’lets de commande qui vous aide à gérer Teams directement à partir de la ligne de commande PowerShell. Écrit dans .NET Standard, Teams PowerShell fonctionne sur PowerShell 5.1 sur Windows, PowerShell 6.x et les systèmes plus élevés sur toutes les plateformes, y compris Azure Cloud Shell.

Avant de commencer à utiliser PowerShell, vous devez [l’installer.](teams-powershell-install.md) 

> [!WARNING]
> Il existe des problèmes connus avec PowerShell 7 et Teams PowerShell. Nous vous recommandons d’utiliser PowerShell 5.1 jusqu’à ce que les problèmes soient résolus.

## <a name="releases"></a>Publication


Teams PowerShell est disponible dans la [galerie PowerShell en](https://www.powershellgallery.com/packages/MicrosoftTeams) deux types.

- **Disponibilité générale (GA)**: cmdlets prêtes pour la production, mises à jour tous les mois.

- **Prévisualisation** publique : Accès précoce aux fonctionnalités. Peut être mis à jour plus fréquemment que GA.

Pour plus d’informations sur les ajouts de fonctionnalités et les améliorations apportées aux deux version, lisez les notes de publication [Teams PowerShell.](teams-powershell-release-notes.md)


## <a name="manage-teams-with-powershell"></a>Gérer Teams avec PowerShell

Vous utiliserez les modules Teams PowerShell pour gérer entièrement Teams :

- [Module Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/): le module Teams PowerShell contient des cmdlets pour la gestion des équipes, des discussions et des canaux.

> [!NOTE]
> La dernière version [publique de Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) est intégrée à Skype Entreprise Online Connector et fournit un seul module pour la gestion de Teams PowerShell.

- [Connecteur PowerShell Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=39366): Le connecteur Skype Entreprise PowerShell fait désormais partie du module Teams PowerShell.

Pour consulter un guide complet de la gestion de Teams à l’aide de ces modules, voir [Gérer Teams avec Teams PowerShell.](teams-powershell-managing-teams.md)


## <a name="related-topics"></a>Sujets associés

[Installation de Teams PowerShell](teams-powershell-install.md)

[Gestion des équipes avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

[Utiliser des rôles d’administrateur de Microsoft Teams pour gérer Teams](using-admin-roles.md)
