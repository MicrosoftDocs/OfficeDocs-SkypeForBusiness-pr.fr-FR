---
title: Configurer et gérer la modération de canal dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment configurer des canaux de modération dans Microsoft Teams, y compris comment ajouter des membres à une équipe comme modérateurs de canaux.
ms.openlocfilehash: 333f0b43c3d703ddd2746bcae0af760228c9fa6e
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804894"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="58a36-103">Configurer et gérer la modération de canal dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="58a36-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="58a36-104">Dans Microsoft Teams, les propriétaires d’équipe peuvent activer le modération d’un canal pour contrôler qui peut démarrer de nouvelles publications et répondre à des publications dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-104">In Microsoft Teams, team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="58a36-105">Les propriétaires d’équipe peuvent également ajouter des membres à une équipe comme modérateurs.</span><span class="sxs-lookup"><span data-stu-id="58a36-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="58a36-106">Il est possible que le propriétaire d’une équipe ne dispose pas de l’expertise du domaine au niveau du canal pour prendre en charge le modérateur du canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="58a36-107">En permettant aux membres d’équipe spécifiques de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs de canaux.</span><span class="sxs-lookup"><span data-stu-id="58a36-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="58a36-108">Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou des propriétaires de contenu en tant que modérateurs, ce qui leur permet de contrôler le partage d’information dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="58a36-109">Que peut faire un modérateur de canal?</span><span class="sxs-lookup"><span data-stu-id="58a36-109">What can a channel moderator do?</span></span>

<span data-ttu-id="58a36-110">Les modérateurs de canal peuvent:</span><span class="sxs-lookup"><span data-stu-id="58a36-110">Channel moderators can:</span></span>

- <span data-ttu-id="58a36-111">Commencez de nouvelles publications dans le canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-111">Start new posts in the channel.</span></span> <span data-ttu-id="58a36-112">Lorsque modération est activée pour un canal, seuls les modérateurs peuvent commencer de nouvelles publications dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-112">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="58a36-113">Ajoutez et supprimez des membres d’équipe comme modérateurs d’un canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-113">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="58a36-114">Gardez à l’esprit que les propriétaires d’équipe sont les modérateurs de canal et ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="58a36-114">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="58a36-115">Déterminez si les membres d’une équipe peuvent répondre à des messages de canal existants et si les robots et connecteurs peuvent envoyer des messages de canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-115">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="58a36-116">Scénarios</span><span class="sxs-lookup"><span data-stu-id="58a36-116">Scenarios</span></span>

<span data-ttu-id="58a36-117">Voici quelques exemples de la manière dont votre organisation peut utiliser le modération des canaux dans Teams.</span><span class="sxs-lookup"><span data-stu-id="58a36-117">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="58a36-118">Utiliser un canal comme canal d’annonce</span><span class="sxs-lookup"><span data-stu-id="58a36-118">Use a channel as an announcement channel</span></span>

<span data-ttu-id="58a36-119">L’équipe marketing utilise un canal spécifique pour partager les annonces principales du projet et les livrables.</span><span class="sxs-lookup"><span data-stu-id="58a36-119">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="58a36-120">Parfois, les membres d’équipe publient du contenu sur le canal qui est plus approprié dans d’autres canaux.</span><span class="sxs-lookup"><span data-stu-id="58a36-120">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="58a36-121">Le propriétaire de l’équipe veut limiter le partage des informations du canal aux annonces uniquement pour permettre aux membres de l’équipe d’utiliser ce canal pour suivre ce qui est important.</span><span class="sxs-lookup"><span data-stu-id="58a36-121">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="58a36-122">Dans ce scénario, le propriétaire de l’équipe ajoute des leads de marketing comme modérateurs pour qu’ils puissent publier des annonces dans le canal et désactiver la possibilité pour les membres de l’équipe de répondre aux messages dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-122">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="58a36-123">Utiliser un canal pour les discussions de classe dans teams éducation</span><span class="sxs-lookup"><span data-stu-id="58a36-123">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="58a36-124">Dans teams pour l’éducation, un enseignant souhaite utiliser un canal pour engager des discussions ciblées sur des sujets spécifiques de la classe.</span><span class="sxs-lookup"><span data-stu-id="58a36-124">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="58a36-125">Dans ce scénario, l’enseignant permet aux assistants d’enseignement de modérer le canal.</span><span class="sxs-lookup"><span data-stu-id="58a36-125">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="58a36-126">Les assistants d’enseignement peuvent ensuite créer de nouvelles publications pour lancer une discussion avec des étudiants et en créer de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="58a36-126">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="58a36-127">Gérer la modération des canaux</span><span class="sxs-lookup"><span data-stu-id="58a36-127">Manage channel moderation</span></span>

<span data-ttu-id="58a36-128">Dans Microsoft Teams, accédez au canal, cliquez sur **autres options.**  >  **Gérer le canal**.</span><span class="sxs-lookup"><span data-stu-id="58a36-128">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="58a36-129">Vous pouvez activer et désactiver la modération, ajouter des membres à une équipe comme modérateurs et définir des préférences.</span><span class="sxs-lookup"><span data-stu-id="58a36-129">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

![Manage-Channel-Moderation-in-teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="58a36-131">Activer ou désactiver la modération d’un canal</span><span class="sxs-lookup"><span data-stu-id="58a36-131">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="58a36-132">Par défaut, la modération est désactivée et vous pouvez limiter de nouvelles publications uniquement aux membres de l’équipe ou autoriser tout le monde, y compris les invités, à commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="58a36-132">By default, moderation is off and you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="58a36-133">Pour activer le modération d’un canal, sous **modération de canal**, cliquez sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="58a36-133">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="58a36-134">Lorsque le modération de canal est activé, seuls les modérateurs peuvent commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="58a36-134">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="58a36-135">Ajouter ou supprimer des modérateurs de canal</span><span class="sxs-lookup"><span data-stu-id="58a36-135">Add or remove channel moderators</span></span>

<span data-ttu-id="58a36-136">Sous **qui est le modérateur?**, cliquez sur **gérer**, puis ajoutez ou supprimez des membres d’équipe comme modérateurs.</span><span class="sxs-lookup"><span data-stu-id="58a36-136">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="58a36-137">Les propriétaires d’équipe et les modérateurs peuvent ajouter et supprimer d’autres modérateurs.</span><span class="sxs-lookup"><span data-stu-id="58a36-137">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="58a36-138">Définir les autorisations des membres de l’équipe</span><span class="sxs-lookup"><span data-stu-id="58a36-138">Set team member permissions</span></span>

<span data-ttu-id="58a36-139">Sous **autorisations des membres**de l’équipe, activez les cases à cocher en regard des activités que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="58a36-139">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58a36-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58a36-140">Related topics</span></span>

- [<span data-ttu-id="58a36-141">Présentation des équipes et des canaux dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58a36-141">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)