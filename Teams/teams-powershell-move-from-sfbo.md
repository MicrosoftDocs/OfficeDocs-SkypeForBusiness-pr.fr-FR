---
title: Passer de Skype Entreprise Online Connector au module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer de Skype Entreprise Online Connector au module Teams PowerShell pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569080"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Passer de Skype Entreprise Online Connector au module Teams PowerShell

Pour passer de l’utilisation de Skype Entreprise Online Connector au module Teams PowerShell afin de gérer Teams, vous devez mettre à jour vos scripts PowerShell existants. Cet article explique comment faire.

1. Installez le module Teams PowerShell le plus récent. Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)
2. Désinstallez Skype Entreprise Online Connector. Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.** 
3. Dans vos scripts PowerShell, modifiez le nom du module référencé. ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams```

    Par exemple, ```Import-Module -Name SkypeOnlineConnector``` changez pour ```Import-Module -Name MicrosoftTeams``` .
4. Lorsque vous utilisez Teams PowerShell Module 2.0 ou une génération ultérieure, modifiez New-csOnlineSession en Connect-MicrosoftTeams. 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a>Voir aussi

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Référence de l’cmdlet Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Référence de l’cmdlet Skype Entreprise](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
