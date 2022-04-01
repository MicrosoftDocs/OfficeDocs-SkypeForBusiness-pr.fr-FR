---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593671"
---
1. Installez PowerShell version 7 ou ultérieure. Pour obtenir une aide étape par étape, voir [Installation de PowerShell sur Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Exécutez PowerShell en mode administrateur.
1. Installez le module Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Vérifiez qu’il s’agit de la version 1.6.1 ou ultérieure.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Installez le module PowerShell Teams Preview.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Vérifiez qu’il s’agit d’une version au moins 4.1.0 et qu’il contient les cmdlets de connecteur Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Installez le module MSAL PowerShell.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. Définissez la sortie de PowerShell en cas d’erreur lors de l’exécution du script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Activez l’écriture de scripts Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```