---
title: Configurer le partage du bureau dans Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
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
ms.openlocfilehash: 955a642d2a2309ccbaf9f9d6280170a93a9179ae
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905896"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="7e575-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7e575-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="7e575-104">Le partage de bureau permet aux utilisateurs d'afficher un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="7e575-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="7e575-105">Les administrateurs peuvent configurer le partage d’écran dans Microsoft Teams pour autoriser les utilisateurs à partager l'ensemble d'un écran, d'une application ou d'un fichier.</span><span class="sxs-lookup"><span data-stu-id="7e575-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="7e575-106">Vous pouvez permettre aux utilisateurs d’attribuer ou de demander le contrôle, d'autoriser le partage PowerPoint, d'ajouter un tableau blanc et d'autoriser les notes partagées.</span><span class="sxs-lookup"><span data-stu-id="7e575-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="7e575-107">Vous pouvez également préciser si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="7e575-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="7e575-108">Pour configurer le partage d’écran, vous créez une stratégie de réunion, puis vous l’attribuez aux utilisateurs que vous souhaitez gérer.</span><span class="sxs-lookup"><span data-stu-id="7e575-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="7e575-109">**Dans le [Centre d’administration Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="7e575-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="7e575-110">Sélectionnez **Réunions** > **Stratégies de réunion**.</span><span class="sxs-lookup"><span data-stu-id="7e575-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Capture d’écran affichant les stratégies de Réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="7e575-112">Sur la page **Stratégies de réunion**, sélectionnez **Nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="7e575-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Capture d’écran affichant le message des stratégies de Réunion](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="7e575-114">Donnez un titre unique à votre stratégie, puis entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="7e575-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="7e575-115">Sous le **Partage de contenu**, choisissez un **Mode de partage d’écran** dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="7e575-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="7e575-116">**Écran complet** : permet au utilisateurs de partager la totalité de leur bureau.</span><span class="sxs-lookup"><span data-stu-id="7e575-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="7e575-117">**Application Unique** : permet aux utilisateurs de limiter le partage d’écran à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="7e575-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="7e575-118">**Désactivé** : désactive le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="7e575-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Capture d’écran affichant les options de mode de partage](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="7e575-120">Activer ou désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="7e575-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="7e575-121">**Autoriser un participant à donner ou demander le contrôle** : permet aux membres de l’équipe de donner ou de demander le contrôle du bureau ou de l'application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="7e575-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="7e575-122">**Autoriser un participant externe à donner ou demander le contrôle** : permet aux utilisateurs invités ou externes (fédérés) de donner ou de demander le contrôle du bureau ou de l'application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="7e575-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="7e575-123">**Autoriser le partage de PowerPoint** : permet aux utilisateurs de créer des réunions autorisant le téléchargement et le partage de présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7e575-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="7e575-124">**Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="7e575-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="7e575-125">**Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="7e575-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="7e575-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="7e575-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="7e575-127">Utiliser PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="7e575-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="7e575-128">Vous pouvez également utiliser l’applet de commande [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="7e575-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="7e575-129">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="7e575-129">Set the following parameters:</span></span>

- <span data-ttu-id="7e575-130">Description</span><span class="sxs-lookup"><span data-stu-id="7e575-130">Description</span></span>
- <span data-ttu-id="7e575-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="7e575-131">ScreenSharingMode</span></span>
- <span data-ttu-id="7e575-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7e575-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7e575-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7e575-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7e575-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="7e575-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="7e575-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="7e575-135">AllowWhiteboard</span></span>
- <span data-ttu-id="7e575-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="7e575-136">AllowSharedNotes</span></span>

<span data-ttu-id="7e575-137">[En savoir plus sur l’utilisation de l'applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7e575-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

