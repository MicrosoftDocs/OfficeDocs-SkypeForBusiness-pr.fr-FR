---
title: Gérer les stratégies de réunion
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
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams et les utiliser pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par les utilisateurs.
ms.openlocfilehash: d9f403625225711cb21245ca01262d3c0140063f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598730"
---
# <a name="manage-meeting-policies-in-teams"></a><span data-ttu-id="6e689-103">Voir Gérer les stratégies de réunion dans Teams.</span><span class="sxs-lookup"><span data-stu-id="6e689-103">Manage meeting policies in Teams</span></span>

<span data-ttu-id="6e689-104"><a name="bkautomatically-admit-people"> </a></span><span class="sxs-lookup"><span data-stu-id="6e689-104"><a name="bkautomatically-admit-people"> </a></span></span>

<span data-ttu-id="6e689-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span><span class="sxs-lookup"><span data-stu-id="6e689-105"><a name="bkallow-a-participant-to-give-or-request-control"> </a></span></span>

<span data-ttu-id="6e689-106"><a name="bkallow-transcription"> </a></span><span class="sxs-lookup"><span data-stu-id="6e689-106"><a name="bkallow-transcription"> </a></span></span>

<span data-ttu-id="6e689-107">Stratégies de réunion: elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6e689-107">Meeting policies are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> <span data-ttu-id="6e689-108">Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) qui est créée automatiquement ou créer et affecter de stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6e689-108">You can use the global (Org-wide default) policy that's automatically created or create and assign custom policies.</span></span> <span data-ttu-id="6e689-109">Vous pouvez gérer les stratégies de réunion dans le Centre d’administration Microsoft Teams ou à l’aide de [PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6e689-109">You manage meeting policies in the Microsoft Teams admin center or by using [PowerShell](teams-powershell-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e689-110">Pour plus d’informations sur l’utilisation de rôles pour gérer les autorisations des présentateurs et des participants à une réunion, consultez [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span><span class="sxs-lookup"><span data-stu-id="6e689-110">For information about using roles to manage the permissions of meeting presenters and attendees, see [Roles in a Teams meeting](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).</span></span>

<span data-ttu-id="6e689-111">Vous pouvez implémenter des stratégies de plusieurs manières, ce qui affecte l’expérience de réunion pour les utilisateurs avant le début d’une réunion, pendant une réunion ou après une réunion.</span><span class="sxs-lookup"><span data-stu-id="6e689-111">You can implement policies in the following ways, which affect the meeting experience for users before a meeting starts, during a meeting, or after a meeting.</span></span>

|<span data-ttu-id="6e689-112">Type d’implémentation</span><span class="sxs-lookup"><span data-stu-id="6e689-112">Implementation type</span></span>  |<span data-ttu-id="6e689-113">Description</span><span class="sxs-lookup"><span data-stu-id="6e689-113">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6e689-114">Par organisateur</span><span class="sxs-lookup"><span data-stu-id="6e689-114">Per-organizer</span></span>    |<span data-ttu-id="6e689-115">Lorsque vous appliquez une stratégie par organisateur, tous les participants à la réunion héritent de la stratégie de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="6e689-115">When you implement a per-organizer policy, all meeting participants inherit the policy of the organizer.</span></span> <span data-ttu-id="6e689-116">Par exemple, le paramètre **Admettre automatiquement des personnes** est une stratégie par organisateur. Elle permet de contrôler si les utilisateurs rejoignent directement la réunion ou attendent dans la salle d’attente pour les réunions planifiées par l’utilisateur auquel la stratégie est attribuée.</span><span class="sxs-lookup"><span data-stu-id="6e689-116">For example, **Automatically admit people** is a per-organizer policy and controls whether users join the meeting directly or wait in the lobby for meetings scheduled by the user who is assigned the policy.</span></span>          |
|<span data-ttu-id="6e689-117">Par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6e689-117">Per-user</span></span>    |<span data-ttu-id="6e689-118">Lorsque vous appliquez une stratégie par utilisateur, seule la stratégie par utilisateur s’applique pour restreindre certaines fonctionnalités pour l’organisateur et/ou les participants à la réunion.</span><span class="sxs-lookup"><span data-stu-id="6e689-118">When you implement a per-user policy, only the per-user policy applies to restrict certain features for the organizer and/or meeting participants.</span></span> <span data-ttu-id="6e689-119">Par exemple, le paramètre **Autoriser la conférence maintenant dans les canaux** est une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e689-119">For example, **Allow Meet now in channels** is a per-user policy.</span></span>     |
|<span data-ttu-id="6e689-120">Par organisateur et par utilisateur</span><span class="sxs-lookup"><span data-stu-id="6e689-120">Per-organizer and per-user</span></span>     |<span data-ttu-id="6e689-121">Lorsque vous appliquez une combinaison d’une stratégie par organisateur et par utilisateur, certaines fonctionnalités sont limitées aux participants à la réunion en fonction de leur stratégie et celle de l’organisateur.</span><span class="sxs-lookup"><span data-stu-id="6e689-121">When you implement a combination of a per-organizer and per-user policy, certain features are restricted for meeting participants based on their policy and the organizer's policy.</span></span> <span data-ttu-id="6e689-122">Par exemple, le paramètre **Autoriser l’enregistrement dans le Cloud** est une stratégie par organisateur et par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6e689-122">For example, **Allow cloud recording** is a per-organizer and per-user policy.</span></span> <span data-ttu-id="6e689-123">Activez ce paramètre pour autoriser l’organisateur de la réunion et les participants à démarrer et arrêter un enregistrement.</span><span class="sxs-lookup"><span data-stu-id="6e689-123">Turn on this setting to allow the meeting organizer and participants to start and stop a recording.</span></span>

