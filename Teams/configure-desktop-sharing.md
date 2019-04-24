---
title: Configurer le partage du bureau dans Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans les conversations des équipes ou des réunions
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0434804e7d0ec57ff4470fd8e9af23b73f8179f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198390"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="2697c-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2697c-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="2697c-104">Le partage du bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="2697c-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="2697c-105">Les administrateurs peuvent configurer Microsoft Teams pour permettre aux utilisateurs de partager un ensemble de l’écran, une application ou un fichier de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="2697c-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="2697c-106">Vous pouvez permettre aux utilisateurs donner ou demander le contrôle, autoriser le partage de PowerPoint, ajouter un tableau blanc et les notes partagées.</span><span class="sxs-lookup"><span data-stu-id="2697c-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="2697c-107">Vous pouvez également configurer si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="2697c-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="2697c-108">Pour configurer le partage d’écran, vous créez une nouvelle stratégie de réunions et puis attribuez-le aux utilisateurs que vous souhaitez gérer.</span><span class="sxs-lookup"><span data-stu-id="2697c-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="2697c-109">**Dans le centre d’administration Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="2697c-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="2697c-110">Sélectionnez les **réunions** > **stratégies de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="2697c-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Sélectionnez les stratégies de la réunion](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="2697c-112">Dans la page **stratégies de la réunion** , sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="2697c-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Sélectionnez nouvelle stratégie](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="2697c-114">Donnez à votre stratégie un titre unique et entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="2697c-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="2697c-115">Sous **partage de contenu**, choisissez un **mode de partage d’écran** de la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="2697c-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="2697c-116">**Écran entier** – permet aux utilisateurs de partager leur bureau.</span><span class="sxs-lookup"><span data-stu-id="2697c-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="2697c-117">**Application unique** – permet le partage d’écran utilisateurs limite à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="2697c-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="2697c-118">**Désactivé** – comment désactiver le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="2697c-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Choisissez un mode de partage d’écran](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="2697c-120">Activer ou désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2697c-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="2697c-121">**Autoriser un participant à faire ou demander le contrôle** – vous permet de membres de l’équipe faire ou demander le contrôle du bureau du présentateur ou d’application.</span><span class="sxs-lookup"><span data-stu-id="2697c-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="2697c-122">**Autoriser un participant externe à faire ou demander le contrôle** – permet aux invités et des utilisateurs externes (fédérés) ou demander le contrôle du bureau ou d’application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="2697c-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="2697c-123">**Partage PowerPoint autoriser** - permet aux utilisateurs de créer des réunions qui autorisent les présentations PowerPoint à être téléchargé et partagés.</span><span class="sxs-lookup"><span data-stu-id="2697c-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="2697c-124">**Tableau blanc autoriser** – permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="2697c-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="2697c-125">**Autoriser les notes partagées** – permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="2697c-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="2697c-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2697c-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="2697c-127">Utilisation de PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="2697c-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="2697c-128">Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="2697c-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="2697c-129">Définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="2697c-129">Set the following parameters:</span></span>

- <span data-ttu-id="2697c-130">Description</span><span class="sxs-lookup"><span data-stu-id="2697c-130">Description</span></span>
- <span data-ttu-id="2697c-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="2697c-131">ScreenSharingMode</span></span>
- <span data-ttu-id="2697c-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="2697c-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="2697c-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="2697c-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="2697c-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="2697c-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="2697c-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="2697c-135">AllowWhiteboard</span></span>
- <span data-ttu-id="2697c-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="2697c-136">AllowSharedNotes</span></span>

<span data-ttu-id="2697c-137">[En savoir plus sur l’utilisation de l’applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2697c-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

