---
title: Utiliser PowerShell pour définir les stratégies d’événements dynamiques
author: lanachin
ms.author: v-lanac
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
description: Exemples d’utilisation de PowerShell pour définir des stratégies dans teams pour contrôler les personnes qui peuvent contenir des événements en direct au sein de votre organisation et les fonctionnalités disponibles dans les événements.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e49c2dca91dca56366dd6b8a8ce460547043c120
ms.sourcegitcommit: f9daef3213a305676127cf5140af907e3b96d046
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48369149"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="df515-103">Utiliser PowerShell pour définir les stratégies d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="df515-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>

<span data-ttu-id="df515-104">Vous pouvez utiliser les applets de commande Windows PowerShell suivantes pour définir et affecter des paramètres de stratégie pour les événements en direct dans teams :</span><span class="sxs-lookup"><span data-stu-id="df515-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="df515-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="df515-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="df515-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="df515-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="df515-107">Nouveau-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="df515-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="df515-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="df515-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="df515-109">Nouveau-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="df515-109">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment?view=teams-ps)

<span data-ttu-id="df515-110">Voici quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="df515-110">Here are some examples.</span></span>

> [!NOTE]
> <span data-ttu-id="df515-111">Pour pouvoir exécuter ces applets de connexion, vous devez être connecté à Skype entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="df515-111">Before you can run these cmdlets you must be connected to Skype for Business Online PowerShell.</span></span> <span data-ttu-id="df515-112">Pour plus d’informations, reportez-vous à la rubrique [gestion de Skype entreprise Online avec Microsoft 365 ou PowerShell Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="df515-112">For more information, see [Manage Skype for Business Online with Microsoft 365 or Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="df515-113">Permettre aux utilisateurs de planifier des événements en direct</span><span class="sxs-lookup"><span data-stu-id="df515-113">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="df515-114">Ces exemples concernent les événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="df515-114">These examples are for events produced in Teams.</span></span> <span data-ttu-id="df515-115">Pour les événements produits avec une application ou un appareil externe, vous devez effectuer des étapes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="df515-115">For events produced with an external app or device, there are additional steps you must do.</span></span> <span data-ttu-id="df515-116">Pour plus d’informations, reportez-vous à la rubrique [permettre aux utilisateurs de planifier des événements qui ont été produits avec un appareil ou une application externe](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span><span class="sxs-lookup"><span data-stu-id="df515-116">For more information, see [Enable users to schedule events that were produced with an external app or device](set-up-for-teams-live-events.md#enable-users-to-schedule-events-that-were-produced-with-an-external-app-or-device).</span></span>

<span data-ttu-id="df515-117">**Permettre à un utilisateur de planifier des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="df515-117">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="df515-118">Si la stratégie globale est affectée à l’utilisateur, exécutez et vérifiez que le paramètre *AllowBroadcastScheduling* est défini sur *true*:</span><span class="sxs-lookup"><span data-stu-id="df515-118">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="df515-119">Affectez ensuite à l’utilisateur la politique globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-119">Then assign the user to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="df515-120">Scénarios utilisateur</span><span class="sxs-lookup"><span data-stu-id="df515-120">User scenarios</span></span>
<span data-ttu-id="df515-121">**Vous souhaitez que tous les utilisateurs de votre organisation puissent planifier des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="df515-121">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="df515-122">Si les utilisateurs disposent de la stratégie globale, exécutez et vérifiez que *AllowBroadcastScheduling* \* est défini sur *true*:</span><span class="sxs-lookup"><span data-stu-id="df515-122">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="df515-123">Si les utilisateurs se voient attribuer une stratégie autre que la stratégie globale, exécutez et vérifiez que *-AllowBroadcastScheduling* est défini sur *true*:</span><span class="sxs-lookup"><span data-stu-id="df515-123">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="df515-124">**Vous voulez que le calendrier des événements dynamiques soit désactivé au sein de votre organisation**</span><span class="sxs-lookup"><span data-stu-id="df515-124">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="df515-125">Désactiver la planification des événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-125">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="df515-126">Attribuer à tous les utilisateurs de votre organisation la stratégie globale, exécuter :</span><span class="sxs-lookup"><span data-stu-id="df515-126">Assign all users in your organization to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="df515-127">**Vous voulez qu’un grand nombre d’utilisateurs puisse planifier des événements en direct et empêcher un ensemble d’utilisateurs de les planifier**</span><span class="sxs-lookup"><span data-stu-id="df515-127">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="df515-128">Exécutez et vérifiez que *AllowBroadcastScheduling* est défini sur *true*:</span><span class="sxs-lookup"><span data-stu-id="df515-128">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```PowerShell
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="df515-129">Puis affectez un ou des utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-129">Then assign a user or users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="df515-130">Créer une nouvelle stratégie qui n’autorise pas la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-130">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy
```
<span data-ttu-id="df515-131">Désactiver la planification des événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-131">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingPolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="df515-132">Assigner des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-132">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingPolicy -Verbose
```
<span data-ttu-id="df515-133">**Vous voulez désactiver la planification d’événements en direct pour un grand nombre d’utilisateurs et permettre à un utilisateur de les planifier**</span><span class="sxs-lookup"><span data-stu-id="df515-133">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="df515-134">Désactiver la planification des événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-134">Disable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="df515-135">Ensuite, attribuez ces utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-135">Then assign those users to the global policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="df515-136">Créer une stratégie pour autoriser la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-136">Create a policy to allow live events scheduling, run:</span></span>
```PowerShell
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="df515-137">Activez la planification des événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-137">Enable live events scheduling, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="df515-138">Assigner des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="df515-138">Then assign users to this policy, run:</span></span>
```PowerShell
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="df515-139">Définir qui peut participer à des événements en direct</span><span class="sxs-lookup"><span data-stu-id="df515-139">Set who can join live events</span></span>
 
<span data-ttu-id="df515-140">Définissez la stratégie globale pour autoriser les utilisateurs à créer des événements que tout le monde, y compris les utilisateurs anonymes, peuvent participer :</span><span class="sxs-lookup"><span data-stu-id="df515-140">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="df515-141">Définir l’option d’enregistrement pour les événements en direct</span><span class="sxs-lookup"><span data-stu-id="df515-141">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="df515-142">Ce paramètre s’applique uniquement aux événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="df515-142">This setting applies only to events produced in Teams.</span></span>

<span data-ttu-id="df515-143">Définissez la stratégie globale pour désactiver l’enregistrement des événements en direct :</span><span class="sxs-lookup"><span data-stu-id="df515-143">Set the global policy to disable recording for live events:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-live-captions-and-subtitles-in-live-events"></a><span data-ttu-id="df515-144">Définir des légendes et des sous-titres en direct dans les événements en direct</span><span class="sxs-lookup"><span data-stu-id="df515-144">Set live captions and subtitles in live events</span></span>
> [!NOTE]
> <span data-ttu-id="df515-145">Ce paramètre s’applique uniquement aux événements produits dans Teams.</span><span class="sxs-lookup"><span data-stu-id="df515-145">This setting applies only to events produced in Teams.</span></span> 

<span data-ttu-id="df515-146">Définissez la stratégie globale pour activer les légendes dynamiques et les sous-titres (transcription) pour les participants au service :</span><span class="sxs-lookup"><span data-stu-id="df515-146">Set the global policy to turn on live captions and subtitles (transcription) for event attendees:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="df515-147">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="df515-147">Related topics</span></span>
- [<span data-ttu-id="df515-148">Configurer les événements en direct Teams</span><span class="sxs-lookup"><span data-stu-id="df515-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
- [<span data-ttu-id="df515-149">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="df515-149">Teams PowerShell overview</span></span>](../teams-powershell-overview.md)

