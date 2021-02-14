---
title: Utiliser PowerShell pour définir des stratégies d’événements en direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 07/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Exemples d’utilisation de PowerShell pour définir des stratégies dans Teams afin de contrôler qui peut organiser des événements en direct dans votre organisation et les fonctionnalités disponibles dans les événements.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ece22b6debd3c7d6209df96983d1d66ed5f6f3ca
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815624"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="cfafa-103">Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cfafa-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="cfafa-104">Vous pouvez utiliser les cmdlets de Windows PowerShell suivantes pour définir et attribuer des paramètres de stratégie pour les événements en direct dans Teams :</span><span class="sxs-lookup"><span data-stu-id="cfafa-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="cfafa-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cfafa-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cfafa-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cfafa-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cfafa-107">New-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cfafa-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cfafa-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="cfafa-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="cfafa-109">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="cfafa-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="cfafa-110">Voici quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="cfafa-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="cfafa-111">Avant d’exécuter ces cmdlets, vous devez être connecté à Skype Entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfafa-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="cfafa-112">Pour plus d’informations, [consultez Gérer Skype Entreprise Online avec Microsoft 365 ou Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="cfafa-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="cfafa-113">Autoriser les utilisateurs à planifier des événements en direct</span><span class="sxs-lookup"><span data-stu-id="cfafa-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="cfafa-114">Ces exemples s’illustrent des événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cfafa-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="cfafa-115">Pour les événements produits avec une application ou un appareil externe, vous devez suivre des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="cfafa-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="cfafa-116">Pour plus d’informations, voir Permettre aux utilisateurs de planifier des événements produits [avec une application ou un appareil externe.](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device)</span><span class="sxs-lookup"><span data-stu-id="cfafa-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="cfafa-117">**Autoriser un utilisateur à planifier des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="cfafa-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="cfafa-118">Si la stratégie globale est affectée à l’utilisateur, exécutez et vérifiez que le paramètre *AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="cfafa-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="cfafa-119">Affectez ensuite l’utilisateur à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="cfafa-120">Scénarios utilisateur</span><span class="sxs-lookup"><span data-stu-id="cfafa-120">User scenarios</span></span>
<span data-ttu-id="cfafa-121">**Vous souhaitez que tous les utilisateurs de votre organisation puissent planifier des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="cfafa-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="cfafa-122">Si la stratégie globale est affectée aux utilisateurs, exécutez et vérifiez que *AllowBroadcastScheduling* \*est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="cfafa-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="cfafa-123">Si des utilisateurs ont une stratégie autre que la stratégie globale, exécutez et vérifiez que la planification *-AllowBroadcast est* définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="cfafa-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="cfafa-124">**Vous souhaitez que la planification d’événements en direct soit désactivée dans votre organisation**</span><span class="sxs-lookup"><span data-stu-id="cfafa-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="cfafa-125">Désactivez la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="cfafa-126">Affectez tous les utilisateurs de votre organisation à la stratégie globale. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="cfafa-127">**Vous souhaitez qu’un grand nombre d’utilisateurs puissent planifier des événements en direct et empêcher un ensemble d’utilisateurs de les planifier**</span><span class="sxs-lookup"><span data-stu-id="cfafa-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="cfafa-128">Exécutez et vérifiez que *la planification AllowBroadcast* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="cfafa-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="cfafa-129">Affectez ensuite un ou plusieurs utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="cfafa-130">Créez une stratégie qui n’autorise pas la planification d’événements en direct. Exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="cfafa-131">Désactivez la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="cfafa-132">Affectez ensuite les utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="cfafa-133">**Vous voulez désactiver la planification d’événements en direct pour un grand nombre d’utilisateurs et autoriser un ensemble d’utilisateurs à les planifier**</span><span class="sxs-lookup"><span data-stu-id="cfafa-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="cfafa-134">Désactivez la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="cfafa-135">Affectez ensuite ces utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="cfafa-136">Créez une stratégie pour autoriser la planification et l’organisation d’événements en direct :</span><span class="sxs-lookup"><span data-stu-id="cfafa-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="cfafa-137">Activez la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="cfafa-138">Affectez ensuite les utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="cfafa-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="cfafa-139">Définir qui peut participer à des événements en direct</span><span class="sxs-lookup"><span data-stu-id="cfafa-139">Set who can join live events</span></span>
 
<span data-ttu-id="cfafa-140">Définissez la stratégie globale pour permettre aux utilisateurs de créer des événements que tout le monde, y compris les utilisateurs anonymes, peuvent participer et exécuter :</span><span class="sxs-lookup"><span data-stu-id="cfafa-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="cfafa-141">Définir l’option d’enregistrement pour les événements en direct</span><span class="sxs-lookup"><span data-stu-id="cfafa-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="cfafa-142">Ce paramètre s’applique uniquement aux événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cfafa-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="cfafa-143">Définissez la stratégie globale pour désactiver l’enregistrement des événements en direct :</span><span class="sxs-lookup"><span data-stu-id="cfafa-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="cfafa-144">Définir des légendes et sous-titres en direct dans des événements en direct</span><span class="sxs-lookup"><span data-stu-id="cfafa-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="cfafa-145">Ce paramètre s’applique uniquement aux événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="cfafa-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="cfafa-146">Définissez la stratégie globale pour activer les légendes et sous-titres en direct (transcription) pour les participants à l’événement :</span><span class="sxs-lookup"><span data-stu-id="cfafa-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="cfafa-147">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="cfafa-147">Related topics</span></span>
- [<span data-ttu-id="cfafa-148">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="cfafa-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="cfafa-149">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfafa-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