<span data-ttu-id="6e689-124">Vous pouvez modifier les paramètres dans la stratégie globale ou créer et affecter une ou plusieurs stratégies personnalisées.</span><span class="sxs-lookup"><span data-stu-id="6e689-124">You can edit the settings in the global policy or create and assign one or more custom policies.</span></span> <span data-ttu-id="6e689-125">Les utilisateurs recevront automatiquement la stratégie par défaut, sauf si vous créez et leur attribuez une stratégie personnalisée.</span><span class="sxs-lookup"><span data-stu-id="6e689-125">Users will get the global policy unless you create and assign a custom policy.</span></span>

> [!NOTE]
> <span data-ttu-id="6e689-126">Le bouton Détails de la réunion est disponible si un utilisateur dispose des licences d’audioconférence activées, ou si l’utilisateur autorise l’audioconférence, si ce n’est pas le cas, les détails de la réunion ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="6e689-126">Meeting details button will be available if a user has the audio conference licenses enabled or the user is allow for audio conferencing, if not, the meeting details will not be available.</span></span>

## <a name="create-a-custom-meeting-policy"></a><span data-ttu-id="6e689-127">Créer une stratégie de réunion personnalisée</span><span class="sxs-lookup"><span data-stu-id="6e689-127">Create a custom meeting policy</span></span>

1. <span data-ttu-id="6e689-128">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions** > **Stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="6e689-128">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6e689-129">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="6e689-129">Click **Add**.</span></span>
3. <span data-ttu-id="6e689-130">Entrez un nom pour votre stratégie, ainsi qu’une description.</span><span class="sxs-lookup"><span data-stu-id="6e689-130">Enter a name and description for the policy.</span></span> <span data-ttu-id="6e689-131">Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères.</span><span class="sxs-lookup"><span data-stu-id="6e689-131">The name can't contain special characters or be longer than 64 characters.</span></span>
4. <span data-ttu-id="6e689-132">Sélectionnez les paramètres de votre choix.</span><span class="sxs-lookup"><span data-stu-id="6e689-132">Choose the settings that you want.</span></span>
5. <span data-ttu-id="6e689-133">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6e689-133">Click **Save**.</span></span>

<span data-ttu-id="6e689-134">Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion.</span><span class="sxs-lookup"><span data-stu-id="6e689-134">For example, say you have a bunch of users and you want to limit the amount of bandwidth that their meeting would require.</span></span> <span data-ttu-id="6e689-135">Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6e689-135">You would create a new custom policy named "Limited bandwidth" and disable the following settings:</span></span>

<span data-ttu-id="6e689-136">Sous **Audio & vidéo** :</span><span class="sxs-lookup"><span data-stu-id="6e689-136">Under **Audio & video**:</span></span>

- <span data-ttu-id="6e689-137">Désactivez l’option Autoriser l’enregistrement Cloud.</span><span class="sxs-lookup"><span data-stu-id="6e689-137">Turn off Allow cloud recording.</span></span>
- <span data-ttu-id="6e689-138">Désactivez Autoriser la vidéo IP.</span><span class="sxs-lookup"><span data-stu-id="6e689-138">Turn off Allow IP video.</span></span>

