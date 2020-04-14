---
title: Configurer et gérer la modération de canal
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment configurer des canaux de modération dans Microsoft Teams, y compris comment ajouter des membres à une équipe comme modérateurs de canaux.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6cdf6988afb9afbd91c2bfd19ed516c8e8fdf702
ms.sourcegitcommit: 379bfaf6b0584c1ac93341af605f93ab932a442b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240614"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="b6946-103">Configurer et gérer la modération de canal dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b6946-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="b6946-104">Dans Microsoft Teams, les propriétaires d’équipe peuvent activer le modération d’un canal standard pour contrôler les utilisateurs qui peuvent lancer de nouvelles publications et répondre aux publications dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="b6946-105">Les propriétaires d’équipe peuvent également ajouter des membres à une équipe comme modérateurs.</span><span class="sxs-lookup"><span data-stu-id="b6946-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="b6946-106">Il est possible que le propriétaire d’une équipe ne dispose pas de l’expertise du domaine au niveau du canal pour prendre en charge le modérateur du canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="b6946-107">En permettant aux membres d’équipe spécifiques de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs de canaux.</span><span class="sxs-lookup"><span data-stu-id="b6946-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="b6946-108">Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou des propriétaires de contenu en tant que modérateurs, ce qui leur permet de contrôler le partage d’information dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="b6946-109">Actuellement, le modération de canal est disponible pour les canaux standard.</span><span class="sxs-lookup"><span data-stu-id="b6946-109">Currently, channel moderation is available for standard channels.</span></span> <span data-ttu-id="b6946-110">Il n’est pas disponible pour les canaux privés.</span><span class="sxs-lookup"><span data-stu-id="b6946-110">It's not available for private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="b6946-111">Que peut faire un modérateur de canal ?</span><span class="sxs-lookup"><span data-stu-id="b6946-111">What can a channel moderator do?</span></span>

<span data-ttu-id="b6946-112">Les modérateurs de canal peuvent :</span><span class="sxs-lookup"><span data-stu-id="b6946-112">Channel moderators can:</span></span>

- <span data-ttu-id="b6946-113">Commencez de nouvelles publications dans le canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-113">Start new posts in the channel.</span></span> <span data-ttu-id="b6946-114">Lorsque modération est activée pour un canal, seuls les modérateurs peuvent commencer de nouvelles publications dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="b6946-115">Ajoutez et supprimez des membres d’équipe comme modérateurs d’un canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="b6946-116">Gardez à l’esprit que les propriétaires d’équipe sont les modérateurs de canal et ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="b6946-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="b6946-117">Déterminez si les membres d’une équipe peuvent répondre à des messages de canal existants et si les robots et connecteurs peuvent envoyer des messages de canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b6946-118">Scénarios</span><span class="sxs-lookup"><span data-stu-id="b6946-118">Scenarios</span></span>

<span data-ttu-id="b6946-119">Voici quelques exemples de la manière dont votre organisation peut utiliser le modération des canaux dans Teams.</span><span class="sxs-lookup"><span data-stu-id="b6946-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="b6946-120">Utiliser un canal comme canal d’annonce</span><span class="sxs-lookup"><span data-stu-id="b6946-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="b6946-121">L’équipe marketing utilise un canal spécifique pour partager les annonces principales du projet et les livrables.</span><span class="sxs-lookup"><span data-stu-id="b6946-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="b6946-122">Parfois, les membres d’équipe publient du contenu sur le canal qui est plus approprié dans d’autres canaux.</span><span class="sxs-lookup"><span data-stu-id="b6946-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="b6946-123">Le propriétaire de l’équipe veut limiter le partage des informations du canal aux annonces uniquement pour permettre aux membres de l’équipe d’utiliser ce canal pour suivre ce qui est important.</span><span class="sxs-lookup"><span data-stu-id="b6946-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="b6946-124">Dans ce scénario, le propriétaire de l’équipe ajoute des leads de marketing comme modérateurs pour qu’ils puissent publier des annonces dans le canal et désactiver la possibilité pour les membres de l’équipe de répondre aux messages dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="b6946-125">Utiliser un canal pour les discussions de classe dans teams éducation</span><span class="sxs-lookup"><span data-stu-id="b6946-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="b6946-126">Dans teams pour l’éducation, un enseignant souhaite utiliser un canal pour engager des discussions ciblées sur des sujets spécifiques de la classe.</span><span class="sxs-lookup"><span data-stu-id="b6946-126">In Teams for Education, a science teacher want to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="b6946-127">Dans ce scénario, l’enseignant permet aux assistants d’enseignement de modérer le canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="b6946-128">Les assistants d’enseignement peuvent ensuite créer de nouvelles publications pour lancer une discussion avec des étudiants et en créer de nouveaux.</span><span class="sxs-lookup"><span data-stu-id="b6946-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="b6946-129">Gérer la modération des canaux</span><span class="sxs-lookup"><span data-stu-id="b6946-129">Manage channel moderation</span></span>

