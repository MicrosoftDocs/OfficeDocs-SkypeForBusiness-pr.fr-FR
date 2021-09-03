---
title: Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer d’Skype Entreprise Online Connector au module PowerShell Teams à gérer les Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cdd6460e6a17a15193104a0871a57fa6dbff8105
ms.sourcegitcommit: 70c07a6b1be81681eec32a89872e2218d70c514d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866356"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migration d’Skype Entreprise Online Connector vers le module Teams PowerShell

Teams Le module PowerShell fournit un ensemble complet d’lets de commande pour la gestion Teams à partir de la ligne de commande PowerShell. Les administrateurs n’ont pas besoin Skype d’un connecteur For Business Online pour leur administration Teams entreprise.

> [!NOTE]
> Teams administrateur ont été informés via la publication du Centre de messages (MC244740, spécifiée le 16 mars 2021 ; MC250940, dated April 16 2021) about this change.
>
> Teams Le module PowerShell utilise l’authentification moderne, mais le client Windows gestion à distance (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base. Pour obtenir des instructions sur [l’Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) de l’authentification de base, voir Télécharger et installer.

## <a name="how-to-migrate"></a>Comment migrer

La migration d’Skype Entreprise Online Connector vers Teams module PowerShell est simple et simple. La procédure ci-dessous explique comment faire.

1. Installez la dernière version Teams module PowerShell. Pour consulter la procédure, [voir Installer Microsoft Teams PowerShell.](teams-powershell-install.md)

2. Désinstaller Skype Entreprise Online Connector. Pour ce faire, dans le Panneau de contrôle, sélectionnez Programmes et fonctionnalités, Skype Entreprise **Online, Windows PowerShell Module,** puis **Désinstaller.**

3. Dans vos scripts PowerShell, modifiez le nom du module référencé ```Import-Module``` dans

    `SkypeOnlineConnector` ou `LyncOnlineConnector` `MicrosoftTeams` à .

    Par exemple, `Import-Module -Name SkypeOnlineConnector` changez pour `Import-Module -Name MicrosoftTeams` .

4. Lorsque vous utilisez Teams PowerShell Module 2.0 ou version ultérieure, mettez à jour vos scripts qui font `New-CsOnlineSession` `Connect-MicrosoftTeams` référence. `Import-PsSession`n’est plus nécessaire pour établir une session PowerShell distante Skype Entreprise Online, comme cela est implicite lors de `Connect-MicrosoftTeams` l’utilisation.

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="related-topics"></a>Sujets associés

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Notes de publication de PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams des cmdlet](/powershell/teams/?view=teams-ps)

[Skype Entreprise des cmdlet](/powershell/skype/intro?view=skype-ps)
