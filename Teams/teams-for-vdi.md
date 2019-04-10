---
title: Équipes pour l’Infrastructure de bureau virtualisé
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 03/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Découvrez comment exécuter Microsoft Teams dans un environnement virtualisé Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30577fc8ee2628520bca7329f651f07cecfe6553
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "31752705"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="d228f-103">Équipes pour l’Infrastructure de bureau virtualisé</span><span class="sxs-lookup"><span data-stu-id="d228f-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="d228f-104">Cet article décrit les exigences et les limitations de l’utilisation de Microsoft Teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="d228f-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="d228f-105">What ' s VDI ?</span><span class="sxs-lookup"><span data-stu-id="d228f-105">What is VDI?</span></span>

<span data-ttu-id="d228f-106">Infrastructure VDI (Virtual Desktop) est la technologie de virtualisation qui héberge un système d’exploitation et des applications sur un serveur dans un centre de données centralisé.</span><span class="sxs-lookup"><span data-stu-id="d228f-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="d228f-107">Cela permet une expérience entièrement personnalisée aux utilisateurs avec une source centralisée entièrement sécurisée et de conformité.</span><span class="sxs-lookup"><span data-stu-id="d228f-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="d228f-108">Actuellement, les équipes dans un environnement virtualisé est disponible avec prise en charge des fonctionnalités de collaboration et de conversation avec un ordinateur dédié de virtualisé permanente (VM).</span><span class="sxs-lookup"><span data-stu-id="d228f-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="d228f-109">Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.</span><span class="sxs-lookup"><span data-stu-id="d228f-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="d228f-110">Configuration requise des équipes</span><span class="sxs-lookup"><span data-stu-id="d228f-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="d228f-111">Définir des stratégies pour désactiver l’appel et fonctionnalités dans les équipes de réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="d228f-112">Les équipes appelant et l’expérience de réunion n’est pas optimisé pour un environnement VDI (bientôt disponible).</span><span class="sxs-lookup"><span data-stu-id="d228f-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="d228f-113">Nous vous recommandons de que définir des stratégies de niveau utilisateur pour désactiver l’appel et fonctionnalités dans les équipes de réunion.</span><span class="sxs-lookup"><span data-stu-id="d228f-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="d228f-114">Vous pouvez toujours choisir d’exécuter des équipes entièrement dans VDI à l’aide de l’application de bureau équipes ou le web app.</span><span class="sxs-lookup"><span data-stu-id="d228f-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="d228f-115">Toutefois, nous vous recommandons de définir les stratégies d’éviter de compromettre l’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="d228f-116">Elle peut prendre un certain temps (quelques heures) pour propager les modifications de stratégie.</span><span class="sxs-lookup"><span data-stu-id="d228f-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="d228f-117">Si vous ne voyez pas immédiatement les modifications pour un compte donné, essayez à nouveau dans quelques heures.</span><span class="sxs-lookup"><span data-stu-id="d228f-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="d228f-118">Lors de l’appel des équipes et des réunions sont optimisées pour une utilisation dans des environnements de bureau virtuels, vous pouvez restaurer ces stratégies et permettre aux utilisateurs d’utiliser des équipes comme ils le feriez normalement.</span><span class="sxs-lookup"><span data-stu-id="d228f-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="d228f-119">Appels</span><span class="sxs-lookup"><span data-stu-id="d228f-119">Calling</span></span>

