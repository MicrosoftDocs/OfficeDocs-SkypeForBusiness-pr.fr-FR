---
title: Exemple de script PowerShell - Aide pour nettoyer le déploiement de Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Utilisez ce script PowerShell pour nettoyer Microsoft Teams sur des machines ciblées ou pour des utilisateurs spécifiques.
localization_priority: Normal
ms.openlocfilehash: 6605f1af0f38a79b6e19018d516357312b5cf49e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458883"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>Exemple de script PowerShell - Nettoyage du déploiement de Microsoft Teams
-------------------------------------------------------------------------

Ce script PowerShell peut être utilisé pour nettoyer Microsoft Teams sur des machines ou pour des utilisateurs spécifiques. Il doit être exécuté pour chaque utilisateur sur une machine spécifique. 


## <a name="sample-script"></a>Exemple de script

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


