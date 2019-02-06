---
title: Configurer le partage du bureau dans Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans les conversations des équipes ou des réunions
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcc76f79d288844611e17154359e8c9c3ab4ed23
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754767"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="cba87-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cba87-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="cba87-104">Le partage du bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="cba87-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="cba87-105">Les administrateurs peuvent configurer Microsoft Teams pour permettre aux utilisateurs de partager un ensemble de l’écran, une application ou un fichier de partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="cba87-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="cba87-106">Vous pouvez permettre aux utilisateurs donner ou demander le contrôle, autoriser le partage de PowerPoint, ajouter un tableau blanc et les notes partagées.</span><span class="sxs-lookup"><span data-stu-id="cba87-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="cba87-107">Vous pouvez également configurer si les utilisateurs anonymes ou externes peuvent demander le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="cba87-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="cba87-108">Pour configurer le partage d’écran, vous créez une nouvelle stratégie de réunions et puis attribuez-le aux utilisateurs que vous souhaitez gérer.</span><span class="sxs-lookup"><span data-stu-id="cba87-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="cba87-109">**Dans le centre d’administration Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="cba87-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cba87-110">Sélectionnez les **réunions** > **stratégies de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="cba87-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Sélectionnez les stratégies de la réunion](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="cba87-112">Dans la page **stratégies de la réunion** , sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="cba87-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Sélectionnez nouvelle stratégie](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="cba87-114">Donnez à votre stratégie un titre unique et entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="cba87-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="cba87-115">Sous **partage de contenu**, choisissez un **mode de partage d’écran** de la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="cba87-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="cba87-116">**Écran entier** – permet aux utilisateurs de partager leur bureau.</span><span class="sxs-lookup"><span data-stu-id="cba87-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="cba87-117">**Application unique** – permet le partage d’écran utilisateurs limite à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="cba87-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="cba87-118">**Désactivé** – comment désactiver le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="cba87-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Choisissez un mode de partage d’écran](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="cba87-120">Activer ou désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="cba87-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="cba87-121">**Autoriser un participant à faire ou demander le contrôle** – vous permet de membres de l’équipe faire ou demander le contrôle du bureau du présentateur ou d’application.</span><span class="sxs-lookup"><span data-stu-id="cba87-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="cba87-122">**Autoriser un participant externe à faire ou demander le contrôle** – permet aux invités et des utilisateurs externes (fédérés) ou demander le contrôle du bureau ou d’application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="cba87-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="cba87-123">**Partage PowerPoint autoriser** - permet aux utilisateurs de créer des réunions qui autorisent les présentations PowerPoint à être téléchargé et partagés.</span><span class="sxs-lookup"><span data-stu-id="cba87-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="cba87-124">**Tableau blanc autoriser** – permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="cba87-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="cba87-125">**Autoriser les notes partagées** – permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="cba87-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="cba87-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="cba87-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="cba87-127">Utilisation de PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="cba87-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="cba87-128">Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="cba87-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="cba87-129">Définir les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="cba87-129">Set the following parameters:</span></span>

- <span data-ttu-id="cba87-130">Description</span><span class="sxs-lookup"><span data-stu-id="cba87-130">Description</span></span>
- <span data-ttu-id="cba87-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="cba87-131">ScreenSharingMode</span></span>
- <span data-ttu-id="cba87-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cba87-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="cba87-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="cba87-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="cba87-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="cba87-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="cba87-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="cba87-135">AllowWhiteboard</span></span>
- <span data-ttu-id="cba87-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="cba87-136">AllowSharedNotes</span></span>

<span data-ttu-id="cba87-137">[En savoir plus sur l’utilisation de l’applet de commande csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="cba87-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