<span data-ttu-id="6e689-139">Sous **Partage de contenu** :</span><span class="sxs-lookup"><span data-stu-id="6e689-139">Under **Content sharing**:</span></span>

- <span data-ttu-id="6e689-140">Désactiver le mode de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="6e689-140">Disable screen sharing mode.</span></span>
- <span data-ttu-id="6e689-141">Désactivez  Autoriser le tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="6e689-141">Turn off Allow whiteboard.</span></span>
- <span data-ttu-id="6e689-142">Désactivez Autoriser les notes partagées.</span><span class="sxs-lookup"><span data-stu-id="6e689-142">Turn off Allow shared notes.</span></span>

<span data-ttu-id="6e689-143">Vous pouvez ensuite attribuer la stratégie aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6e689-143">Then assign the policy to the users.</span></span>

## <a name="edit-a-meeting-policy"></a><span data-ttu-id="6e689-144">Modifier une stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="6e689-144">Edit a meeting policy</span></span>

<span data-ttu-id="6e689-145">Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez.</span><span class="sxs-lookup"><span data-stu-id="6e689-145">You can edit the global policy and any custom policies that you create.</span></span>

1. <span data-ttu-id="6e689-146">Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions** > **Stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="6e689-146">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6e689-147">Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="6e689-147">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="6e689-148">À partir de là, apportez les modifications souhaitées.</span><span class="sxs-lookup"><span data-stu-id="6e689-148">From here, make the changes that you want.</span></span>
4. <span data-ttu-id="6e689-149">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="6e689-149">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="6e689-150">Un utilisateur ne peut être affecté qu’à une stratégie de réunion à la fois.</span><span class="sxs-lookup"><span data-stu-id="6e689-150">A user can be assigned only one meeting policy at a time.</span></span>

## <a name="assign-a-meeting-policy-to-users"></a><span data-ttu-id="6e689-151">Affecter une stratégie de réunion aux utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6e689-151">Assign a meeting policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> <span data-ttu-id="6e689-152">Vous ne pouvez pas supprimer une stratégie qui est attribuée à des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6e689-152">You can't delete a policy if users are assigned to it.</span></span> <span data-ttu-id="6e689-153">Vous devez d'abord attribuer une autre stratégie à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.</span><span class="sxs-lookup"><span data-stu-id="6e689-153">You must first assign a different policy to all affected users, and then you can delete the original policy.</span></span>

## <a name="meeting-policy-settings"></a><span data-ttu-id="6e689-154">Paramètres de stratégie de réunion</span><span class="sxs-lookup"><span data-stu-id="6e689-154">Meeting policy settings</span></span>

<span data-ttu-id="6e689-155">Lorsque vous sélectionnez une stratégie existante dans la page **Stratégies de réunion** ou que vous sélectionnez **Ajouter** pour ajouter une nouvelle stratégie, les paramètres suivants peuvent être configurés.</span><span class="sxs-lookup"><span data-stu-id="6e689-155">When you select an existing policy on the **Meeting policies** page or select **Add** to add a new policy, you can configure settings for the following.</span></span>

- [<span data-ttu-id="6e689-156">Général</span><span class="sxs-lookup"><span data-stu-id="6e689-156">General</span></span>](meeting-policies-in-teams-general.md)
- [<span data-ttu-id="6e689-157">Vidéo et audio</span><span class="sxs-lookup"><span data-stu-id="6e689-157">Audio & video</span></span>](meeting-policies-audio-and-video.md)
- [<span data-ttu-id="6e689-158">Partage de contenu</span><span class="sxs-lookup"><span data-stu-id="6e689-158">Content sharing</span></span>](meeting-policies-content-sharing.md)
- [<span data-ttu-id="6e689-159">Participants et invités</span><span class="sxs-lookup"><span data-stu-id="6e689-159">Participants & guests</span></span>](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a><span data-ttu-id="6e689-160">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="6e689-160">Related topics</span></span>

- [<span data-ttu-id="6e689-161">Présentation de Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e689-161">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="6e689-162">Attribuer des stratégies à vos utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6e689-162">Assign policies to your users in Teams</span></span>](assign-policies.md)
- [<span data-ttu-id="6e689-163">Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6e689-163">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>](meeting-policies-restricted-anonymous-access.md)