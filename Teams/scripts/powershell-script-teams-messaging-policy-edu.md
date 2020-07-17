---
title: Exemple de script PowerShell-créer & affecter une stratégie de messagerie
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Utilisez ce script PowerShell pour créer une stratégie de messagerie dans teams et l’attribuer aux utilisateurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c1df183046dc2378081382e2a8b46c9b3b92c80a
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938193"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="3ddc4-103">Exemple de script PowerShell : créer et attribuer une stratégie de messagerie</span><span class="sxs-lookup"><span data-stu-id="3ddc4-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="3ddc4-104">Utilisez ce script PowerShell pour créer une stratégie de messagerie dans Microsoft teams et l’affecter à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="3ddc4-105">Pour plus d’informations sur l’utilisation de ce script PowerShell, reportez-vous à la rubrique [démarrage rapide-teams pour l’éducation](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span><span class="sxs-lookup"><span data-stu-id="3ddc4-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="3ddc4-106">Ce script utilise l’applet de connexion [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) dans le module PowerShell de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="3ddc4-107">Pour en savoir plus sur la gestion d’équipes à l’aide de PowerShell, voir [vue d’ensemble de PowerShell teams](../teams-powershell-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="3ddc4-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="3ddc4-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="3ddc4-108">Before you start</span></span>

<span data-ttu-id="3ddc4-109">Téléchargez et installez le [module PowerShell de Skype entreprise Online](https://www.microsoft.com/download/details.aspx?id=39366), puis redémarrez l’ordinateur si vous y êtes invité.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="3ddc4-110">Pour plus d’informations, reportez-vous à la rubrique [gestion de Skype entreprise Online avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ddc4-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>


## <a name="sample-script"></a><span data-ttu-id="3ddc4-111">Exemple de script</span><span class="sxs-lookup"><span data-stu-id="3ddc4-111">Sample script</span></span>

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
> <span data-ttu-id="3ddc4-112">Vous pouvez également attribuer une stratégie de messagerie directement aux utilisateurs à l’échelle à l’aide d’une affectation de stratégie de lot ou d’un groupe dont les utilisateurs sont membres.</span><span class="sxs-lookup"><span data-stu-id="3ddc4-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="3ddc4-113">Pour plus d’informations [, voir attribuer des stratégies à de grands ensembles d’utilisateurs dans votre établissement scolaire](../batch-policy-assignment-edu.md) et [affecter des stratégies à vos utilisateurs dans teams](../assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc4-113">For more information see [Assign policies to large sets of users in your school](../batch-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