<span data-ttu-id="d228f-120">Utilisez les applets de commande **CSTeamsCallingPolicy** pour contrôler si les utilisateurs sont autorisés à utiliser l’appel et options d’appel en privé et conversations de groupe.</span><span class="sxs-lookup"><span data-stu-id="d228f-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="d228f-121">Voici la liste des paramètres de stratégie et les valeurs recommandées.</span><span class="sxs-lookup"><span data-stu-id="d228f-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="d228f-122">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="d228f-122">Policy name</span></span>  |<span data-ttu-id="d228f-123">Description</span><span class="sxs-lookup"><span data-stu-id="d228f-123">Description</span></span> |<span data-ttu-id="d228f-124">Valeur recommandée</span><span class="sxs-lookup"><span data-stu-id="d228f-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="d228f-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="d228f-125">AllowCalling</span></span>    |<span data-ttu-id="d228f-126">Interopérabilité de contrôles capacités d’appel.</span><span class="sxs-lookup"><span data-stu-id="d228f-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="d228f-127">Permet d’activer cette fonctionnalité Skype pour les utilisateurs professionnels pour que les appels en tête-à-tête avec les utilisateurs des équipes et inversement.</span><span class="sxs-lookup"><span data-stu-id="d228f-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="d228f-128">La valeur False pour empêcher les appels Skype pour les utilisateurs professionnels d’arrivée dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="d228f-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="d228f-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="d228f-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="d228f-130">Contrôle si l’application d’appel est disponible dans la barre d’application sur le côté gauche du client équipes et si les utilisateurs voient appel et vidéo dans la conversation privée, les options d’appel</span><span class="sxs-lookup"><span data-stu-id="d228f-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="d228f-131">La valeur False pour supprimer l’application de l’appel de la barre d’application sur le côté gauche des équipes et de supprimer les options d’appel appel et la vidéo dans la conversation privée.</span><span class="sxs-lookup"><span data-stu-id="d228f-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="d228f-132">Créer et affecter une stratégie d’appel</span><span class="sxs-lookup"><span data-stu-id="d228f-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="d228f-133">Démarrer une session Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="d228f-134">Se connecter au connecteur Skype en ligne.</span><span class="sxs-lookup"><span data-stu-id="d228f-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="d228f-135">Afficher la liste des options de stratégie d’appel.</span><span class="sxs-lookup"><span data-stu-id="d228f-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="d228f-136">Recherchez l’option stratégie intégrée où toutes les stratégies d’appel sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d228f-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="d228f-137">Il se présente comme suit.</span><span class="sxs-lookup"><span data-stu-id="d228f-137">It looks like this.</span></span>
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. <span data-ttu-id="d228f-138">Appliquer l’option de stratégie intégrée DisallowCalling à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="d228f-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="d228f-139">Pour plus d’informations sur les équipes appelant des stratégies, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d228f-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="d228f-140">Réunions</span><span class="sxs-lookup"><span data-stu-id="d228f-140">Meetings</span></span>

