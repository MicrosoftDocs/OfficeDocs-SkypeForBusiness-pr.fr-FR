---
title: Exemple de Script PowerShell - facilite le déploiement des équipes Microsoft de nettoyage
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Utilisez ce script PowerShell pour créer une équipe publique à l’échelle de l’entreprise dans Teams.
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 1466a08d493538eadb6cd2bfc2f50ac15acb0fa7
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="78fd4-103">Exemple de Script PowerShell - déploiement de Teams Microsoft nettoyer</span><span class="sxs-lookup"><span data-stu-id="78fd4-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="78fd4-104">Ce script PowerShell peut être exploité pour le nettoyage de Teams Microsoft à partir de la cible machines\users.</span><span class="sxs-lookup"><span data-stu-id="78fd4-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines\users.</span></span> <span data-ttu-id="78fd4-105">Il doit être exécuté pour chaque utilisateur sur un ordinateur cible.</span><span class="sxs-lookup"><span data-stu-id="78fd4-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="78fd4-106">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="78fd4-106">Sample script</span></span>

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


