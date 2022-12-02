---
title: Migration de Skype Entreprise Online Connector vers le module Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Découvrez comment passer de Skype Entreprise Connecteur en ligne au module PowerShell Teams pour gérer Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 648ce1fb69f9e1641840f2e4b92acc1b98f4bbe8
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242288"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a>Migration de Skype Entreprise Online Connector vers le module Teams PowerShell

Le module PowerShell Teams fournit un ensemble complet d’applets de commande pour la gestion de Teams directement à partir de la ligne de commande PowerShell. Les administrateurs n’ont pas besoin du connecteur Skype Entreprise Online pour leur administration Teams.

> [!NOTE]
> Les administrateurs Teams ont été avertis par le biais d’une publication du centre de messages (MC244740, en date du 16 mars 2021 ; MC250940, daté du 16 avril 2021) à propos de ce changement.
>
> Le module PowerShell Teams utilise l’authentification moderne, mais le client Windows Remote Management (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base. Consultez [Télécharger et installer Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) pour obtenir des instructions sur l’activation de WinRM pour l’authentification de base.

## <a name="how-to-migrate"></a>Guide pratique pour migrer

La migration de Skype Entreprise Connecteur en ligne vers le module PowerShell Teams est simple et simple. Les étapes ci-dessous expliquent comment procéder.

1. Installez le dernier module Teams PowerShell. Pour connaître les étapes à suivre, consultez [Installer Microsoft Teams PowerShell](teams-powershell-install.md).

2. Désinstallez le connecteur Skype Entreprise Online. Pour ce faire, dans Panneau de configuration, accédez à **Programmes et fonctionnalités**, sélectionnez **Skype Entreprise En ligne, Windows PowerShell Module**, puis **sélectionnez Désinstaller**.

3. Dans vos scripts PowerShell, modifiez le nom du module référencé dans ```Import-Module``` à partir de

    `SkypeOnlineConnector` ou `LyncOnlineConnector` à `MicrosoftTeams`.

    Par exemple, remplacez par `Import-Module -Name SkypeOnlineConnector` `Import-Module -Name MicrosoftTeams`.

4. Lorsque vous utilisez Teams PowerShell Module 2.0 ou version ultérieure, mettez à jour vos scripts qui font référence `New-CsOnlineSession` à `Connect-MicrosoftTeams`. `Import-PsSession`n’est plus nécessaire pour établir une Skype Entreprise session PowerShell distante en ligne, car cela s’effectue implicitement lors de l’utilisation `Connect-MicrosoftTeams`de .

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

## <a name="related-topics"></a>Rubriques connexes

[Installer Microsoft Teams PowerShell](teams-powershell-install.md)

[Gérer Teams avec Teams PowerShell](teams-powershell-managing-teams.md)

[Notes de publication de Teams PowerShell](teams-powershell-release-notes.md)

[Informations de référence sur les applets de commande Microsoft Teams](/powershell/teams/)

[Informations de référence sur les applets de commande Skype Entreprise](/powershell/skype/intro)
