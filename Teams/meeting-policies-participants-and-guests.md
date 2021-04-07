---
title: Gérer les stratégies de réunion pour les participants et les invités
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
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams pour les participants et les invités.
ms.openlocfilehash: 51d121ab9c537e6ba304045e47b6e875cd98afd6
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598722"
---
# <a name="meeting-policy-settings---participants--guests"></a><span data-ttu-id="ba286-103">Paramètres de stratégie de réunion : participants et invités</span><span class="sxs-lookup"><span data-stu-id="ba286-103">Meeting policy settings - Participants & guests</span></span>

<span data-ttu-id="ba286-104"><a name="bkmeetingparticipants"> </a></span><span class="sxs-lookup"><span data-stu-id="ba286-104"><a name="bkmeetingparticipants"> </a></span></span>

<span data-ttu-id="ba286-105">Ces paramètres contrôlent les participants à la réunion qui attendent dans la salle d’attente avant d’être admis à la réunion et le niveau de participation à une réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-105">These settings control which meeting participants wait in the lobby before they are admitted to the meeting and the level of participation they are allowed in a meeting.</span></span>

- [<span data-ttu-id="ba286-106">Autoriser les personnes anonymes à démarrer une réunion</span><span class="sxs-lookup"><span data-stu-id="ba286-106">Let anonymous people start a meeting</span></span>](#let-anonymous-people-start-a-meeting)
- [<span data-ttu-id="ba286-107">Admettre les personnes automatiquement</span><span class="sxs-lookup"><span data-stu-id="ba286-107">Automatically admit people</span></span>](#automatically-admit-people)
- [<span data-ttu-id="ba286-108">Autoriser les utilisateurs entrants à éviter la salle d’attente</span><span class="sxs-lookup"><span data-stu-id="ba286-108">Allow dial-in users to bypass the lobby</span></span>](#allow-dial-in-users-to-bypass-the-lobby)
- [<span data-ttu-id="ba286-109">Activer les légendes dynamiques</span><span class="sxs-lookup"><span data-stu-id="ba286-109">Enable live captions</span></span>](#enable-live-captions)
- [<span data-ttu-id="ba286-110">Autoriser la conversation en réunion</span><span class="sxs-lookup"><span data-stu-id="ba286-110">Allow chat in meetings</span></span>](#allow-chat-in-meetings)

> [!NOTE]
><span data-ttu-id="ba286-111">Les options permettant de participer à une réunion varient en fonction des paramètres de chaque groupe Teams et de la méthode de connexion.</span><span class="sxs-lookup"><span data-stu-id="ba286-111">Options to join a meeting will vary, depending on the settings for each Teams group, and the connection method.</span></span> <span data-ttu-id="ba286-112">Si votre groupe dispose d’une audioconférence et l’utilise pour se connecter, consultez[Audioconférence](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ba286-112">If your group has audio conferencing, and uses it to connect, see [Audio Conferencing](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365).</span></span> <span data-ttu-id="ba286-113">Si votre équipe n’a pas d’audioconférence, consultez [Participer à une réunion dans Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span><span class="sxs-lookup"><span data-stu-id="ba286-113">If your Teams group doesn't have audio conferencing, refer to [Join a meeting in Teams](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9).</span></span>

## <a name="let-anonymous-people-start-a-meeting"></a><span data-ttu-id="ba286-114">Autoriser les personnes anonymes à démarrer une réunion</span><span class="sxs-lookup"><span data-stu-id="ba286-114">Let anonymous people start a meeting</span></span>

<span data-ttu-id="ba286-115">Ce paramètre est une stratégie par organisateur qui autorise les réunions de conférence rendez-vous sans leader.</span><span class="sxs-lookup"><span data-stu-id="ba286-115">This setting is a per-organizer policy that allows for leaderless dial-in conferencing meetings.</span></span> <span data-ttu-id="ba286-116">Ce paramètre détermine si les utilisateurs des appels entrants peuvent rejoindre la réunion sans utilisateur authentifié de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="ba286-116">This setting controls whether dial-in users can join the meeting without an authenticated user from the organization in attendance.</span></span> <span data-ttu-id="ba286-117">Par défaut, ce paramètre est désactivé, ce qui signifie que les utilisateurs rendez-vous attendront dans la salle d’attente jusqu’à ce qu’un utilisateur authentifié de l’organisation rejoigne la réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-117">By default, this setting is turned off, which means dial-in users will wait in the lobby until an authenticated user from the organization joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="ba286-118">Si ce paramètre est désactivé et qu’un utilisateur de participation a rejoint la réunion pour la première fois et est placé dans la salle d’attente, l’utilisateur d’une organisation doit participer à la réunion avec un client Teams pour admettre l’utilisateur de la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-118">If this setting is turned off and a dial-in user joins the meeting first and is placed in the lobby, an organization user must join the meeting with a Teams client to admit the user from the lobby.</span></span> <span data-ttu-id="ba286-119">Il n’y a pas de contrôle de salle d’attente disponible pour les utilisateurs entrants.</span><span class="sxs-lookup"><span data-stu-id="ba286-119">There are no lobby controls available for dialed in users.</span></span>

## <a name="automatically-admit-people"></a><span data-ttu-id="ba286-120">Admettre les personnes automatiquement</span><span class="sxs-lookup"><span data-stu-id="ba286-120">Automatically admit people</span></span>

<span data-ttu-id="ba286-121">Il s’agit d’une stratégie par organisateur.</span><span class="sxs-lookup"><span data-stu-id="ba286-121">This is a per-organizer policy.</span></span> <span data-ttu-id="ba286-122">Ce paramètre contrôle la jointure directe des personnes à une réunion ou l’attente dans la salle d’attente jusqu’à ce qu’elles soient intégrées par un utilisateur authentifié.</span><span class="sxs-lookup"><span data-stu-id="ba286-122">This setting controls whether people join a meeting directly or wait in the lobby until they are admitted by an authenticated user.</span></span> <span data-ttu-id="ba286-123">Ce paramètre ne s’applique pas aux utilisateurs distants.</span><span class="sxs-lookup"><span data-stu-id="ba286-123">This setting does not apply to dial-in users.</span></span>

![Capture d’écran montrant une réunion avec un utilisateur dans la salle d’attente](media/meeting-policies-lobby.png)

 <span data-ttu-id="ba286-125">Les organisateurs de réunion peuvent cliquer sur **Options de réunion** dans l’invitation à la réunion afin de modifier ce paramètre pour chaque réunion qu’ils planifient.</span><span class="sxs-lookup"><span data-stu-id="ba286-125">Meeting organizers can click **Meeting Options** in the meeting invitation to change this setting for each meeting they schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="ba286-126">Dans les options de la réunion, le paramètre est intitulé « Qui peut ignorer la salle d’attente ».</span><span class="sxs-lookup"><span data-stu-id="ba286-126">In the meeting options the setting is labeled "Who can bypass the lobby".</span></span> <span data-ttu-id="ba286-127">Si vous modifiez le paramètre par défaut pour un utilisateur, celui-ci s’applique à toutes les réunions organisées par cet utilisateur et aux réunions antérieures où l’utilisateur n’a pas modifié les options de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-127">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>
  
|<span data-ttu-id="ba286-128">Valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="ba286-128">Setting value</span></span>  |<span data-ttu-id="ba286-129">Comportement de jointure</span><span class="sxs-lookup"><span data-stu-id="ba286-129">Join behavior</span></span> |
|---------|---------|
|<span data-ttu-id="ba286-130">**Tout le monde**</span><span class="sxs-lookup"><span data-stu-id="ba286-130">**Everyone**</span></span>   |<span data-ttu-id="ba286-131">Tous les participants à la réunion joignent directement la réunion sans attendre dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-131">All meeting participants join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="ba286-132">Cela inclut les utilisateurs authentifiés, les utilisateurs externes d’organisations approuvées (fédérées), les invités et les utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="ba286-132">This includes authenticated users, external users from trusted organizations (federated), guests, and anonymous users.</span></span>     |
|<span data-ttu-id="ba286-133">**Tous les membres de votre organisation et les organisations fédérées**</span><span class="sxs-lookup"><span data-stu-id="ba286-133">**Everyone in your organization and federated organizations**</span></span>     |<span data-ttu-id="ba286-134">Les utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités et les utilisateurs des organisations approuvées, peuvent participer directement à la réunion sans attendre dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-134">Authenticated users within the organization, including guest users and the users from trusted organizations, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="ba286-135">Les utilisateurs anonymes attendent dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-135">Anonymous users wait in the lobby.</span></span>   |
|<span data-ttu-id="ba286-136">**Tout le monde dans votre organisation**</span><span class="sxs-lookup"><span data-stu-id="ba286-136">**Everyone in your organization**</span></span>    |<span data-ttu-id="ba286-137">Les utilisateurs authentifiés au sein de l’organisation, y compris les utilisateurs invités, joignent directement la réunion sans attendre dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-137">Authenticated users from within the organization, including guest users, join the meeting directly without waiting in the lobby.</span></span>  <span data-ttu-id="ba286-138">Les utilisateurs des organisations approuvées et des utilisateurs anonymes attendent dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-138">Users from trusted organizations and anonymous users wait in the lobby.</span></span> <span data-ttu-id="ba286-139">Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="ba286-139">This is the default setting.</span></span>           |
|<span data-ttu-id="ba286-140">**Organisateur uniquement**</span><span class="sxs-lookup"><span data-stu-id="ba286-140">**Organizer only**</span></span>    |<span data-ttu-id="ba286-141">Seuls les organisateurs de réunion peuvent rejoindre directement la réunion sans attendre dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-141">Only meeting organizers can join the meeting directly without waiting in the lobby.</span></span> <span data-ttu-id="ba286-142">Toutes les autres personnes, y compris les utilisateurs authentifiés au sein de l’organisation, les utilisateurs invités, les utilisateurs des organisations approuvées et les utilisateurs anonymes, doivent attendre dans la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="ba286-142">Everyone else, including authenticated users within the organization, guest users, users from trusted organizations and anonymous users must wait in the lobby.</span></span>           |

## <a name="allow-dial-in-users-to-bypass-the-lobby"></a><span data-ttu-id="ba286-143">Autoriser les utilisateurs entrants à éviter la salle d’attente</span><span class="sxs-lookup"><span data-stu-id="ba286-143">Allow dial-in users to bypass the lobby</span></span>

<span data-ttu-id="ba286-144">Il s’agit d’une stratégie par organisateur.</span><span class="sxs-lookup"><span data-stu-id="ba286-144">This is a per-organizer policy.</span></span> <span data-ttu-id="ba286-145">Ce paramètre contrôle si les personnes qui utilisent le téléphone rejoignent directement la réunion ou attendent dans la salle d’attente, quel que soit le paramètre **Autoriser les personnes automatiquement**.</span><span class="sxs-lookup"><span data-stu-id="ba286-145">This setting controls whether people who dial in by phone join the meeting directly or wait in the lobby regardless of the **Automatically admit people** setting.</span></span> <span data-ttu-id="ba286-146">Par défaut, ce paramètre est désactivé.</span><span class="sxs-lookup"><span data-stu-id="ba286-146">By default, this setting is turned off.</span></span> <span data-ttu-id="ba286-147">Lorsque ce paramètre est désactivé, les utilisateurs rendez-vous patientent dans la salle d’attente jusqu’à ce qu’un utilisateur de l’organisation rejoigne la réunion avec un client Teams et les admette.</span><span class="sxs-lookup"><span data-stu-id="ba286-147">When this setting is turned off, dial-in users will wait in the lobby until an organization user joins the meeting with a Teams client and admits them.</span></span> <span data-ttu-id="ba286-148">Lorsque ce paramètre est activé, les utilisateurs des appels entrants joignent automatiquement la réunion lorsqu’un utilisateur de l’organisation rejoint la réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-148">When this setting is turned on, dial-in users will automatically join the meeting when an organization user joins the meeting.</span></span>

> [!NOTE]
> <span data-ttu-id="ba286-149">Si un utilisateur connecté rejoint une réunion avant qu'un utilisateur de l'organisation ne la rejoigne, il sera placé dans la salle d'attente jusqu'à ce qu'un utilisateur de l'organisation rejoigne la réunion à l'aide d'un client Teams et l'admette.</span><span class="sxs-lookup"><span data-stu-id="ba286-149">If a dial-in user joins a meeting before an organization user joins the meeting, they will be placed in the lobby until an organization user joins the meeting using a Teams client and admits them.</span></span> <span data-ttu-id="ba286-150">Si vous modifiez le paramètre par défaut pour un utilisateur, celui-ci s’applique à toutes les réunions organisées par cet utilisateur et aux réunions antérieures où l’utilisateur n’a pas modifié les options de la réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-150">If you change the default setting for any user, it will apply to all new meetings organized by that user and any prior meetings where the user didn't modify Meeting options.</span></span>

## <a name="enable-live-captions"></a><span data-ttu-id="ba286-151">Activer les légendes dynamiques</span><span class="sxs-lookup"><span data-stu-id="ba286-151">Enable live captions</span></span>

<span data-ttu-id="ba286-152">Ce paramètre est une stratégie par utilisateur et s’applique pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-152">This setting is a per-user policy and applies during a meeting.</span></span> <span data-ttu-id="ba286-153">Ce paramètre détermine si l’option **Activer les légendes dynamiques** est disponible pour l’utilisateur, afin d’activer et de désactiver les légendes dynamiques dans les réunions qu’elle attend.</span><span class="sxs-lookup"><span data-stu-id="ba286-153">This setting controls whether the **Turn on live captions** option is available for the user to turn on and turn off live captions in meetings that the user attends.</span></span>  

![Capture d’écran montrant l’option Activer les légendes dynamiques](media/meeting-policies-live-captions.png)

|<span data-ttu-id="ba286-155">Valeur du paramètre</span><span class="sxs-lookup"><span data-stu-id="ba286-155">Setting value</span></span> |<span data-ttu-id="ba286-156">Comportement</span><span class="sxs-lookup"><span data-stu-id="ba286-156">Behavior</span></span>  |
|---------|---------|
|<span data-ttu-id="ba286-157">**Désactivé, mais l’utilisateur peut remplacer**</span><span class="sxs-lookup"><span data-stu-id="ba286-157">**Disabled but the user can override**</span></span>     | <span data-ttu-id="ba286-158">Les sous-titres en direct ne sont pas activés automatiquement pour l’utilisateur pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-158">Live captions aren't automatically turned on for the user during a meeting.</span></span> <span data-ttu-id="ba286-159">L’utilisateur voit l’option **Activer les sous-titres en direct** dans le menu débordement (**...**) pour les activer.</span><span class="sxs-lookup"><span data-stu-id="ba286-159">The user sees the **Turn on live captions** option in the overflow (**...**) menu to turn them on.</span></span> <span data-ttu-id="ba286-160">Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="ba286-160">This is the default setting.</span></span> |
|<span data-ttu-id="ba286-161">**Désactivé**</span><span class="sxs-lookup"><span data-stu-id="ba286-161">**Disabled**</span></span>     | <span data-ttu-id="ba286-162">Les légendes dynamiques sont désactivées pour l’utilisateur pendant une réunion.</span><span class="sxs-lookup"><span data-stu-id="ba286-162">Live captions are disabled for the user during a meeting.</span></span> <span data-ttu-id="ba286-163">L’utilisateur n’a pas la possibilité de les activer.</span><span class="sxs-lookup"><span data-stu-id="ba286-163">The user doesn't have the option to turn them on.</span></span>          |

<span data-ttu-id="ba286-164"><a name="bkcontentsharing"> </a></span><span class="sxs-lookup"><span data-stu-id="ba286-164"><a name="bkcontentsharing"> </a></span></span>

## <a name="allow-chat-in-meetings"></a><span data-ttu-id="ba286-165">Autoriser la conversation en réunion</span><span class="sxs-lookup"><span data-stu-id="ba286-165">Allow chat in meetings</span></span>

<span data-ttu-id="ba286-166">Ce paramètre est un paramètre par participant.</span><span class="sxs-lookup"><span data-stu-id="ba286-166">This setting is a per-participant setting.</span></span> <span data-ttu-id="ba286-167">Ce paramètre détermine si la conversation de réunion est autorisée pendant la réunion de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ba286-167">This setting controls whether meeting chat is allowed in the user's meeting.</span></span>

<span data-ttu-id="ba286-168"><a name="bkparticipantsandguests"> </a></span><span class="sxs-lookup"><span data-stu-id="ba286-168"><a name="bkparticipantsandguests"> </a></span></span>






## <a name="related-topics"></a><span data-ttu-id="ba286-169">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="ba286-169">Related topics</span></span>

- [<span data-ttu-id="ba286-170">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba286-170">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="ba286-171">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ba286-171">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="ba286-172">Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ba286-172">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)
