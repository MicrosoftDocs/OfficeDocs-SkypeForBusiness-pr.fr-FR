---
title: Modifier les modes de barrière de l’information avec un script PowerShell
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell après avoir déployé des barrières d’informations pour mettre à jour le mode de l’ouvrir à l’implicite pour tous les groupes de votre client.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767547"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Modifier les modes de barrière de l’information avec un script PowerShell

Utilisez ce script PowerShell pour mettre à jour les barrières à l’information (IB) pour tous les Teams connectés à un client. Une fois les barrières d’informations déployées, vous devrez mettre à jour le mode pour ces groupes. Le mode Ouvrir est attribué aux groupes déjà activés avant *l’ouverture de l’offre* IB. En *mode Ouvrir,* il n’existe pas de stratégies IB applicables. Après avoir activé l' IB, *l’implicite* devient le mode par défaut pour tous les nouveaux groupes que vous créez. Toutefois, les groupes existants conservent la configuration *du* mode Ouvrir. Exécutez ce script pour modifier ces groupes existants en mode *implicite.*

Dans ce script, vous allez utiliser l’cmdlet [Get-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) qui se trouve dans le module Exchange Online PowerShell pour mettre à jour le mode. Pour en savoir plus sur la gestion des Teams à l’aide de PowerShell, voir [Teams vue d’ensemble de PowerShell.](./teams-powershell-overview.md)

## <a name="sample-script"></a>Exemple de script

Pour exécuter ce script, vous devez utiliser un compte scolaire ou scolaire ou un compte qui dispose du rôle d’administrateur général attribué à votre client.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```