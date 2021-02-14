---
title: Exemple de script PowerShell - Nettoyage du déploiement de Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour désinstaller Teams et supprimer le dossier Teams pour les utilisateurs.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4b0bac09e18a9c6378623066889d6b1a891a4a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809484"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a><span data-ttu-id="8e089-103">Exemple de script PowerShell - Nettoyage du déploiement teams</span><span class="sxs-lookup"><span data-stu-id="8e089-103">PowerShell script sample - Teams deployment clean up</span></span>

<span data-ttu-id="8e089-104">Utilisez ce script pour supprimer Teams.</span><span class="sxs-lookup"><span data-stu-id="8e089-104">Use this script to remove Teams.</span></span> <span data-ttu-id="8e089-105">Ce script désinstalle Teams et supprime le dossier Teams d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8e089-105">This script uninstalls Teams and removes the Teams folder for a user.</span></span> <span data-ttu-id="8e089-106">Exécutez ce script pour chaque profil utilisateur dans lequel Teams a été installé sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="8e089-106">Run this script for each user profile in which Teams was installed on a computer.</span></span>


## <a name="sample-script"></a><span data-ttu-id="8e089-107">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="8e089-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
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

## <a name="related-topics"></a><span data-ttu-id="8e089-108">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="8e089-108">Related topics</span></span>

- [<span data-ttu-id="8e089-109">Installer Microsoft Teams à l’aide de Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e089-109">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>](../msi-deployment.md)
- [<span data-ttu-id="8e089-110">Déployer Teams avec les applications Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e089-110">Deploy Teams with Microsoft 365 Apps</span></span>](https://docs.microsoft.com/deployoffice/teams-install)