<span data-ttu-id="d228f-141">Utilisez les applets de commande **CsTeamsMeetingPolicy** pour contrôler le type de réunions que les utilisateurs peuvent créer, les fonctionnalités auxquels ils peuvent accéder dans une réunion et les fonctionnalités de réunion qui sont accessibles aux utilisateurs anonymes et externes.</span><span class="sxs-lookup"><span data-stu-id="d228f-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="d228f-142">Voici la liste des paramètres de stratégie et les valeurs recommandées.</span><span class="sxs-lookup"><span data-stu-id="d228f-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="d228f-143">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="d228f-143">Policy Name</span></span> |<span data-ttu-id="d228f-144">Description</span><span class="sxs-lookup"><span data-stu-id="d228f-144">Description</span></span>|<span data-ttu-id="d228f-145">Valeur recommandée</span><span class="sxs-lookup"><span data-stu-id="d228f-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="d228f-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d228f-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="d228f-147">Détermine si un utilisateur est autorisé à planifier des réunions privées.</span><span class="sxs-lookup"><span data-stu-id="d228f-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="d228f-148">La valeur False pour empêcher l’utilisateur de pouvoir planifier des réunions privées.</span><span class="sxs-lookup"><span data-stu-id="d228f-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="d228f-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="d228f-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="d228f-150">Détermine si un utilisateur est autorisé à planifier des réunions de canal.</span><span class="sxs-lookup"><span data-stu-id="d228f-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="d228f-151">La valeur False pour empêcher l’utilisateur de pouvoir planifier des réunions de canal.</span><span class="sxs-lookup"><span data-stu-id="d228f-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="d228f-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="d228f-152">AllowMeetNow</span></span> |<span data-ttu-id="d228f-153">Détermine si un utilisateur est autorisé à créer ou démarrer des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="d228f-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="d228f-154">Définissez cette valeur False pour interdire à l’utilisateur de pouvoir démarrer des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="d228f-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="d228f-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="d228f-155">ScreenSharingMode</span></span> | <span data-ttu-id="d228f-156">Détermine le mode dans lequel un utilisateur est autorisé à partager leur écran dans les appels ou des réunions.</span><span class="sxs-lookup"><span data-stu-id="d228f-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="d228f-157">La valeur désactivé pour empêcher l’utilisateur de partager leurs écrans</span><span class="sxs-lookup"><span data-stu-id="d228f-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="d228f-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="d228f-158">AllowIPVideo</span></span> |<span data-ttu-id="d228f-159">Détermine si la vidéo est activée dans les réunions ou les appels d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="d228f-160">La valeur False pour empêcher l’utilisateur de partager leur vidéo</span><span class="sxs-lookup"><span data-stu-id="d228f-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="d228f-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="d228f-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="d228f-162">Détermine si les utilisateurs anonymes sont autorisés à appeler un numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="d228f-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="d228f-163">La valeur False pour empêcher les utilisateurs anonymes à partir d’un appel sortant</span><span class="sxs-lookup"><span data-stu-id="d228f-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="d228f-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="d228f-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="d228f-165">Détermine si les utilisateurs anonymes peuvent démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="d228f-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="d228f-166">La valeur False pour empêcher les utilisateurs de démarrer une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="d228f-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="d228f-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="d228f-168">Détermine si un utilisateur peut planifier des réunions d’équipes dans le client de bureau Outlook.</span><span class="sxs-lookup"><span data-stu-id="d228f-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="d228f-169">La valeur False pour empêcher un utilisateur de planifier des réunions d’équipes dans le client de bureau Outlook</span><span class="sxs-lookup"><span data-stu-id="d228f-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="d228f-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d228f-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="d228f-171">Détermine si les participants peuvent demander ou donner le contrôle du partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="d228f-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="d228f-172">La valeur False pour empêcher l’utilisateur d’octroyer et demander le contrôle à une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="d228f-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d228f-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="d228f-174">Détermine si les participants externes peuvent demander ou donner le contrôle du partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="d228f-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="d228f-175">La valeur False pour empêcher un utilisateur externe de donner, demander le contrôle à une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="d228f-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="d228f-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="d228f-177">Détermine si le partage de PowerPoint est autorisé dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="d228f-178">La valeur False pour empêcher un utilisateur à partir du partage de fichiers PowerPoint dans une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="d228f-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="d228f-179">AllowWhiteboard</span></span> | <span data-ttu-id="d228f-180">Détermine si le tableau blanc est autorisée dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="d228f-181">La valeur False pour empêcher le tableau blanc dans une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="d228f-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="d228f-182">AllowTranscription</span></span> |<span data-ttu-id="d228f-183">Détermine si les légendes en temps réel et/ou postérieures à la réunions et des transcriptions sont autorisées dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="d228f-184">La valeur False pour empêcher la transcription et des légendes à une réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="d228f-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="d228f-185">AllowSharedNotes</span></span> | <span data-ttu-id="d228f-186">Détermine si les utilisateurs sont autorisés à prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="d228f-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="d228f-187">La valeur False pour empêcher les utilisateurs de prendre des notes partagées</span><span class="sxs-lookup"><span data-stu-id="d228f-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="d228f-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="d228f-188">MediaBitRateKB</span></span> |<span data-ttu-id="d228f-189">Détermine la vitesse de transmission multimédia pour audio/vidéo / d’application dans les réunions, les transmissions de partage</span><span class="sxs-lookup"><span data-stu-id="d228f-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="d228f-190">Valeur suggérée est 5 000 (5 Mo).</span><span class="sxs-lookup"><span data-stu-id="d228f-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="d228f-191">Vous pouvez modifier en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d228f-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="d228f-192">Créer et attribuer une stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="d228f-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="d228f-193">Démarrer une session Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d228f-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="d228f-194">Se connecter au connecteur Skype en ligne.</span><span class="sxs-lookup"><span data-stu-id="d228f-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="d228f-195">Afficher la liste des options de la stratégie de réunion.</span><span class="sxs-lookup"><span data-stu-id="d228f-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="d228f-196">Recherchez l’option stratégie intégrée où toutes les stratégies de réunion sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d228f-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="d228f-197">Il se présente comme suit.</span><span class="sxs-lookup"><span data-stu-id="d228f-197">It looks like this.</span></span>
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AlowTranscription                           : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="d228f-198">Appliquer l’option de stratégie intégrée AllOff à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="d228f-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="d228f-199">Pour plus d’informations sur les stratégies de réunion équipes, voir [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="d228f-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="d228f-200">Configuration requise de fournisseur de la virtualisation</span><span class="sxs-lookup"><span data-stu-id="d228f-200">Virtualization provider requirements</span></span>

