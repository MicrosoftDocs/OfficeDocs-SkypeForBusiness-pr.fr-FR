---
title: Configurer et gérer la modération de canal
author: cichur
ms.author: v-cichur
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
description: Découvrez comment configurer des canaux pour la modération dans Microsoft Teams, y compris comment ajouter des membres de l’équipe comme modérateurs de canaux.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 81e5159cf0e64a4c5b88afea51de528c299daf80
ms.sourcegitcommit: a731226d62d8b23fe73bd7bf61654e16367fbd90
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51948640"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a><span data-ttu-id="6e308-103">Configurer et gérer la modération de canal dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6e308-103">Set up and manage channel moderation in Microsoft Teams</span></span>

<span data-ttu-id="6e308-104">Dans Microsoft Teams, les propriétaires d’équipe peuvent activer la modération pour un canal standard afin de contrôler qui peut commencer de nouvelles publications et y répondre.</span><span class="sxs-lookup"><span data-stu-id="6e308-104">In Microsoft Teams, team owners can turn on moderation for a standard channel to control who can start new posts and reply to posts in that channel.</span></span>

<span data-ttu-id="6e308-105">Les propriétaires d’équipe peuvent également ajouter des membres de l’équipe en tant que modérateurs.</span><span class="sxs-lookup"><span data-stu-id="6e308-105">Team owners can also add team members as moderators.</span></span> <span data-ttu-id="6e308-106">Un propriétaire d’équipe peut ne pas avoir au niveau du canal l’expertise en la matière pour prendre en charge au mieux la modération du canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-106">A team owner might not have the subject matter expertise at the channel level to best support channel moderation.</span></span> <span data-ttu-id="6e308-107">En permettant à des membres spécifiques d’une équipe de modérer un canal, la responsabilité de la gestion du contenu et du contexte au sein d’un canal est partagée entre les propriétaires d’équipe et les modérateurs des canaux.</span><span class="sxs-lookup"><span data-stu-id="6e308-107">By allowing specific team members to moderate a channel, the responsibility of managing content and context within a channel is shared between team owners and channel moderators.</span></span> <span data-ttu-id="6e308-108">Par exemple, un propriétaire d’équipe peut ajouter des propriétaires d’entreprise ou de contenu comme modérateurs, ce qui leur permet de contrôler le partage d’informations dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-108">For example, a team owner can add business owners or content owners as moderators, which lets them control information sharing in that channel.</span></span>

> [!NOTE]
> <span data-ttu-id="6e308-109">La modération de canal est disponible pour les canaux standard.</span><span class="sxs-lookup"><span data-stu-id="6e308-109">Channel moderation is available for standard channels.</span></span> <span data-ttu-id="6e308-110">Elle n’est pas disponible pour le canal Général ou les canaux privés.</span><span class="sxs-lookup"><span data-stu-id="6e308-110">It's not available for the General channel or private channels.</span></span>

## <a name="what-can-a-channel-moderator-do"></a><span data-ttu-id="6e308-111">Que peut faire un modérateur de canal ?</span><span class="sxs-lookup"><span data-stu-id="6e308-111">What can a channel moderator do?</span></span>

<span data-ttu-id="6e308-112">Les modérateurs de canaux peuvent :</span><span class="sxs-lookup"><span data-stu-id="6e308-112">Channel moderators can:</span></span>

- <span data-ttu-id="6e308-113">Commencez de nouvelles publications dans le canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-113">Start new posts in the channel.</span></span> <span data-ttu-id="6e308-114">Lorsque la modération est désactivée pour un canal, seuls les modérateurs peuvent commencer de nouvelles publications dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-114">When moderation is turned on for a channel, only moderators can start new posts in that channel.</span></span>
- <span data-ttu-id="6e308-115">Ajoutez et supprimez des membres de l’équipe en tant que modérateurs d’un canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-115">Add and remove team members as moderators to a channel.</span></span> <span data-ttu-id="6e308-116">Gardez à l’esprit que, par défaut, les propriétaires d’équipe sont des modérateurs de canaux et ne peuvent pas être supprimés.</span><span class="sxs-lookup"><span data-stu-id="6e308-116">Keep in mind that by default, team owners are channel moderators and can't be removed.</span></span>
- <span data-ttu-id="6e308-117">Contrôler si les membres de l’équipe peuvent répondre aux messages de canal existants et si les bots et connecteurs peuvent envoyer des messages de canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-117">Control whether team members can reply to existing channel messages and whether bots and connectors can submit channel messages.</span></span>

