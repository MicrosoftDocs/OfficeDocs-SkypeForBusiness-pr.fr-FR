---
title: Exemple de script PowerShell - nettoyage Teams de déploiement
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour désinstaller Teams et supprimer le Teams dossier des utilisateurs.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 246c47b74fc90ddfb7b38a0474bc88bff5321559
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402648"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Exemple de script PowerShell - nettoyage Teams de déploiement

Utilisez ce script pour supprimer des Teams. Ce script désinstalle Teams et supprime le Teams d’un utilisateur. Exécutez ce script pour chaque profil utilisateur dans lequel Teams été installé sur un ordinateur.


## <a name="sample-script"></a>Exemple de script

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>Voir aussi

- [Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Déployer des Teams avec Microsoft 365 Apps](/deployoffice/teams-install)