<span data-ttu-id="d228f-201">L’application équipes a été validée sur les principaux fournisseurs de solutions de virtualisation.</span><span class="sxs-lookup"><span data-stu-id="d228f-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="d228f-202">Avec plusieurs fournisseurs de marché, consultez votre fournisseur de solutions de virtualisation pour vérifier la configuration minimale requise est respectée.</span><span class="sxs-lookup"><span data-stu-id="d228f-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="d228f-203">Configuration requise de Machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="d228f-203">Virtual Machine requirements</span></span>

<span data-ttu-id="d228f-204">Avec les diverses charges de travail et les besoins des utilisateurs dans un environnement virtualisé, voici la configuration minimale recommandée de configuration de l’ordinateur virtuel.</span><span class="sxs-lookup"><span data-stu-id="d228f-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="d228f-205">Paramètre</span><span class="sxs-lookup"><span data-stu-id="d228f-205">Parameter</span></span>  |<span data-ttu-id="d228f-206">Mesure</span><span class="sxs-lookup"><span data-stu-id="d228f-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="d228f-207">processeurs virtuels</span><span class="sxs-lookup"><span data-stu-id="d228f-207">vCPU</span></span>    |  <span data-ttu-id="d228f-208">2 cœurs</span><span class="sxs-lookup"><span data-stu-id="d228f-208">2 cores</span></span>       |
|<span data-ttu-id="d228f-209">RAM</span><span class="sxs-lookup"><span data-stu-id="d228f-209">RAM</span></span>     |  <span data-ttu-id="d228f-210">4 GO</span><span class="sxs-lookup"><span data-stu-id="d228f-210">4 GB</span></span>      |
|<span data-ttu-id="d228f-211">Stockage</span><span class="sxs-lookup"><span data-stu-id="d228f-211">Storage</span></span>     | <span data-ttu-id="d228f-212">8 Go</span><span class="sxs-lookup"><span data-stu-id="d228f-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="d228f-213">Configuration requise du système d’exploitation Machine virtuelle</span><span class="sxs-lookup"><span data-stu-id="d228f-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="d228f-214">Les systèmes d’exploitation pris en charge pour l’ordinateur virtuel sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="d228f-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="d228f-215">Windows 10 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="d228f-215">Windows 10 and later</span></span>
- <span data-ttu-id="d228f-216">Windows Server 2012 R2 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="d228f-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="d228f-217">Installer des équipes sur VDI</span><span class="sxs-lookup"><span data-stu-id="d228f-217">Install Teams on VDI</span></span>

