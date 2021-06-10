---
title: Gérer les stratégies de réunion pour le partage de contenu
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.contentsharing
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams partage de contenu.
ms.openlocfilehash: 7b318ad0025d6c68b041c65d8fbb78cbfbc87723
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598741"
---
# <a name="meeting-policy-settings---content-sharing"></a><span data-ttu-id="ce361-103">Paramètres de stratégie de réunion : partage de contenu</span><span class="sxs-lookup"><span data-stu-id="ce361-103">Meeting policy settings - Content sharing</span></span>

<span data-ttu-id="ce361-104"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="ce361-104"><a name="bkcontentsharing"> </a></span></span>

<span data-ttu-id="ce361-105">Cet article décrit les paramètres de stratégie de réunion suivants concernant le partage de contenu :</span><span class="sxs-lookup"><span data-stu-id="ce361-105">This article describes the following meeting policy settings related to content sharing:</span></span>

- [<span data-ttu-id="ce361-106">Mode de partage d’écran</span><span class="sxs-lookup"><span data-stu-id="ce361-106">Screen sharing mode</span></span>](#screen-sharing-mode)
- <span data-ttu-id="ce361-107">[Autoriser un participant à donner ou demander le contrôle](#allow-a-participant-to-give-or-request-control).</span><span class="sxs-lookup"><span data-stu-id="ce361-107">[Allow a participant to give or request control](#allow-a-participant-to-give-or-request-control)</span></span>
- [<span data-ttu-id="ce361-108">Autoriser un participant externe à donner ou demander le contrôle</span><span class="sxs-lookup"><span data-stu-id="ce361-108">Allow an external participant to give or request control</span></span>](#allow-an-external-participant-to-give-or-request-control)
- [<span data-ttu-id="ce361-109">Autoriser le partage de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ce361-109">Allow PowerPoint sharing</span></span>](#allow-powerpoint-sharing)
- [<span data-ttu-id="ce361-110">Autoriser le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="ce361-110">Allow whiteboard</span></span>](#allow-whiteboard)
- [<span data-ttu-id="ce361-111">Autoriser les notes partagées</span><span class="sxs-lookup"><span data-stu-id="ce361-111">Allow shared notes</span></span>](#allow-shared-notes)

## <a name="screen-sharing-mode"></a><span data-ttu-id="ce361-112">Mode de partage d’écran</span><span class="sxs-lookup"><span data-stu-id="ce361-112">Screen sharing mode</span></span>

<span data-ttu-id="ce361-113">Ce paramètre est une combinaison de stratégies par organisateur et par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-113">This setting is a combination of a per-organizer and per-user policies.</span></span> <span data-ttu-id="ce361-114">Ce paramètre contrôle si le partage du Bureau et des fenêtres est autorisé dans la réunion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-114">This setting controls whether desktop and window sharing is allowed in the user's meeting.</span></span> <span data-ttu-id="ce361-115">Les participants à la réunion qui n'ont pas de stratégie attribuée (par exemple, les participants anonymes, invités, B2B et fédérés) héritent de la stratégie de l'organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-115">Meeting participants who don't have any policies assigned (for example, anonymous, guest, B2B, and federated participants) inherit the policy of the meeting organizer.</span></span>

|<span data-ttu-id="ce361-116">Valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="ce361-116">Setting value</span></span> |<span data-ttu-id="ce361-117">Comportement</span><span class="sxs-lookup"><span data-stu-id="ce361-117">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="ce361-118">**Écran entier**</span><span class="sxs-lookup"><span data-stu-id="ce361-118">**Entire screen**</span></span>    | <span data-ttu-id="ce361-119">Le partage de bureau et le partage d’applications complets sont autorisés pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-119">Full desktop sharing and application sharing are allowed in the meeting</span></span> |
|<span data-ttu-id="ce361-120">**Application unique**</span><span class="sxs-lookup"><span data-stu-id="ce361-120">**Single application**</span></span>   | <span data-ttu-id="ce361-121">Le partage d’applications est autorisé pendant la réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-121">Application sharing is allowed in the meeting</span></span>        |
|<span data-ttu-id="ce361-122">**Désactivé**</span><span class="sxs-lookup"><span data-stu-id="ce361-122">**Disabled**</span></span>     |<span data-ttu-id="ce361-123">Partage d’écran et partage d’applications désactivé pendant la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-123">Screen sharing and application sharing turned off in the meeting.</span></span>       |

<span data-ttu-id="ce361-124">Examinons l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ce361-124">Let's look at the following example.</span></span>

|<span data-ttu-id="ce361-125">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce361-125">User</span></span> |<span data-ttu-id="ce361-126">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-126">Meeting policy</span></span> |<span data-ttu-id="ce361-127">Mode de partage d’écran</span><span class="sxs-lookup"><span data-stu-id="ce361-127">Screen sharing mode</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ce361-128">Daniela</span><span class="sxs-lookup"><span data-stu-id="ce361-128">Daniela</span></span>  | <span data-ttu-id="ce361-129">Global</span><span class="sxs-lookup"><span data-stu-id="ce361-129">Global</span></span>   | <span data-ttu-id="ce361-130">Écran entier</span><span class="sxs-lookup"><span data-stu-id="ce361-130">Entire screen</span></span> |
|<span data-ttu-id="ce361-131">Geneviève</span><span class="sxs-lookup"><span data-stu-id="ce361-131">Amanda</span></span>   | <span data-ttu-id="ce361-132">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="ce361-132">Location1MeetingPolicy</span></span>  | <span data-ttu-id="ce361-133">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ce361-133">Disabled</span></span> |

<span data-ttu-id="ce361-134">Réunions hébergées par Daniela permettre aux participants d’une réunion de partager l’ensemble de l’écran ou d’une application spécifique.</span><span class="sxs-lookup"><span data-stu-id="ce361-134">Meetings hosted by Daniela allow meeting participants to share their entire screen or a specific application.</span></span> <span data-ttu-id="ce361-135">Si Amanda rejoint la réunion de Daniela, elle ne pourra pas partager son écran ou une application spécifique car son paramètre de stratégie est désactivé.</span><span class="sxs-lookup"><span data-stu-id="ce361-135">If Amanda joins Daniela's meeting, Amanda can't share her screen or a specific application as her policy setting is disabled.</span></span> <span data-ttu-id="ce361-136">Les réunions hébergées par Amanda ne sont pas autorisées à partager leur écran ou une seule application, quelle que soit la stratégie de mode de partage d’écran qui leur est attribuée.</span><span class="sxs-lookup"><span data-stu-id="ce361-136">In meetings hosted by Amanda, no one is allowed to share their screen or a single application, regardless of the screen sharing mode policy assigned to them.</span></span>  <span data-ttu-id="ce361-137">Par conséquent, Daniela ne peut pas partager son écran ou une seule application dans les réunions deSyz.</span><span class="sxs-lookup"><span data-stu-id="ce361-137">Consequently, Daniela can't share her screen or a single application in Amanda's meetings.</span></span>  

<span data-ttu-id="ce361-138">Pour l’instant, les utilisateurs ne peuvent pas lire de vidéo ou partager leur écran dans une réunion Teams s’ils utilisent Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="ce361-138">Currently, users can't play video or share their screen in a Teams meeting if they're using Google Chrome.</span></span>

## <a name="allow-a-participant-to-give-or-request-control"></a><span data-ttu-id="ce361-139">Autoriser un participant à donner ou demander le contrôle</span><span class="sxs-lookup"><span data-stu-id="ce361-139">Allow a participant to give or request control</span></span>

<span data-ttu-id="ce361-140">Ce paramètre est une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-140">This setting is a per-user policy.</span></span> <span data-ttu-id="ce361-141">Ce paramètre détermine si l’utilisateur peut donner le contrôle de la fenêtre ou du Bureau partagé aux autres participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-141">This setting controls whether the user can give control of the shared desktop or window to other meeting participants.</span></span> <span data-ttu-id="ce361-142">Pour donner le contrôle, pointez sur la partie supérieure de l’écran.</span><span class="sxs-lookup"><span data-stu-id="ce361-142">To give control, hover over the top of the screen.</span></span>

<span data-ttu-id="ce361-143">Si ce paramètre est activé pour l’utilisateur, l’option **Attribuer un contrôle** s’affiche dans la barre supérieure d’une session de partage.</span><span class="sxs-lookup"><span data-stu-id="ce361-143">If this setting is turned on for the user, the **Give Control** option is displayed in the top bar in a sharing session.</span></span>

![Capture d’écran montrant l’option donner le contrôle](media/meeting-policies-give-control.png)

<span data-ttu-id="ce361-145">Si le paramètre est désactivé pour l’utilisateur, l’option **Donner le contrôle** n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ce361-145">If the setting is turned off for the user, the **Give Control** option isn't available.</span></span>

![Capture d’écran montrant que l’option attribuer le contrôle n’est pas disponible](media/meeting-policies-give-control-not-available.png)

<span data-ttu-id="ce361-147">Examinons l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ce361-147">Let's look at the following example.</span></span>

|<span data-ttu-id="ce361-148">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce361-148">User</span></span> |<span data-ttu-id="ce361-149">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-149">Meeting policy</span></span>  |<span data-ttu-id="ce361-150">Autoriser un participant à donner ou demander le contrôle</span><span class="sxs-lookup"><span data-stu-id="ce361-150">Allow participant to give or request control</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ce361-151">Daniela</span><span class="sxs-lookup"><span data-stu-id="ce361-151">Daniela</span></span>   | <span data-ttu-id="ce361-152">Global</span><span class="sxs-lookup"><span data-stu-id="ce361-152">Global</span></span>   | <span data-ttu-id="ce361-153">Activé</span><span class="sxs-lookup"><span data-stu-id="ce361-153">On</span></span>       |
|<span data-ttu-id="ce361-154">Babek</span><span class="sxs-lookup"><span data-stu-id="ce361-154">Babek</span></span>    | <span data-ttu-id="ce361-155">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="ce361-155">Location1MeetingPolicy</span></span>        | <span data-ttu-id="ce361-156">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ce361-156">Off</span></span>   |

<span data-ttu-id="ce361-157">Daniela peut donner le contrôle du Bureau ou de la fenêtre partagé(e) aux autres participants d’une réunion organisée par Danielk.</span><span class="sxs-lookup"><span data-stu-id="ce361-157">Daniela can give control of the shared desktop or window to other participants in a meeting organized by Babek.</span></span> <span data-ttu-id="ce361-158">Toutefois, il ne peut pas donner le contrôle aux autres participants.</span><span class="sxs-lookup"><span data-stu-id="ce361-158">However, Babek can't give control to other participants.</span></span>

<span data-ttu-id="ce361-159">Pour utiliser PowerShell afin de contrôler qui peut donner le contrôle ou accepter les demandes de contrôle, utilisez l’applet de commande AllowParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="ce361-159">To use PowerShell to control who can give control or accept requests for control, use the AllowParticipantGiveRequestControl cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ce361-160">Pour donner et prendre le contrôle du contenu partagé pendant le partage, les deux personnes doivent utiliser le client de bureau Teams.</span><span class="sxs-lookup"><span data-stu-id="ce361-160">To give and take control of shared content during sharing, both parties must be using the Teams desktop client.</span></span> <span data-ttu-id="ce361-161">Le contrôle n’est pas pris en charge lorsqu'une des parties exécute Teams dans un navigateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-161">Control isn't supported when either party is running Teams in a browser.</span></span> <span data-ttu-id="ce361-162">Il s'agit d'une limitation technique que nous nous efforçons de résoudre.</span><span class="sxs-lookup"><span data-stu-id="ce361-162">This is due to a technical limitation that we're planning to fix.</span></span>

## <a name="allow-an-external-participant-to-give-or-request-control"></a><span data-ttu-id="ce361-163">Autoriser un participant externe à donner ou demander le contrôle</span><span class="sxs-lookup"><span data-stu-id="ce361-163">Allow an external participant to give or request control</span></span>

<span data-ttu-id="ce361-164">Ce paramètre est une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-164">This setting is a per-user policy.</span></span> <span data-ttu-id="ce361-165">Qu’une organisation ait définie cette stratégie pour un utilisateur ne contrôle pas ce que les participants externes peuvent faire, quelle que soit la stratégie définie par l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-165">Whether an organization has set this policy for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="ce361-166">Ce paramètre détermine si les participants externes peuvent bénéficier d’un contrôle ou demander le contrôle de l’écran du destinataire, en fonction de ce que le partage a défini dans les stratégies de réunion de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="ce361-166">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span> <span data-ttu-id="ce361-167">Les participants externes aux réunions Teams peuvent être classés comme suit :</span><span class="sxs-lookup"><span data-stu-id="ce361-167">External participants in Teams meetings can be categorized as follows:</span></span>  

- <span data-ttu-id="ce361-168">Utilisateur anonyme</span><span class="sxs-lookup"><span data-stu-id="ce361-168">Anonymous user</span></span>
- <span data-ttu-id="ce361-169">Utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="ce361-169">Guest users</span></span>  
- <span data-ttu-id="ce361-170">Utilisateur B2B</span><span class="sxs-lookup"><span data-stu-id="ce361-170">B2B user</span></span>
- <span data-ttu-id="ce361-171">Utilisateur fédéré</span><span class="sxs-lookup"><span data-stu-id="ce361-171">Federated user</span></span>  

<span data-ttu-id="ce361-172">La possibilité pour les utilisateurs fédérés de donner le contrôle à des utilisateurs externes tandis que le partage est contrôlé par le paramètre **Autoriser à un participant externe d’attribuer ou de demander un contrôle** dans son organisation.</span><span class="sxs-lookup"><span data-stu-id="ce361-172">Whether federated users can give control to external users while sharing is controlled by the **Allow an external participant to give or request control** setting in their organization.</span></span>

<span data-ttu-id="ce361-173">Pour utiliser PowerShell afin de contrôler si les participants externes peuvent transmettre des demandes de contrôle ou d’acceptation, utilisez l’applet de commande AllowExternalParticipantGiveRequestControl.</span><span class="sxs-lookup"><span data-stu-id="ce361-173">To use PowerShell to control whether external participants can give control or accept requests for control, use the AllowExternalParticipantGiveRequestControl cmdlet.</span></span>

### <a name="allow-powerpoint-sharing"></a><span data-ttu-id="ce361-174">Autoriser le partage de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ce361-174">Allow PowerPoint sharing</span></span>

<span data-ttu-id="ce361-175">Il s’agit d’une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-175">This is a per-user policy.</span></span> <span data-ttu-id="ce361-176">Ce paramètre détermine si l’utilisateur peut partager des diapositives PowerPoint dans une réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-176">This setting controls whether the user can share PowerPoint slide decks in a meeting.</span></span> <span data-ttu-id="ce361-177">Les utilisateurs externes, y compris les utilisateurs anonymes, invités et fédérés, héritent de la stratégie de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-177">External users, including anonymous, guest, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="ce361-178">Examinons l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ce361-178">Let's look at the following example.</span></span>

|<span data-ttu-id="ce361-179">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce361-179">User</span></span> |<span data-ttu-id="ce361-180">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-180">Meeting policy</span></span>  |<span data-ttu-id="ce361-181">Autoriser le partage de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ce361-181">Allow PowerPoint sharing</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ce361-182">Daniela</span><span class="sxs-lookup"><span data-stu-id="ce361-182">Daniela</span></span>   | <span data-ttu-id="ce361-183">Global</span><span class="sxs-lookup"><span data-stu-id="ce361-183">Global</span></span>   | <span data-ttu-id="ce361-184">Activé</span><span class="sxs-lookup"><span data-stu-id="ce361-184">On</span></span>       |
|<span data-ttu-id="ce361-185">Geneviève</span><span class="sxs-lookup"><span data-stu-id="ce361-185">Amanda</span></span>   | <span data-ttu-id="ce361-186">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="ce361-186">Location1MeetingPolicy</span></span>        | <span data-ttu-id="ce361-187">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ce361-187">Off</span></span>   |

<span data-ttu-id="ce361-188">Amanda ne peut pas partager les diapositives PowerPoint dans les réunions, même si elle est l’organisatrice de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-188">Amanda can't share PowerPoint slide decks in meetings even if she's the meeting organizer.</span></span> <span data-ttu-id="ce361-189">Daniela peut partager des diapositives PowerPoint, même si la réunion est organisée par Amanda.</span><span class="sxs-lookup"><span data-stu-id="ce361-189">Daniela can share PowerPoint slide decks even if the meeting is organized by Amanda.</span></span> <span data-ttu-id="ce361-190">Amanda peut afficher les diapositives PowerPoint partagées par d’autres personnes pendant la réunion, même si elles ne peuvent pas partager les diapositives PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ce361-190">Amanda can view the PowerPoint slide decks shared by others in the meeting, even though she can't share PowerPoint slide decks.</span></span>

## <a name="allow-whiteboard"></a><span data-ttu-id="ce361-191">Autoriser le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="ce361-191">Allow whiteboard</span></span>

<span data-ttu-id="ce361-192">Ce paramètre est une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-192">This setting is a per-user policy.</span></span> <span data-ttu-id="ce361-193">Ce paramètre détermine si un utilisateur peut partager le tableau blanc pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-193">This setting controls whether a user can share the whiteboard in a meeting.</span></span> <span data-ttu-id="ce361-194">Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-194">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span>

<span data-ttu-id="ce361-195">Examinons l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ce361-195">Let's look at the following example.</span></span>

|<span data-ttu-id="ce361-196">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce361-196">User</span></span> |<span data-ttu-id="ce361-197">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-197">Meeting policy</span></span>  |<span data-ttu-id="ce361-198">Autoriser le tableau blanc</span><span class="sxs-lookup"><span data-stu-id="ce361-198">Allow whiteboard</span></span>|
|---------|---------|---------|
|<span data-ttu-id="ce361-199">Daniela</span><span class="sxs-lookup"><span data-stu-id="ce361-199">Daniela</span></span>   | <span data-ttu-id="ce361-200">Global</span><span class="sxs-lookup"><span data-stu-id="ce361-200">Global</span></span>   | <span data-ttu-id="ce361-201">Activé</span><span class="sxs-lookup"><span data-stu-id="ce361-201">On</span></span>       |
|<span data-ttu-id="ce361-202">Geneviève</span><span class="sxs-lookup"><span data-stu-id="ce361-202">Amanda</span></span>   | <span data-ttu-id="ce361-203">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="ce361-203">Location1MeetingPolicy</span></span>        | <span data-ttu-id="ce361-204">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ce361-204">Off</span></span>   |

<span data-ttu-id="ce361-205">Amanda ne peut pas partager le tableau blanc pendant une réunion, même si elle est l’organisatrice de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-205">Amanda can't share the whiteboard in a meeting even if she's the meeting organizer.</span></span> <span data-ttu-id="ce361-206">Daniela peut partager le tableau blanc même si une réunion est organisée par Amanda.</span><span class="sxs-lookup"><span data-stu-id="ce361-206">Daniela can share the whiteboard even if a meeting is organized by Amanda.</span></span>  

## <a name="allow-shared-notes"></a><span data-ttu-id="ce361-207">Autoriser les notes partagées</span><span class="sxs-lookup"><span data-stu-id="ce361-207">Allow shared notes</span></span>

<span data-ttu-id="ce361-208">Ce paramètre est une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce361-208">This setting is a per-user policy.</span></span> <span data-ttu-id="ce361-209">Ce paramètre détermine si un utilisateur peut créer et partager des notes pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-209">This setting controls whether a user can create and share notes in a meeting.</span></span> <span data-ttu-id="ce361-210">Les utilisateurs externes, y compris les utilisateurs anonymes, B2B et fédérés, héritent de la stratégie de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-210">External users, including anonymous, B2B, and federated users, inherit the policy of the meeting organizer.</span></span> <span data-ttu-id="ce361-211">L’onglet **Notes de réunion** n’est pas pris en charge pour l’instant pour les réunions ayant moins de 20 participants.</span><span class="sxs-lookup"><span data-stu-id="ce361-211">The **Meeting Notes** tab is currently only supported in meetings that have fewer than 20 participants.</span></span>

<span data-ttu-id="ce361-212">Examinons l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="ce361-212">Let's look at the following example.</span></span>

|<span data-ttu-id="ce361-213">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="ce361-213">User</span></span> |<span data-ttu-id="ce361-214">Stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="ce361-214">Meeting policy</span></span>  |<span data-ttu-id="ce361-215">Autoriser les notes partagées</span><span class="sxs-lookup"><span data-stu-id="ce361-215">Allow shared notes</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ce361-216">Daniela</span><span class="sxs-lookup"><span data-stu-id="ce361-216">Daniela</span></span>   | <span data-ttu-id="ce361-217">Global</span><span class="sxs-lookup"><span data-stu-id="ce361-217">Global</span></span>   | <span data-ttu-id="ce361-218">Activé</span><span class="sxs-lookup"><span data-stu-id="ce361-218">On</span></span>       |
|<span data-ttu-id="ce361-219">Geneviève</span><span class="sxs-lookup"><span data-stu-id="ce361-219">Amanda</span></span>   | <span data-ttu-id="ce361-220">Location1MeetingPolicy</span><span class="sxs-lookup"><span data-stu-id="ce361-220">Location1MeetingPolicy</span></span> | <span data-ttu-id="ce361-221">Désactivé</span><span class="sxs-lookup"><span data-stu-id="ce361-221">Off</span></span> |

<span data-ttu-id="ce361-222">Daniela peut prendre des notes dans les réunions d’Amanda et Amanda ne peut pas prendre de notes pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ce361-222">Daniela can take notes in Amanda's meetings and Amanda can't take notes in any meetings.</span></span>




## <a name="related-topics"></a><span data-ttu-id="ce361-223">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ce361-223">Related topics</span></span>

- [<span data-ttu-id="ce361-224">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce361-224">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="ce361-225">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ce361-225">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="ce361-226">Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ce361-226">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
