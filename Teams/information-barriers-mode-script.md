---
title: Modifier les modes de barrières d’information avec un script PowerShell
description: Utilisez ce script PowerShell après avoir déployé des barrières d’informations pour mettre à jour le mode de l’ouverture à l’implicite pour tous les groupes de votre locataire.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047124"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Modifier les modes de barrières d’information avec un script PowerShell

Utilisez ce script PowerShell pour mettre à jour le mode des barrières à l’information (IB) pour tous les groupes connectés à Teams dans votre locataire. Vous devez mettre à jour le mode de ces groupes après avoir déployé des barrières à l’information. Les groupes approvisionnés avant d’activer IB se voient attribuer le mode *Open* . En mode *Ouvert* , il n’existe aucune stratégie IB applicable. Une fois que vous avez activé IB, *Implicit* devient le mode par défaut pour tous les nouveaux groupes que vous créez. Toutefois, les groupes existants conservent toujours la configuration en mode *Ouvert* . Exécutez ce script pour changer ces groupes existants en mode *implicite* .

Dans ce script, vous allez utiliser l’applet de commande [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup), qui se trouve dans le module PowerShell Exchange Online pour mettre à jour le mode. Pour en savoir plus sur la gestion de Teams à l’aide de PowerShell, consultez [la vue d’ensemble de Teams PowerShell](./teams-powershell-overview.md).

## <a name="sample-script"></a>Exemple de script

Vous devez utiliser un compte professionnel ou scolaire qui a reçu le rôle d’administrateur général pour que votre locataire exécute ce script.

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