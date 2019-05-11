---
title: Exemple de script PowerShell - Aide pour nettoyer le déploiement de Microsoft Teams
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Utilisez ce script PowerShell pour nettoyer Microsoft Teams sur des machines ciblées ou pour des utilisateurs spécifiques.
localization_priority: Normal
ms.openlocfilehash: cd19bb3b0d26069d339b61b5d4bf059fef724407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920611"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="75660-103">Exemple de script PowerShell - Nettoyage du déploiement de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75660-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="75660-104">Ce script PowerShell peut être utilisé pour nettoyer Microsoft Teams sur des machines ou pour des utilisateurs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="75660-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="75660-105">Il doit être exécuté pour chaque utilisateur sur une machine spécifique.</span><span class="sxs-lookup"><span data-stu-id="75660-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="75660-106">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="75660-106">Sample script</span></span>

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


