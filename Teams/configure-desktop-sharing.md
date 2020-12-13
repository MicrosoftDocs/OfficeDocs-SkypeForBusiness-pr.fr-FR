---
title: Configurer le partage du bureau dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment configurer une stratégie de réunion permettant aux utilisateurs de partager leurs bureaux dans des conversations ou réunions Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652470"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="25b53-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25b53-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="25b53-104">Le partage de bureau permet aux utilisateurs d'afficher un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="25b53-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="25b53-105">Les administrateurs peuvent configurer le partage d’écran dans Microsoft Teams pour autoriser les utilisateurs à partager l'ensemble d'un écran, d'une application ou d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="25b53-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="25b53-106">Vous pouvez permettre aux utilisateurs d’attribuer ou de demander le contrôle, d'autoriser le partage PowerPoint, d'ajouter un tableau blanc et d'autoriser les notes partagées.</span><span class="sxs-lookup"><span data-stu-id="25b53-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="25b53-107">Vous pouvez également préciser si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="25b53-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="25b53-108">Les participants externes aux réunions Teams peuvent être classés comme suit :</span><span class="sxs-lookup"><span data-stu-id="25b53-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="25b53-109">Utilisateur anonyme</span><span class="sxs-lookup"><span data-stu-id="25b53-109">Anonymous user</span></span>
- <span data-ttu-id="25b53-110">Utilisateurs invités</span><span class="sxs-lookup"><span data-stu-id="25b53-110">Guest users</span></span>
- <span data-ttu-id="25b53-111">Utilisateur B2B</span><span class="sxs-lookup"><span data-stu-id="25b53-111">B2B user</span></span>
- <span data-ttu-id="25b53-112">Utilisateur fédéré</span><span class="sxs-lookup"><span data-stu-id="25b53-112">Federated user</span></span>

<span data-ttu-id="25b53-113">Pour configurer le partage d’écran, vous créez une stratégie de réunion, puis vous l’attribuez aux utilisateurs que vous souhaitez gérer.</span><span class="sxs-lookup"><span data-stu-id="25b53-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="25b53-114">**Dans le [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="25b53-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="25b53-115">Sélectionnez **Réunions** > **Stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="25b53-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Stratégies de Réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="25b53-117">Sur la page **Stratégies de réunion**, sélectionnez **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="25b53-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![Le message des stratégies de réunion](media/addMeeting.png)

3. <span data-ttu-id="25b53-119">Donnez un titre unique à votre stratégie, puis entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="25b53-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="25b53-120">Sous le **Partage de contenu**, choisissez un **Mode de partage d’écran** dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="25b53-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="25b53-121">**Écran complet** : permet au utilisateurs de partager la totalité de leur bureau.</span><span class="sxs-lookup"><span data-stu-id="25b53-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="25b53-122">**Application Unique** : permet aux utilisateurs de limiter le partage d’écran à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="25b53-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="25b53-123">**Désactivé** : désactive le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="25b53-123">**Disabled** – Turns off screen sharing.</span></span>

    ![Les options du mode Partage](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="25b53-125">Vous ne pouvez pas activer la stratégie d’appel pour que les utilisateurs utilisent le partage d’écran à partir de la conversation.</span><span class="sxs-lookup"><span data-stu-id="25b53-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="25b53-126">Toutefois, leur audio est désactivé jusqu’à ce qu’ils activent le son eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="25b53-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="25b53-127">En outre, l’utilisateur partageant l’écran peut cliquer sur **Ajouter l’audio** pour activer l’audio.</span><span class="sxs-lookup"><span data-stu-id="25b53-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="25b53-128">Si la stratégie d’appel est désactivée, les utilisateurs ne pourront pas ajouter l’audio au partage d’écran à partir de la session de conversation.</span><span class="sxs-lookup"><span data-stu-id="25b53-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="25b53-129">Activer ou désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="25b53-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="25b53-130">**Autoriser un participant à donner ou demander le contrôle** : permet aux membres de l’équipe de donner ou de demander le contrôle du bureau ou de l'application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="25b53-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="25b53-131">**Autoriser un participant externe à donner ou demander le contrôle** – Il s’agit d’une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="25b53-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="25b53-132">Le fait qu’une organisation ait cette définition pour un utilisateur ne contrôle pas ce que les participants externes peuvent effectuer, quel que soit l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="25b53-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="25b53-133">Ce paramètre détermine si les participants externes peuvent bénéficier d’un contrôle ou demander le contrôle de l’écran du destinataire, en fonction de ce que le partage a défini dans les stratégies de réunion de leur organisation.</span><span class="sxs-lookup"><span data-stu-id="25b53-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="25b53-134">**Autoriser le partage de PowerPoint** : permet aux utilisateurs de créer des réunions autorisant le téléchargement et le partage de présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="25b53-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="25b53-135">**Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="25b53-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="25b53-136">**Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="25b53-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="25b53-137">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="25b53-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="25b53-138">Utiliser PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="25b53-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="25b53-139">Vous pouvez également utiliser l’applet de commande [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="25b53-139">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="25b53-140">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="25b53-140">Set the following parameters:</span></span>

- <span data-ttu-id="25b53-141">Description</span><span class="sxs-lookup"><span data-stu-id="25b53-141">Description</span></span>
- <span data-ttu-id="25b53-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="25b53-142">ScreenSharingMode</span></span>
- <span data-ttu-id="25b53-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="25b53-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="25b53-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="25b53-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="25b53-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="25b53-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="25b53-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="25b53-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="25b53-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="25b53-147">AllowWhiteboard</span></span>
- <span data-ttu-id="25b53-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="25b53-148">AllowSharedNotes</span></span>

<span data-ttu-id="25b53-149">[En savoir plus sur l’utilisation de l'applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="25b53-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>