## <a name="scenarios"></a><span data-ttu-id="6e308-118">Scénarios</span><span class="sxs-lookup"><span data-stu-id="6e308-118">Scenarios</span></span>

<span data-ttu-id="6e308-119">Voici quelques exemples de la façon dont votre organisation peut utiliser la modération de canal Teams.</span><span class="sxs-lookup"><span data-stu-id="6e308-119">Here's some examples of how your organization can use channel moderation in Teams.</span></span>

### <a name="use-a-channel-as-an-announcement-channel"></a><span data-ttu-id="6e308-120">Utiliser un canal comme canal d’annonce</span><span class="sxs-lookup"><span data-stu-id="6e308-120">Use a channel as an announcement channel</span></span>

<span data-ttu-id="6e308-121">L’équipe marketing utilise un canal spécifique pour partager les annonces et livrables clés du projet.</span><span class="sxs-lookup"><span data-stu-id="6e308-121">The Marketing team uses a specific channel to share key project announcements and deliverables.</span></span> <span data-ttu-id="6e308-122">Parfois, les membres de l’équipe publient du contenu sur le canal appartenant le mieux à d’autres canaux.</span><span class="sxs-lookup"><span data-stu-id="6e308-122">Sometimes team members post content to the channel that more appropriately belongs in other channels.</span></span> <span data-ttu-id="6e308-123">Le propriétaire de l’équipe souhaite limiter le partage d’informations dans le canal aux annonces uniquement afin que les membres de l’équipe peuvent utiliser ce canal pour rester au fait de ce qui est important.</span><span class="sxs-lookup"><span data-stu-id="6e308-123">The team owner wants to restrict information sharing in the channel to only announcements so that team members can use that channel to stay on top of what's important.</span></span>

<span data-ttu-id="6e308-124">Dans ce scénario, le propriétaire de l’équipe ajoute des prospects marketing en tant que modérateurs afin qu’ils peuvent publier des annonces dans le canal et les membres de l’équipe ne peuvent plus répondre aux messages dans ce canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-124">In this scenario, the team owner adds Marketing leads as moderators so they can post announcements in the channel and turns off the ability for team members to reply to messages in that channel.</span></span>

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a><span data-ttu-id="6e308-125">Utiliser un canal pour les discussions de classe Teams pour l’éducation</span><span class="sxs-lookup"><span data-stu-id="6e308-125">Use a channel for class discussions in Teams for Education</span></span>

<span data-ttu-id="6e308-126">Dans Teams Éducation, un enseignant de science souhaite utiliser un canal pour impliquer les étudiants dans des discussions axées sur des sujets de classe spécifiques.</span><span class="sxs-lookup"><span data-stu-id="6e308-126">In Teams for Education, a science teacher wants to use a channel to engage students in focused discussions on specific classroom topics.</span></span>

<span data-ttu-id="6e308-127">Dans ce scénario, l’enseignant autorise ses assistants d’enseignement à modérer le canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-127">In this scenario, the teacher allows their teaching assistants to moderate the channel.</span></span> <span data-ttu-id="6e308-128">Les assistants enseignants peuvent ensuite créer des billets pour lancer et conduire des discussions avec les étudiants.</span><span class="sxs-lookup"><span data-stu-id="6e308-128">The teaching assistants can then create new posts to initiate and drive discussions with students.</span></span>

## <a name="manage-channel-moderation"></a><span data-ttu-id="6e308-129">Gérer la modération de canal</span><span class="sxs-lookup"><span data-stu-id="6e308-129">Manage channel moderation</span></span>

<span data-ttu-id="6e308-130">Dans Teams, sur le canal, cliquez sur **Autres options...**  >  **Gérer le canal.**</span><span class="sxs-lookup"><span data-stu-id="6e308-130">In Teams, go to the channel, click **More options ...** > **Manage channel**.</span></span> <span data-ttu-id="6e308-131">À partir de là, vous pouvez activer et désactiver la modération, ajouter des membres de l’équipe comme modérateurs et définir des préférences.</span><span class="sxs-lookup"><span data-stu-id="6e308-131">From here you can turn on and turn off moderation, add team members as moderators, and set preferences.</span></span>

