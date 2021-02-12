---
title: Exemple de script PowerShell - Créer & stratégie de messagerie
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Teams et l’affecter à des utilisateurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804654"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e1465-103">Exemple de script PowerShell : créer et attribuer une stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="e1465-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="e1465-104">Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft Teams et l’affecter à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e1465-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e1465-105">Pour plus d’informations sur l’utilisation de ce script PowerShell, voir [Démarrage rapide - Teams pour l’éducation.](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)</span><span class="sxs-lookup"><span data-stu-id="e1465-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e1465-106">Ce script utilise l’cmdlet [Grant-CsTeamsMesspolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) qui se trouve dans le module PowerShell de Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="e1465-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="e1465-107">Consultez [la vue d’ensemble de Teams PowerShell](../teams-powershell-overview.md) pour en savoir plus sur la gestion des équipes à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1465-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e1465-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e1465-108">Before you start</span></span>

<span data-ttu-id="e1465-109">Téléchargez et installez [le module PowerShell Skype](https://www.microsoft.com/download/details.aspx?id=39366)Entreprise Online, puis redémarrez votre ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="e1465-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e1465-110">Pour en savoir plus, [consultez Gérer Skype Entreprise Online avec PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e1465-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="e1465-111">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="e1465-111">Sample script</span></span>

```powershell
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
```

> [!NOTE]
> <span data-ttu-id="e1465-112">Vous pouvez également affecter une stratégie de messagerie directement aux utilisateurs à l’échelle via une affectation de stratégie de lot ou à un groupe dont les utilisateurs sont membres.</span><span class="sxs-lookup"><span data-stu-id="e1465-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="e1465-113">Pour plus d’informations, voir Attribuer des stratégies à un grand [nombre](../batch-group-policy-assignment-edu.md) d’utilisateurs dans votre établissement scolaire et Attribuer des stratégies [à vos utilisateurs dans Teams.](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e1465-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
