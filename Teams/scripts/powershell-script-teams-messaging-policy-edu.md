---
title: Exemple de script PowerShell - créer et attribuer une stratégie de messagerie
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans les équipes et attribuez-le aux utilisateurs de votre organisation.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 108272636925daadfb361c1e79ff14b9c04f514a
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021857"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="02ede-103">Exemple de script PowerShell - créer et attribuer une stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="02ede-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="02ede-104">Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft Teams et attribuez-le aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02ede-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="02ede-105">Pour plus d’informations sur l’utilisation de ce script PowerShell, voir [démarrage rapide - équipes pour l’éducation](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="02ede-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="02ede-106">Si vous débutez avec PowerShell et avez besoin d’aide pour démarrer, reportez-vous à la rubrique [Présentation d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="02ede-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="02ede-107">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="02ede-107">Sample script</span></span>

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId
   
 }

````