<span data-ttu-id="6e308-132">La modération de canal est un paramètre par canal.</span><span class="sxs-lookup"><span data-stu-id="6e308-132">Channel moderation is a per-channel setting.</span></span> <span data-ttu-id="6e308-133">Il n’existe aucun paramètre de modération au niveau du client.</span><span class="sxs-lookup"><span data-stu-id="6e308-133">There's no tenant-level setting for channel moderation.</span></span> <span data-ttu-id="6e308-134">Si vous souhaitez que nous ajoutons un paramètre de modération de canal au niveau du client, demandez-le [sur Teams UserVoice.](https://microsoftteams.uservoice.com/)</span><span class="sxs-lookup"><span data-stu-id="6e308-134">If you'd like us to add a tenant-level channel moderation setting, request it on [Teams UserVoice](https://microsoftteams.uservoice.com/).</span></span>

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![préférences pour la gestion-canal-modération-dans-équipes](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a><span data-ttu-id="6e308-136">Activer ou désactiver la modération pour un canal</span><span class="sxs-lookup"><span data-stu-id="6e308-136">Turn on or turn off moderation for a channel</span></span>

<span data-ttu-id="6e308-137">Par défaut, la modération est off, ce qui signifie que les paramètres habituels du canal s’appliquent aux propriétaires d’équipe et aux membres d’équipe.</span><span class="sxs-lookup"><span data-stu-id="6e308-137">By default, moderation is off, which means that the usual channel settings apply to team owners and team members.</span></span> <span data-ttu-id="6e308-138">Par exemple, vous pouvez limiter les nouvelles publications aux seuls membres de l’équipe ou autoriser tout le monde, y compris les invités, à commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="6e308-138">For example, you can restrict new posts to only team members or allow everyone, including guests, to start new posts.</span></span>

<span data-ttu-id="6e308-139">Pour activer la modération pour un canal, sous **Modération du** canal, cliquez **sur Activer.**</span><span class="sxs-lookup"><span data-stu-id="6e308-139">To turn on moderation for a channel, under **Channel moderation**, click **On**.</span></span> <span data-ttu-id="6e308-140">Lorsque la modération de canal est en cours, seuls les modérateurs peuvent commencer de nouvelles publications.</span><span class="sxs-lookup"><span data-stu-id="6e308-140">When channel moderation is on, only moderators can start new posts.</span></span> 

### <a name="add-or-remove-channel-moderators"></a><span data-ttu-id="6e308-141">Ajouter ou supprimer des modérateurs de canal</span><span class="sxs-lookup"><span data-stu-id="6e308-141">Add or remove channel moderators</span></span>

<span data-ttu-id="6e308-142">Sous **Qui sont les modérateurs ?** Cliquez sur Gérer, puis ajoutez ou supprimez des membres de l’équipe comme modérateurs. </span><span class="sxs-lookup"><span data-stu-id="6e308-142">Under **Who are the moderators?**, click **Manage**, and then add or remove team members as moderators.</span></span> <span data-ttu-id="6e308-143">Les propriétaires d’équipe et les modérateurs peuvent ajouter et supprimer d’autres modérateurs.</span><span class="sxs-lookup"><span data-stu-id="6e308-143">Team owners and moderators can add and remove other moderators.</span></span>  

### <a name="set-team-member-permissions"></a><span data-ttu-id="6e308-144">Définir les autorisations des membres d’une équipe</span><span class="sxs-lookup"><span data-stu-id="6e308-144">Set team member permissions</span></span>

<span data-ttu-id="6e308-145">Sous **Autorisations des membres de l’équipe,** cochez les cases en regard des activités que vous voulez autoriser.</span><span class="sxs-lookup"><span data-stu-id="6e308-145">Under **Team member permissions**, select the check boxes next to the activities  you want to allow.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6e308-146">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6e308-146">Related topics</span></span>

- [<span data-ttu-id="6e308-147">Présentation des équipes et des canaux dans Teams</span><span class="sxs-lookup"><span data-stu-id="6e308-147">Overview of teams and channels in Teams</span></span>](teams-channels-overview.md)
