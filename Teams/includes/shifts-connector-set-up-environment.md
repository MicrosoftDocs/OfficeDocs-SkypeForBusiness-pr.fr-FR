---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976015"
---
1. Installez PowerShell version 7 ou ultérieure. Pour obtenir des instructions pas à pas, consultez [l’installation de PowerShell sur Windows](/powershell/scripting/install/installing-powershell-on-windows).

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

1. Installez le module PowerShell Teams préversion.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Vérifiez qu’il s’agit au moins de la version 4.1.0 et qu’il contient les applets de commande du connecteur Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Définissez PowerShell pour qu’il s’arrête si une erreur se produit lors de l’exécution du script.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Activez l’exécution des scripts dans Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```