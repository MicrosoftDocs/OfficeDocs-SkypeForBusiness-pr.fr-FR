---
title: Teams pour une infrastructure bureau virtualisée(VDI)
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Découvrez comment exécuter Microsoft teams dans un environnement VDI (Virtual Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e88a5fb4e8522a94389e3bad24ddc3da8283a53
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588142"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a><span data-ttu-id="b480e-103">Teams pour une infrastructure bureau virtualisée(VDI)</span><span class="sxs-lookup"><span data-stu-id="b480e-103">Teams for Virtualized Desktop Infrastructure</span></span>

<span data-ttu-id="b480e-104">Cet article décrit les exigences et limitations relatives à l’utilisation de Microsoft teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="b480e-104">This article describes the requirements and limitations for using Microsoft Teams in a virtualized environment.</span></span>

## <a name="what-is-vdi"></a><span data-ttu-id="b480e-105">Qu’est-ce qu’un infrastructure VDI?</span><span class="sxs-lookup"><span data-stu-id="b480e-105">What is VDI?</span></span>

<span data-ttu-id="b480e-106">La technologie VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation et des applications de bureau sur un serveur centralisé dans un centre de données.</span><span class="sxs-lookup"><span data-stu-id="b480e-106">Virtual Desktop Infrastructure (VDI) is virtualization technology that hosts a desktop operating system and applications on a centralized server in a data center.</span></span> <span data-ttu-id="b480e-107">Cela permet d’offrir une expérience de bureau entièrement personnalisée aux utilisateurs dotés d’une source centralisée entièrement sécurisée et compatible.</span><span class="sxs-lookup"><span data-stu-id="b480e-107">This enables a fully personalized desktop experience to users with a fully secured and compliant centralized source.</span></span> 
 
<span data-ttu-id="b480e-108">Pour le moment, teams dans un environnement virtualisé est disponible avec la prise en charge de la fonctionnalité de collaboration et de conversation avec un ordinateur virtuel permanent dédié.</span><span class="sxs-lookup"><span data-stu-id="b480e-108">Currently, Teams in a virtualized environment is available with support for collaboration and chat functionality with a dedicated persistent virtualized machine (VM).</span></span> <span data-ttu-id="b480e-109">Pour garantir une utilisation optimale des utilisateurs, suivez les recommandations de cet article.</span><span class="sxs-lookup"><span data-stu-id="b480e-109">To ensure an optimal user experience, follow the guidance in this article.</span></span> 

## <a name="teams-requirements"></a><span data-ttu-id="b480e-110">Exigences des équipes</span><span class="sxs-lookup"><span data-stu-id="b480e-110">Teams requirements</span></span>

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a><span data-ttu-id="b480e-111">Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion dans teams</span><span class="sxs-lookup"><span data-stu-id="b480e-111">Set policies to turn off calling and meeting functionality in Teams</span></span>

<span data-ttu-id="b480e-112">Les équipes d’appel et de réunion ne sont pas optimisées dans un environnement VDI (bientôt disponible).</span><span class="sxs-lookup"><span data-stu-id="b480e-112">The Teams calling and meeting experience isn't optimized for a VDI environment (coming soon).</span></span> <span data-ttu-id="b480e-113">Nous vous recommandons de définir les stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b480e-113">We recommend you set user-level policies to turn off calling and meeting functionality in Teams.</span></span>

<span data-ttu-id="b480e-114">Vous pouvez toujours choisir d’exécuter entièrement des équipes dans une infrastructure VDI à l’aide de l’application de bureau teams ou de l’application Web.</span><span class="sxs-lookup"><span data-stu-id="b480e-114">You can still choose to run Teams fully in VDI using either the Teams desktop app or web app.</span></span> <span data-ttu-id="b480e-115">Toutefois, nous vous recommandons de définir les stratégies afin d’éviter d’entraver l’utilisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-115">However, we recommend that you set the policies to avoid compromising the user experience.</span></span>  

<span data-ttu-id="b480e-116">L’exécution de la stratégie peut prendre un certain temps (quelques heures).</span><span class="sxs-lookup"><span data-stu-id="b480e-116">It can take some time (a few hours) for the policy changes to propagate.</span></span> <span data-ttu-id="b480e-117">Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez dans quelques heures.</span><span class="sxs-lookup"><span data-stu-id="b480e-117">If you don’t see changes for a given account immediately, try again in a few hours.</span></span>

> [!NOTE]
> <span data-ttu-id="b480e-118">Lorsque les équipes appelant et rendez-vous sont optimisées pour une utilisation dans les environnements de bureau virtuels, vous pouvez rétablir ces stratégies et permettre aux utilisateurs d’utiliser teams comme vous le feriez habituellement.</span><span class="sxs-lookup"><span data-stu-id="b480e-118">When Teams calling and meetings are optimized for use in virtual desktop environments, you can revert these policies and allow users to use Teams as they normally would.</span></span> 

#### <a name="calling"></a><span data-ttu-id="b480e-119">Appels</span><span class="sxs-lookup"><span data-stu-id="b480e-119">Calling</span></span>

<span data-ttu-id="b480e-120">Utilisez les applets de commande **CSTeamsCallingPolicy** pour contrôler si les utilisateurs sont autorisés à utiliser les options d’appel et d’appel dans les discussions privées et de groupe.</span><span class="sxs-lookup"><span data-stu-id="b480e-120">Use the **CSTeamsCallingPolicy** cmdlets to control whether users are allowed to use calling and calling options in private and group chats.</span></span> <span data-ttu-id="b480e-121">Voici la liste des paramètres de stratégie et des valeurs recommandées.</span><span class="sxs-lookup"><span data-stu-id="b480e-121">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b480e-122">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="b480e-122">Policy name</span></span>  |<span data-ttu-id="b480e-123">Description</span><span class="sxs-lookup"><span data-stu-id="b480e-123">Description</span></span> |<span data-ttu-id="b480e-124">Valeur recommandée</span><span class="sxs-lookup"><span data-stu-id="b480e-124">Recommended value</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b480e-125">AllowCalling</span><span class="sxs-lookup"><span data-stu-id="b480e-125">AllowCalling</span></span>    |<span data-ttu-id="b480e-126">Contrôle les fonctionnalités d’appel d’interopérabilité.</span><span class="sxs-lookup"><span data-stu-id="b480e-126">Controls interop calling capabilities.</span></span> <span data-ttu-id="b480e-127">L’activation de cette option permet aux utilisateurs de Skype entreprise d’avoir des appels en tête-à-tête avec les utilisateurs de Microsoft Teams, et vice versa.</span><span class="sxs-lookup"><span data-stu-id="b480e-127">Turning this on allows Skype for Business users to have one-on-one calls with Teams users and vice versa.</span></span>         |<span data-ttu-id="b480e-128">Valeur définie sur false pour empêcher les appels d’utilisateurs Skype entreprise dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b480e-128">Set to False to prevent calls from Skype for Business users landing in Teams.</span></span>          |
|<span data-ttu-id="b480e-129">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="b480e-129">AllowPrivateCalling</span></span>     | <span data-ttu-id="b480e-130">Indique si l’application à l’origine de l’appel est disponible dans la barre de l’application, sur le côté gauche du client teams et si les utilisateurs voient les options d’appel et de vidéo dans une conversation privée</span><span class="sxs-lookup"><span data-stu-id="b480e-130">Controls whether the Calling app is available in the app bar on the left side of the Teams client and whether users see Calling and Video call options in private chat</span></span>         |<span data-ttu-id="b480e-131">False pour supprimer l’application à l’origine de l’appel dans la barre de l’application, sur le côté gauche de teams, et supprimer les options d’appel et de vidéo dans une conversation privée.</span><span class="sxs-lookup"><span data-stu-id="b480e-131">Set to False to remove the Calling app from the app bar on the left side of Teams and to remove the Calling and Video call options in private chat.</span></span>          |

#### <a name="create-and-assign-a-calling-policy"></a><span data-ttu-id="b480e-132">Création et affectation d’une stratégie d’appel</span><span class="sxs-lookup"><span data-stu-id="b480e-132">Create and assign a calling policy</span></span>

1. <span data-ttu-id="b480e-133">Démarrez une session Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-133">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b480e-134">Connectez-vous au connecteur en ligne Skype.</span><span class="sxs-lookup"><span data-stu-id="b480e-134">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b480e-135">Affichez la liste des options de stratégie d’appel.</span><span class="sxs-lookup"><span data-stu-id="b480e-135">View a list of calling policy options.</span></span>

       Get-CsTeamsCallingPolicy
 
4. <span data-ttu-id="b480e-136">Recherchez l’option de stratégie intégrée dans laquelle toutes les stratégies d’appel sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="b480e-136">Look for the built-in policy option where all calling policies are disabled.</span></span> <span data-ttu-id="b480e-137">Elle se présente comme suit.</span><span class="sxs-lookup"><span data-stu-id="b480e-137">It looks like this.</span></span>
   
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

5. <span data-ttu-id="b480e-138">Appliquez l’option de stratégie intégrée à DisallowCalling à tous les utilisateurs qui utiliseront teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="b480e-138">Apply the DisallowCalling built-in policy option to all users who will be using Teams in a virtualized environment.</span></span>

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

<span data-ttu-id="b480e-139">Pour plus d’informations sur les stratégies d’appel d’équipe, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b480e-139">For more information about Teams calling policies, see [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).</span></span>

#### <a name="meetings"></a><span data-ttu-id="b480e-140">Réunions</span><span class="sxs-lookup"><span data-stu-id="b480e-140">Meetings</span></span>

<span data-ttu-id="b480e-141">Utilisez les applets de commande **CsTeamsMeetingPolicy** pour contrôler le type de réunion que les utilisateurs peuvent créer, les fonctionnalités auxquelles ils peuvent accéder pendant une réunion, ainsi que les fonctionnalités de réunion disponibles pour les utilisateurs anonymes et externes.</span><span class="sxs-lookup"><span data-stu-id="b480e-141">Use the **CsTeamsMeetingPolicy** cmdlets to control the type of meetings that users can create, the features that they can access while in a meeting, and the meeting features that are available to anonymous and external users.</span></span> <span data-ttu-id="b480e-142">Voici la liste des paramètres de stratégie et des valeurs recommandées.</span><span class="sxs-lookup"><span data-stu-id="b480e-142">Here's the list of policy settings and recommended values.</span></span>

|<span data-ttu-id="b480e-143">Nom de la stratégie</span><span class="sxs-lookup"><span data-stu-id="b480e-143">Policy Name</span></span> |<span data-ttu-id="b480e-144">Description</span><span class="sxs-lookup"><span data-stu-id="b480e-144">Description</span></span>|<span data-ttu-id="b480e-145">Valeur recommandée</span><span class="sxs-lookup"><span data-stu-id="b480e-145">Recommended Value</span></span>                   |
|-------------------|-----------------|-----------------------|
|<span data-ttu-id="b480e-146">AllowPrivateMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b480e-146">AllowPrivateMeetingScheduling</span></span>  | <span data-ttu-id="b480e-147">Détermine si un utilisateur est autorisé à planifier des réunions privées.</span><span class="sxs-lookup"><span data-stu-id="b480e-147">Determines whether a user is allowed to schedule private meetings.</span></span>| <span data-ttu-id="b480e-148">Valeur définie sur false pour empêcher l’utilisateur d’être en mesure de planifier des réunions privées.</span><span class="sxs-lookup"><span data-stu-id="b480e-148">Set to False to prohibit the user from being able to schedule private meetings.</span></span>  |
|<span data-ttu-id="b480e-149">AllowChannelMeetingScheduling</span><span class="sxs-lookup"><span data-stu-id="b480e-149">AllowChannelMeetingScheduling</span></span>  | <span data-ttu-id="b480e-150">Détermine si un utilisateur est autorisé à planifier des réunions de canal.</span><span class="sxs-lookup"><span data-stu-id="b480e-150">Determines whether a user is allowed to schedule channel meetings.</span></span> | <span data-ttu-id="b480e-151">Valeur définie sur false pour empêcher l’utilisateur d’être en mesure de planifier des réunions de canal.</span><span class="sxs-lookup"><span data-stu-id="b480e-151">Set to False to prohibit the user from being able to schedule channel meetings.</span></span>                       |
|<span data-ttu-id="b480e-152">AllowMeetNow</span><span class="sxs-lookup"><span data-stu-id="b480e-152">AllowMeetNow</span></span> |<span data-ttu-id="b480e-153">Détermine si un utilisateur est autorisé à créer ou à démarrer des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b480e-153">Determines whether a user is allowed to create or start ad-hoc meetings.</span></span>              |  <span data-ttu-id="b480e-154">Définissez cette valeur sur false pour empêcher l’utilisateur de démarrer des réunions ad hoc.</span><span class="sxs-lookup"><span data-stu-id="b480e-154">Set this to False to prohibit the user from being able to start ad-hoc meetings.</span></span>                     |
|<span data-ttu-id="b480e-155">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="b480e-155">ScreenSharingMode</span></span> | <span data-ttu-id="b480e-156">Détermine le mode dans lequel un utilisateur est autorisé à partager son écran dans des appels ou des réunions.</span><span class="sxs-lookup"><span data-stu-id="b480e-156">Determines the mode in which a user is allowed to share their screen in calls or meetings.</span></span> | <span data-ttu-id="b480e-157">Défini sur Disabled pour empêcher l’utilisateur de partager son écran</span><span class="sxs-lookup"><span data-stu-id="b480e-157">Set to Disabled to prohibit the user from sharing their screens</span></span>                          |
|<span data-ttu-id="b480e-158">AllowIPVideo</span><span class="sxs-lookup"><span data-stu-id="b480e-158">AllowIPVideo</span></span> |<span data-ttu-id="b480e-159">Détermine si la vidéo est activée dans les réunions ou les appels d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-159">Determines whether video is enabled in a user's meetings or calls.</span></span>                  |    <span data-ttu-id="b480e-160">Valeur définie sur false pour empêcher l’utilisateur de partager sa vidéo</span><span class="sxs-lookup"><span data-stu-id="b480e-160">Set to False to prohibit the user from sharing their video</span></span>                                         |
| <span data-ttu-id="b480e-161">AllowAnonymousUsersToDialOut</span><span class="sxs-lookup"><span data-stu-id="b480e-161">AllowAnonymousUsersToDialOut</span></span> | <span data-ttu-id="b480e-162">Détermine si les utilisateurs anonymes sont autorisés à appeler un numéro PSTN.</span><span class="sxs-lookup"><span data-stu-id="b480e-162">Determines whether anonymous users are allowed to dial out to a PSTN number.</span></span> | <span data-ttu-id="b480e-163">Valeur définie sur false pour interdire aux utilisateurs anonymes de composer un numéro</span><span class="sxs-lookup"><span data-stu-id="b480e-163">Set to False to prohibit anonymous users from dialing out</span></span>                                  |
| <span data-ttu-id="b480e-164">AllowAnonymousUsersToStartMeeting</span><span class="sxs-lookup"><span data-stu-id="b480e-164">AllowAnonymousUsersToStartMeeting</span></span> | <span data-ttu-id="b480e-165">Détermine si les utilisateurs anonymes peuvent démarrer une réunion.</span><span class="sxs-lookup"><span data-stu-id="b480e-165">Determines whether anonymous users can start a meeting.</span></span>     |  <span data-ttu-id="b480e-166">Valeur définie sur false pour interdire aux utilisateurs de démarrer une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-166">Set to False to prohibit users from starting a meeting</span></span>                                            |
| <span data-ttu-id="b480e-167">AllowOutlookAddIn</span><span class="sxs-lookup"><span data-stu-id="b480e-167">AllowOutlookAddIn</span></span> |<span data-ttu-id="b480e-168">Détermine si un utilisateur peut planifier des réunions d’équipes dans le client de bureau Outlook.</span><span class="sxs-lookup"><span data-stu-id="b480e-168">Determines whether a user can schedule Teams meetings in the Outlook desktop client.</span></span>| <span data-ttu-id="b480e-169">Défini sur false pour empêcher un utilisateur de planifier des réunions teams dans le client de bureau Outlook</span><span class="sxs-lookup"><span data-stu-id="b480e-169">Set to False to prohibit a user from  scheduling Teams meetings in the Outlook desktop client</span></span>|
| <span data-ttu-id="b480e-170">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b480e-170">AllowParticipantGiveRequestControl</span></span>|<span data-ttu-id="b480e-171">Détermine si les participants peuvent demander ou donner le contrôle du partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="b480e-171">Determines whether participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b480e-172">Valeur définie sur false pour empêcher l’utilisateur d’attribuer et de demander le contrôle pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-172">Set to False to prohibit the user from giving and requesting control in a meeting</span></span>    |
| <span data-ttu-id="b480e-173">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="b480e-173">AllowExternalParticipantGiveRequestControl</span></span> | <span data-ttu-id="b480e-174">Détermine si les participants externes peuvent demander ou donner le contrôle du partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="b480e-174">Determines whether external participants can request or give control of screen sharing.</span></span>| <span data-ttu-id="b480e-175">Défini sur false pour interdire à un utilisateur externe de demander le contrôle pendant une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-175">Set to False to prohibit an external user from giving, requesting control in a meeting</span></span>|
|<span data-ttu-id="b480e-176">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="b480e-176">AllowPowerPointSharing</span></span>|<span data-ttu-id="b480e-177">Détermine si le partage PowerPoint est autorisé dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-177">Determines whether PowerPoint sharing is allowed in a user’s meetings.</span></span> |<span data-ttu-id="b480e-178">Défini sur false pour empêcher un utilisateur de partager des fichiers PowerPoint dans une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-178">Set to False to prohibit a user from sharing PowerPoint files in a meeting</span></span>  |
|<span data-ttu-id="b480e-179">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="b480e-179">AllowWhiteboard</span></span> | <span data-ttu-id="b480e-180">Détermine si le tableau blanc est autorisé dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-180">Determines whether whiteboard is allowed in a user’s meetings.</span></span> |   <span data-ttu-id="b480e-181">Valeur définie sur false pour interdire le tableau blanc dans une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-181">Set to False to prohibit whiteboard in a meeting</span></span> |
| <span data-ttu-id="b480e-182">AllowTranscription</span><span class="sxs-lookup"><span data-stu-id="b480e-182">AllowTranscription</span></span> |<span data-ttu-id="b480e-183">Détermine si les légendes et les transcriptions en temps réel et/ou après réunion sont autorisées dans les réunions d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-183">Determines whether real-time and/or post-meeting captions and transcriptions are allowed in a user's meetings.</span></span>|    <span data-ttu-id="b480e-184">Valeur false pour interdire la transcription et les légendes dans une réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-184">Set to False to prohibit transcription  and captions in a meeting</span></span>  |  
| <span data-ttu-id="b480e-185">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="b480e-185">AllowSharedNotes</span></span> | <span data-ttu-id="b480e-186">Détermine si les utilisateurs sont autorisés à prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="b480e-186">Determines whether users are allowed to take shared notes.</span></span> | <span data-ttu-id="b480e-187">Défini sur false pour interdire aux utilisateurs de suivre des notes partagées</span><span class="sxs-lookup"><span data-stu-id="b480e-187">Set to False to prohibit users from taking shared notes</span></span> |
|<span data-ttu-id="b480e-188">MediaBitRateKB</span><span class="sxs-lookup"><span data-stu-id="b480e-188">MediaBitRateKB</span></span> |<span data-ttu-id="b480e-189">Détermine le taux de bits média pour les transmissions du partage audio/vidéo/d’application en réunions.</span><span class="sxs-lookup"><span data-stu-id="b480e-189">Determines the media bit rate for audio/video/app sharing transmissions in meetings</span></span>  | <span data-ttu-id="b480e-190">La valeur suggérée est 5000 (5 Mo).</span><span class="sxs-lookup"><span data-stu-id="b480e-190">Suggested value is 5000 (5 MB).</span></span> <span data-ttu-id="b480e-191">Vous pouvez le modifier en fonction des besoins de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b480e-191">You can change it based on your organization’s needs.</span></span>| 

#### <a name="create-and-assign-a-meeting-policy"></a><span data-ttu-id="b480e-192">Création et affectation d’une stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-192">Create and assign a meeting policy</span></span>

1. <span data-ttu-id="b480e-193">Démarrez une session Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b480e-193">Start a Windows PowerShell session as an administrator.</span></span>
2. <span data-ttu-id="b480e-194">Connectez-vous au connecteur en ligne Skype.</span><span class="sxs-lookup"><span data-stu-id="b480e-194">Connect to the Skype Online Connector.</span></span>

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. <span data-ttu-id="b480e-195">Afficher une liste des options de stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="b480e-195">View a list of meeting policy options.</span></span>

       Get-CsTeamsMeetingPolicy
 
4. <span data-ttu-id="b480e-196">Recherchez l’option de stratégie prédéfinie dans laquelle toutes les stratégies de réunion sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="b480e-196">Look for the built-in policy option where all meeting policies are disabled.</span></span> <span data-ttu-id="b480e-197">Elle se présente comme suit.</span><span class="sxs-lookup"><span data-stu-id="b480e-197">It looks like this.</span></span>
   
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
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. <span data-ttu-id="b480e-198">Appliquez l’option de stratégie intégrée à AllOff à tous les utilisateurs qui utiliseront teams dans un environnement virtualisé.</span><span class="sxs-lookup"><span data-stu-id="b480e-198">Apply the AllOff built-in policy option to all users who will be using Teams in a virtualized environment.</span></span> 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 <span data-ttu-id="b480e-199">Pour plus d’informations sur les stratégies de réunion Teams, voir [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span><span class="sxs-lookup"><span data-stu-id="b480e-199">For more information about Teams meeting policies, see [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).</span></span>

### <a name="virtualization-provider-requirements"></a><span data-ttu-id="b480e-200">Configuration requise pour les fournisseurs de virtualisation</span><span class="sxs-lookup"><span data-stu-id="b480e-200">Virtualization provider requirements</span></span>

<span data-ttu-id="b480e-201">L’application teams a été validée sur les principaux fournisseurs de solutions de virtualisation.</span><span class="sxs-lookup"><span data-stu-id="b480e-201">The Teams app has been validated on leading virtualization solution providers.</span></span> <span data-ttu-id="b480e-202">Auprès de plusieurs fournisseurs de marché, contactez votre fournisseur de solutions de virtualisation pour vous assurer que les exigences minimales sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="b480e-202">With multiple market providers, consult your virtualization solution provider to ensure minimum requirements are met.</span></span>

### <a name="virtual-machine-requirements"></a><span data-ttu-id="b480e-203">Configuration requise pour les machines virtuelles</span><span class="sxs-lookup"><span data-stu-id="b480e-203">Virtual Machine requirements</span></span>

<span data-ttu-id="b480e-204">En ce qui concerne les diverses charges de travail et les besoins des utilisateurs dans un environnement virtualisé, voici la configuration minimale recommandée pour les ordinateurs virtuels.</span><span class="sxs-lookup"><span data-stu-id="b480e-204">With the diverse workloads and user needs in a virtualized environment, the following is the minimum recommended VM configuration.</span></span>

|<span data-ttu-id="b480e-205">Paramètre</span><span class="sxs-lookup"><span data-stu-id="b480e-205">Parameter</span></span>  |<span data-ttu-id="b480e-206">Action</span><span class="sxs-lookup"><span data-stu-id="b480e-206">Measure</span></span>  |
|---------|---------|
|<span data-ttu-id="b480e-207">CPU</span><span class="sxs-lookup"><span data-stu-id="b480e-207">vCPU</span></span>    |  <span data-ttu-id="b480e-208">2 cœurs</span><span class="sxs-lookup"><span data-stu-id="b480e-208">2 cores</span></span>       |
|<span data-ttu-id="b480e-209">RAM</span><span class="sxs-lookup"><span data-stu-id="b480e-209">RAM</span></span>     |  <span data-ttu-id="b480e-210">4 GO</span><span class="sxs-lookup"><span data-stu-id="b480e-210">4 GB</span></span>      |
|<span data-ttu-id="b480e-211">Stockage</span><span class="sxs-lookup"><span data-stu-id="b480e-211">Storage</span></span>     | <span data-ttu-id="b480e-212">8 Go</span><span class="sxs-lookup"><span data-stu-id="b480e-212">8 GB</span></span>       |

### <a name="virtual-machine-operating-system-requirements"></a><span data-ttu-id="b480e-213">Configuration requise pour le système d’exploitation de l’ordinateur virtuel</span><span class="sxs-lookup"><span data-stu-id="b480e-213">Virtual Machine operating system requirements</span></span>

<span data-ttu-id="b480e-214">Les systèmes d’exploitation pris en charge pour les VM sont les suivants:</span><span class="sxs-lookup"><span data-stu-id="b480e-214">The supported operating systems for VM are:</span></span>

- <span data-ttu-id="b480e-215">Windows 10 et versions ultérieures</span><span class="sxs-lookup"><span data-stu-id="b480e-215">Windows 10 and later</span></span>
- <span data-ttu-id="b480e-216">Windows Server 2012 R2 et version ultérieure</span><span class="sxs-lookup"><span data-stu-id="b480e-216">Windows Server 2012 R2 and later</span></span>

## <a name="install-teams-on-vdi"></a><span data-ttu-id="b480e-217">Installer teams sur un infrastructure VDI</span><span class="sxs-lookup"><span data-stu-id="b480e-217">Install Teams on VDI</span></span>

<span data-ttu-id="b480e-218">Voici le processus et les outils de déploiement de l’application de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="b480e-218">Here's the process and tools to deploy the Teams desktop app.</span></span> 

1. <span data-ttu-id="b480e-219">Téléchargez le package MSI teams à l’aide de l’un des liens suivants selon l’environnement.</span><span class="sxs-lookup"><span data-stu-id="b480e-219">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="b480e-220">Nous vous recommandons d’utiliser la version 64 bits d’un VM VDI doté d’un système d’exploitation 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b480e-220">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="b480e-221">version 32 bits</span><span class="sxs-lookup"><span data-stu-id="b480e-221">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="b480e-222">version 64 bits</span><span class="sxs-lookup"><span data-stu-id="b480e-222">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="b480e-223">Exécutez la commande suivante pour installer le MSI sur la machine virtuelle VDI (ou terminer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="b480e-223">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="b480e-224">Cette opération permet d’installer teams pour programmer des fichiers.</span><span class="sxs-lookup"><span data-stu-id="b480e-224">This installs Teams to Program Files.</span></span> <span data-ttu-id="b480e-225">À ce stade, la configuration de l’image Golden est terminée.</span><span class="sxs-lookup"><span data-stu-id="b480e-225">At this point, the golden image setup is complete.</span></span>
 
    <span data-ttu-id="b480e-226">La prochaine session interactive de connexion démarre teams et demande des informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="b480e-226">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="b480e-227">Notez qu’il n’est pas possible de désactiver le lancement automatique d’équipes lors de l’installation d’équipes sur VDI à l’aide de la propriété ALLUSER.</span><span class="sxs-lookup"><span data-stu-id="b480e-227">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span> 

3. <span data-ttu-id="b480e-228">Exécutez la commande suivante pour désinstaller le MSI de l’ordinateur virtuel VDI (ou préparer la mise à jour).</span><span class="sxs-lookup"><span data-stu-id="b480e-228">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="b480e-229">Cela a pour cela la désinstallation de teams.</span><span class="sxs-lookup"><span data-stu-id="b480e-229">This uninstalls Teams from Program Files.</span></span>

## <a name="known-issues-and-limitations"></a><span data-ttu-id="b480e-230">Problèmes connus et limitations</span><span class="sxs-lookup"><span data-stu-id="b480e-230">Known issues and limitations</span></span>

<span data-ttu-id="b480e-231">Vous trouverez ci-après des problèmes connus et des limitations applicables aux équipes sur VDI.</span><span class="sxs-lookup"><span data-stu-id="b480e-231">The following are known issues and limitations for Teams on VDI.</span></span>

- <span data-ttu-id="b480e-232">**Déploiements de type hôte de session partagée**: les déploiements de type hôte de session partagée (par exemple, configuration VM non persistante partagée) ne sont pas dans l’étendue.</span><span class="sxs-lookup"><span data-stu-id="b480e-232">**Shared session host type deployments**: Shared session host type deployments (for example, shared non-persistent VM configuration) aren't in scope.</span></span>
- <span data-ttu-id="b480e-233">**Appels et réunions**:</span><span class="sxs-lookup"><span data-stu-id="b480e-233">**Calling and meetings**:</span></span>

    - <span data-ttu-id="b480e-234">Les scénarios d’appel et de réunion ne sont pas optimisés pour VDI.</span><span class="sxs-lookup"><span data-stu-id="b480e-234">Calling and meeting scenarios aren't optimized for VDI.</span></span> <span data-ttu-id="b480e-235">Ces scénarios d’exécution seront médiocres.</span><span class="sxs-lookup"><span data-stu-id="b480e-235">These scenarios will perform poorly.</span></span> <span data-ttu-id="b480e-236">Nous vous recommandons d’utiliser des stratégies de niveau utilisateur comme décrit dans la section [définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion dans teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .</span><span class="sxs-lookup"><span data-stu-id="b480e-236">We recommend using user-level policies as described in the [Set policies to turn off calling and meeting functionality in Teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) section.</span></span>  
    - <span data-ttu-id="b480e-237">Le recours aux stratégies décrites dans cet article affecte la possibilité d’utiliser les fonctionnalités d’appel et de réunion, qui varient en fonction des autres stratégies, peuvent affecter d’autres utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b480e-237">Applying the policies described in this article impacts the ability to use calling and meeting functionality, which depending on other policies, may affect other users in your organization.</span></span> <span data-ttu-id="b480e-238">Si les utilisateurs de votre organisation utilisent des clients non-VDI, vous pouvez choisir de ne pas appliquer les stratégies.</span><span class="sxs-lookup"><span data-stu-id="b480e-238">If users in your organization use non-VDI clients, you can choose to not apply the policies.</span></span>  

- <span data-ttu-id="b480e-239">**Participation à des appels et des réunions créées par d’autres utilisateurs**: bien que les stratégies restreignent les utilisateurs de la création de réunions, elles peuvent quand même participer à des réunions lorsqu’un autre utilisateur les appelle à partir de la réunion.</span><span class="sxs-lookup"><span data-stu-id="b480e-239">**Joining calls and meetings created by other users**: Although the policies restrict users from creating meetings, they can still join meetings if another user dials out to them from the meeting.</span></span> <span data-ttu-id="b480e-240">Lors de ces réunions, la capacité de l’utilisateur à partager la vidéo, utiliser le tableau blanc et les autres fonctionnalités selon que vous avez désactivé ces fonctionnalités à l’aide de TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="b480e-240">In these meetings, the user's ability to share video, use whiteboard and other features depend on whether you disabled those features using TeamsMeetingPolicy.</span></span>  
- <span data-ttu-id="b480e-241">**Contenu mis en cache**: si l’environnement virtuel dans lequel teams est en cours d’exécution n’est pas permanent (et si les données sont nettoyées à la fin de chaque session utilisateur), les utilisateurs peuvent remarquer une dégradation des performances en raison de l’actualisation du contenu, que l’utilisateur ait accédé ou non. contenu d’une session précédente.</span><span class="sxs-lookup"><span data-stu-id="b480e-241">**Cached content**: If the virtual environment in which Teams is running isn't persistent (and data is cleaned up at the end of each user session), users may notice performance degradation due to content refresh, regardless of whether the user accessed the same content in a previous session.</span></span>
- <span data-ttu-id="b480e-242">**Mises à jour du client**: teams sur l’infrastructure VDI n’est pas automatiquement mis à jour de la même manière que les clients teams non-VDI.</span><span class="sxs-lookup"><span data-stu-id="b480e-242">**Client updates**: Teams on VDI isn't automatically updated like the way that non-VDI Teams clients are.</span></span>  <span data-ttu-id="b480e-243">Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans la section [installer teams sur VDI](#install-teams-on-vdi) .</span><span class="sxs-lookup"><span data-stu-id="b480e-243">You have to update the VM image by installing a new MSI as described in the [Install Teams on VDI](#install-teams-on-vdi) section.</span></span> <span data-ttu-id="b480e-244">Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.</span><span class="sxs-lookup"><span data-stu-id="b480e-244">You must uninstall the current version to update to a newer version.</span></span>
- <span data-ttu-id="b480e-245">\*\*\*\* Environnement d’utilisation: l’environnement d’utilisation des équipes dans un environnement VDI est différent d’un environnement non-VDI.</span><span class="sxs-lookup"><span data-stu-id="b480e-245">**User experience**: The Teams user experience in a VDI environment may be different from a non-VDI environment.</span></span> <span data-ttu-id="b480e-246">Il y a des différences en raison des paramètres de stratégie et de la prise en charge des fonctionnalités dans l’environnement.</span><span class="sxs-lookup"><span data-stu-id="b480e-246">The differences may be because of policy settings and/or feature support in the environment.</span></span>

<span data-ttu-id="b480e-247">Pour les problèmes connus qui ne sont pas liés à VDI, voir [problèmes connus de Microsoft teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b480e-247">For Teams known issues that aren't related to VDI, see [Known issues for Microsoft Teams](Known-issues.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b480e-248">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b480e-248">Related topics</span></span>

- [<span data-ttu-id="b480e-249">Installation de Microsoft teams à l’aide de MSI</span><span class="sxs-lookup"><span data-stu-id="b480e-249">Install Microsoft Teams using MSI</span></span>](msi-deployment.md)