<span data-ttu-id="d228f-218">Voici le processus et les outils nécessaires pour déployer l’application de bureau équipes.</span><span class="sxs-lookup"><span data-stu-id="d228f-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="d228f-219">Téléchargez le package MSI équipes à l’aide d’un des liens suivants en fonction de l’environnement.</span><span class="sxs-lookup"><span data-stu-id="d228f-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="d228f-220">Nous vous recommandons la version 64 bits pour une VM VDI avec un système d’exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="d228f-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="d228f-221">version 32 bits</span><span class="sxs-lookup"><span data-stu-id="d228f-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="d228f-222">version 64 bits</span><span class="sxs-lookup"><span data-stu-id="d228f-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="d228f-223">Exécutez la commande suivante pour installer le fichier MSI de VM VDI (ou effectuer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="d228f-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="d228f-224">Cela installe des équipes pour les fichiers de programme.</span><span class="sxs-lookup"><span data-stu-id="d228f-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="d228f-225">À ce stade, le programme d’installation or image est terminée.</span><span class="sxs-lookup"><span data-stu-id="d228f-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="d228f-226">La prochaine ouverture de session interactive démarre les équipes et demande des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="d228f-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="d228f-227">Notez qu’il n’est pas possible de désactiver le démarrage automatique des équipes lors de l’installation des équipes sur VDI à l’aide de la propriété ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="d228f-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="d228f-228">Exécutez la commande suivante pour désinstaller le fichier MSI de la VM VDI (ou préparer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="d228f-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="d228f-229">Les équipes est désinstallé à partir des fichiers de programme.</span><span class="sxs-lookup"><span data-stu-id="d228f-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="d228f-230">Problèmes connus et limitations</span><span class="sxs-lookup"><span data-stu-id="d228f-230">Known issues and limitations</span></span>

<span data-ttu-id="d228f-231">Les éléments suivants sont problèmes connus et limitations pour les équipes sur VDI.</span><span class="sxs-lookup"><span data-stu-id="d228f-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="d228f-232">**Déploiements de type Shared session hôte**: déploiements de type Shared session hôte (par exemple, non persistants VM configuration partagé) ne sont pas dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="d228f-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="d228f-233">**Appel et réunions**:</span><span class="sxs-lookup"><span data-stu-id="d228f-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="d228f-234">Appel et scénarios de réunion ne sont pas optimisés pour VDI.</span><span class="sxs-lookup"><span data-stu-id="d228f-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="d228f-235">Ces scénarios sont médiocres.</span><span class="sxs-lookup"><span data-stu-id="d228f-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="d228f-236">Nous recommandons l’utilisation de stratégies au niveau de l’utilisateur comme décrit dans la section [définir des stratégies pour désactiver l’appel et fonctionnalités dans les équipes de réunion](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="d228f-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="d228f-237">Appliquer les stratégies décrites dans cet article a un impact sur la possibilité d’utiliser les fonctionnalités d’appel et de réunion, qui peut affecter d’autres utilisateurs de votre organisation en fonction d’autres stratégies.</span><span class="sxs-lookup"><span data-stu-id="d228f-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="d228f-238">Si les utilisateurs de votre organisation utilisent des clients de non VDI, vous pouvez choisir de ne pas appliquer les stratégies.</span><span class="sxs-lookup"><span data-stu-id="d228f-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="d228f-239">**Participer à des appels et les réunions créées par les autres utilisateurs**: bien que les stratégies d’empêcher les utilisateurs de créer des réunions, ils peuvent toujours participer aux réunions si un autre utilisateur se connecte à leur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="d228f-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="d228f-240">Ces réunions, la possibilité de l’utilisateur à partager une vidéo, utiliser un tableau blanc et autres fonctionnalités dépendent si vous avez désactivé les fonctionnalités de TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="d228f-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="d228f-241">**Contenu mis en cache**: si l’environnement virtuel dans les équipes est en cours d’exécution n’est pas persistant (et données sont nettoyées à la fin de chaque session de l’utilisateur), les utilisateurs peuvent remarquer une dégradation des performances en raison de l’actualisation du contenu, quelle que soit ou non l’utilisateur accède à la même contenu dans une session précédente.</span><span class="sxs-lookup"><span data-stu-id="d228f-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="d228f-242">**Mises à jour du client**: équipes sur VDI n’est pas automatiquement mis à jour de la même manière que les clients non - VDI équipes.</span><span class="sxs-lookup"><span data-stu-id="d228f-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="d228f-243">Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau fichier MSI, comme décrit dans la section [Installer des équipes sur VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="d228f-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="d228f-244">Vous devez désinstaller la version actuelle de mise à jour vers une version plus récente.</span><span class="sxs-lookup"><span data-stu-id="d228f-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="d228f-245">**Expérience utilisateur**: équipes l’expérience de l’utilisateur dans un environnement VDI peut être différente d’un environnement non VDI.</span><span class="sxs-lookup"><span data-stu-id="d228f-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="d228f-246">Les différences peuvent être en raison des paramètres de stratégie et/ou fonctionnalité prise en charge dans l’environnement.</span><span class="sxs-lookup"><span data-stu-id="d228f-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="d228f-247">Pour les équipes qui ne sont pas liés à VDI problèmes connus, voir [problèmes connus relatifs aux équipes Microsoft](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d228f-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d228f-248">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="d228f-248">Related topics</span></span>

- [<span data-ttu-id="d228f-249">Installer Microsoft Teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="d228f-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)