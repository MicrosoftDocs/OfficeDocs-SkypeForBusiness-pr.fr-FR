---
title: Utilisation de PowerShell pour définir des stratégies d’événements en direct dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 10/23/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
description: Exemples illustrant comment utiliser PowerShell pour définir des stratégies dans les équipes pour contrôler qui peut contenir des événements en direct dans votre organisation et les fonctionnalités qui sont disponibles dans les événements qu’ils créent
appliesto:
- Microsoft Teams
ms.openlocfilehash: f802c2b67c0a4cd4b0838dd9aeec9c4bbf884968
ms.sourcegitcommit: 2e9761a3b195d31080bff3c9cc17a18adcd5350e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2018
ms.locfileid: "25749166"
---
# <a name="use-powershell-to-set-live-events-policies-in-microsoft-teams"></a><span data-ttu-id="2ca59-103">Utilisation de PowerShell pour définir des stratégies d’événements en direct dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ca59-103">Use PowerShell to set live events policies in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="2ca59-104">Vous pouvez utiliser les applets de commande Windows PowerShell suivante pour configurer et affecter des paramètres de stratégie pour les événements en temps réel dans les équipes :</span><span class="sxs-lookup"><span data-stu-id="2ca59-104">You can use the following Windows PowerShell cmdlets to set and assign policy settings for live events in Teams:</span></span> 
- [<span data-ttu-id="2ca59-105">Get-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2ca59-105">Get-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2ca59-106">Set-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2ca59-106">Set-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2ca59-107">Nouvelle CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2ca59-107">New-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingbroadcastpolicy?view=skype-ps)
- [<span data-ttu-id="2ca59-108">Grant-CsTeamsMeetingBroadcastPolicy</span><span class="sxs-lookup"><span data-stu-id="2ca59-108">Grant-CsTeamsMeetingBroadcastPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingbroadcastpolicy?view=skype-ps)

<span data-ttu-id="2ca59-109">Voici quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="2ca59-109">Here's some examples.</span></span>

## <a name="allow-users-to-schedule-live-events"></a><span data-ttu-id="2ca59-110">Permettre aux utilisateurs de planifier des événements en direct</span><span class="sxs-lookup"><span data-stu-id="2ca59-110">Allow users to schedule live events</span></span> 

> [!NOTE]
> <span data-ttu-id="2ca59-111">Ces exemples sont pour les événements de démarrage rapide.</span><span class="sxs-lookup"><span data-stu-id="2ca59-111">These examples are for quick start events.</span></span> <span data-ttu-id="2ca59-112">Pour les événements de codage externe, il existe des étapes supplémentaires que vous devez effectuer.</span><span class="sxs-lookup"><span data-stu-id="2ca59-112">For external encoder events, there are additional steps you must do.</span></span> <span data-ttu-id="2ca59-113">Pour plus d’informations, voir [permettent aux utilisateurs de planifier des événements de codage externe](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span><span class="sxs-lookup"><span data-stu-id="2ca59-113">For more information, see [Enable users to schedule external encoder events](set-up-for-teams-live-events.md#enable-users-to-schedule-external-encoder-events).</span></span>

<span data-ttu-id="2ca59-114">**Autoriser un utilisateur à organiser des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="2ca59-114">**Allow a user to schedule live events**</span></span>

<span data-ttu-id="2ca59-115">Si l’utilisateur est affecté à la stratégie globale, exécuter et vérifiez que le paramètre *AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="2ca59-115">If the user is assigned the global policy, run and verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="2ca59-116">Affecter l’utilisateur à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-116">Then assign the user to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

### <a name="user-scenarios"></a><span data-ttu-id="2ca59-117">Scénarios utilisateur</span><span class="sxs-lookup"><span data-stu-id="2ca59-117">User scenarios</span></span>
<span data-ttu-id="2ca59-118">**Vous que tous les utilisateurs dans votre organisation pour pouvoir planifier des événements en direct**</span><span class="sxs-lookup"><span data-stu-id="2ca59-118">**You want all users in your organization to be able to schedule live events**</span></span>

<span data-ttu-id="2ca59-119">Si les utilisateurs sont affectés à la stratégie globale, exécutez et vérifiez *AllowBroadcastScheduling* \* est défini sur *True*:</span><span class="sxs-lookup"><span data-stu-id="2ca59-119">If users are assigned the global policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="2ca59-120">Si les utilisateurs sont affectés à une stratégie de la stratégie globale, exécuter et vérifiez que l’option *-AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="2ca59-120">If users are assigned a policy other than the global policy, run and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```
<span data-ttu-id="2ca59-121">**Vous souhaitez que les événements live désactivé au sein de votre organisation de la planification**</span><span class="sxs-lookup"><span data-stu-id="2ca59-121">**You want live events scheduling to be disabled across your organization**</span></span>

<span data-ttu-id="2ca59-122">Désactiver la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-122">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="2ca59-123">Affecter tous les utilisateurs de votre organisation à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-123">Assign all users in your organization to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="2ca59-124">**Vous souhaitez un grand nombre d’utilisateurs puissent planifier des événements en direct et empêcher un ensemble d’utilisateurs de leur planification**</span><span class="sxs-lookup"><span data-stu-id="2ca59-124">**You want a large number of users to be able to schedule live events and prevent a set of users from scheduling them**</span></span>

<span data-ttu-id="2ca59-125">Exécutez et vérifiez que *AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="2ca59-125">Run and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -Identity Global
```
<span data-ttu-id="2ca59-126">Puis affecter un ou plusieurs utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-126">Then assign a user or users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="2ca59-127">Créer une nouvelle stratégie qui n’autorise pas la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-127">Create a new policy that doesn't allow scheduling live events, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="2ca59-128">Désactiver la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-128">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="2ca59-129">Puis affecter des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-129">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="2ca59-130">**Pour désactiver des événements live planification pour un grand nombre d’utilisateurs en autorisant un ensemble d’utilisateurs à l’échéancier**</span><span class="sxs-lookup"><span data-stu-id="2ca59-130">**You want to disable live event scheduling for a large number of the users and allow a set of users to schedule them**</span></span>

<span data-ttu-id="2ca59-131">Désactiver la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-131">Disable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="2ca59-132">Puis affecter ces utilisateurs à la stratégie globale, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-132">Then assign those users to the global policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="2ca59-133">Créer une stratégie pour autoriser la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-133">Create a policy to allow live events scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="2ca59-134">Activer la planification d’événements en direct, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-134">Enable live events scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="2ca59-135">Puis affecter des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-135">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```
## <a name="set-who-can-join-live-events"></a><span data-ttu-id="2ca59-136">Set qui peut participer à des événements en direct</span><span class="sxs-lookup"><span data-stu-id="2ca59-136">Set who can join live events</span></span>
 
<span data-ttu-id="2ca59-137">Définir la stratégie globale pour permettre aux utilisateurs de créer des événements que tout le monde, y compris les utilisateurs anonymes, peut participer, exécutez :</span><span class="sxs-lookup"><span data-stu-id="2ca59-137">Set the global policy to allow users to create events that everyone, including anonymous users, can attend, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="set-the-recording-option-for-live-events"></a><span data-ttu-id="2ca59-138">Définissez l’option d’enregistrement des événements live</span><span class="sxs-lookup"><span data-stu-id="2ca59-138">Set the recording option for live events</span></span>
> [!NOTE]
> <span data-ttu-id="2ca59-139">Ce paramètre s’applique uniquement aux événements de démarrage rapide.</span><span class="sxs-lookup"><span data-stu-id="2ca59-139">This setting applies only to quick start events.</span></span>

<span data-ttu-id="2ca59-140">Définir la stratégie globale pour désactiver l’enregistrement des événements live :</span><span class="sxs-lookup"><span data-stu-id="2ca59-140">Set the global policy to disable recording for live events:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="set-transcription-and-translation-in-live-events-coming-soon"></a><span data-ttu-id="2ca59-141">Définir la transcription et traduction dans les événements live (bientôt disponible)</span><span class="sxs-lookup"><span data-stu-id="2ca59-141">Set transcription and translation in live events (coming soon)</span></span>
> [!NOTE]
> <span data-ttu-id="2ca59-142">Ce paramètre s’applique uniquement aux événements de démarrage rapide.</span><span class="sxs-lookup"><span data-stu-id="2ca59-142">This setting applies only to quick start events.</span></span> 

<span data-ttu-id="2ca59-143">Définir la stratégie globale pour activer transcription et traduction sur des participants d’événement :</span><span class="sxs-lookup"><span data-stu-id="2ca59-143">Set the global policy to turn on transcription and translation on for event attendees:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```

### <a name="related-topics"></a><span data-ttu-id="2ca59-144">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="2ca59-144">Related topics</span></span>
- [<span data-ttu-id="2ca59-145">Configurer des équipes événements en direct</span><span class="sxs-lookup"><span data-stu-id="2ca59-145">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)