<span data-ttu-id="b6946-130">Dans Microsoft Teams, accédez au canal, cliquez sur **autres options.**  >  **Gérer le canal**.</span><span class="sxs-lookup"><span data-stu-id="b6946-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="b6946-131">Vous pouvez activer et désactiver la modération, ajouter des membres à une équipe comme modérateurs et définir des préférences.</span><span class="sxs-lookup"><span data-stu-id="b6946-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="b6946-132">Le modération de canal est un paramètre par canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="b6946-133">Il n’existe aucun paramètre de niveau client pour modération de canal.</span><span class="sxs-lookup"><span data-stu-id="b6946-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="b6946-134">Si vous souhaitez ajouter un paramètre de modération de canal au niveau du client, demandez-le sur les [équipes UserVoice](https://microsoftteams.uservoice.com/).</span><span class="sxs-lookup"><span data-stu-id="b6946-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

![Manage-Channel-Moderation-in-teams-Preferences. png](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="b6946-136">Activer ou désactiver la modération d’un canal</span><span class="sxs-lookup"><span data-stu-id="b6946-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="b6946-137">Par défaut, la modération est désdésactivée, ce qui signifie que les paramètres du canal habituel s’appliquent aux propriétaires d’équipe et aux membres de l’équipe.</span><span class="sxs-lookup"><span data-stu-id="b6946-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="b6946-138">Par exemple, vous pouvez limiter de nouvelles publications uniquement aux membres de l’équipe ou autoriser tout le monde, y compris les invités, à commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="b6946-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="b6946-139">Pour activer le modération d’un canal, sous **modération de canal**, cliquez sur **activé**.</span><span class="sxs-lookup"><span data-stu-id="b6946-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="b6946-140">Lorsque le modération de canal est activé, seuls les modérateurs peuvent commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="b6946-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="b6946-141">Ajouter ou supprimer des modérateurs de canal</span><span class="sxs-lookup"><span data-stu-id="b6946-141">Add or remove channel moderators</span></span>

<span data-ttu-id="b6946-142">Sous **qui est le modérateur ?**, cliquez sur **gérer**, puis ajoutez ou supprimez des membres d’équipe comme modérateurs.</span><span class="sxs-lookup"><span data-stu-id="b6946-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="b6946-143">Les propriétaires d’équipe et les modérateurs peuvent ajouter et supprimer d’autres modérateurs.</span><span class="sxs-lookup"><span data-stu-id="b6946-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="b6946-144">Définir les autorisations des membres de l’équipe</span><span class="sxs-lookup"><span data-stu-id="b6946-144">Set team member permissions</span></span>

<span data-ttu-id="b6946-145">Sous **autorisations des membres**de l’équipe, activez les cases à cocher en regard des activités que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="b6946-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6946-146">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="b6946-146">Related topics</span></span>

- [<span data-ttu-id="b6946-147">Présentation des équipes et des canaux dans Teams</span><span class="sxs-lookup"><span data-stu-id="b6946-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
