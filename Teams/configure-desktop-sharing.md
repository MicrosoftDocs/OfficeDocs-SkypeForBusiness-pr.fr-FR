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
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans des conversations ou des réunions teams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bf213b919ee0bea344807f932e16240587b2b84
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433238"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="051e9-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="051e9-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="051e9-104">Le partage de bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="051e9-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="051e9-105">Les administrateurs peuvent configurer le partage d’écran dans Microsoft teams pour permettre aux utilisateurs de partager tout l’écran, une application ou un fichier.</span><span class="sxs-lookup"><span data-stu-id="051e9-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="051e9-106">Vous pouvez permettre aux utilisateurs de donner ou de demander le contrôle, d’autoriser le partage PowerPoint, d’ajouter un tableau blanc et de permettre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="051e9-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="051e9-107">Vous pouvez également configurer la possibilité pour les utilisateurs anonymes ou externes d’exiger le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="051e9-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="051e9-108">Pour configurer le partage d’écran, vous devez créer une nouvelle stratégie de réunion, puis l’affecter aux utilisateurs que vous voulez gérer.</span><span class="sxs-lookup"><span data-stu-id="051e9-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="051e9-109">**Dans le centre d’administration Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="051e9-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="051e9-110">Sélectionnez \*\*\*\* > **stratégies de réunion**pour les réunions.</span><span class="sxs-lookup"><span data-stu-id="051e9-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Capture d’écran montrant les stratégies de réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="051e9-112">Dans la page stratégies de la **réunion** , sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="051e9-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Capture d’écran montrant le message stratégies de réunion](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="051e9-114">Donnez un titre unique à votre politique et entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="051e9-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="051e9-115">Sous **partage de contenu**, choisissez un **mode de partage d’écran** dans la liste déroulante:</span><span class="sxs-lookup"><span data-stu-id="051e9-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="051e9-116">**Tout l’écran** : permet aux utilisateurs de partager leur bureau entier.</span><span class="sxs-lookup"><span data-stu-id="051e9-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="051e9-117">**Application unique** -permet aux utilisateurs de limiter le partage d’écran à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="051e9-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="051e9-118">**Désactivé** -désactive le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="051e9-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Capture d’écran montrant les options du mode de partage](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="051e9-120">Activer ou désactiver les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="051e9-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="051e9-121">**Permettre à un participant de donner ou demander le contrôle** – permet aux membres de l’équipe de donner ou demander le contrôle de l’application ou du Bureau du présentateur.</span><span class="sxs-lookup"><span data-stu-id="051e9-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="051e9-122">**Autoriser un participant externe à céder ou demander le contrôle** – permet aux invités et aux utilisateurs externes d’octroyer le contrôle du bureau ou de l’application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="051e9-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="051e9-123">**Autoriser le partage PowerPoint** -permet aux utilisateurs de créer des réunions permettant de télécharger et de partager des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="051e9-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="051e9-124">**Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="051e9-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="051e9-125">**Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="051e9-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="051e9-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="051e9-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="051e9-127">Utiliser PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="051e9-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="051e9-128">Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="051e9-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="051e9-129">Définissez les paramètres suivants:</span><span class="sxs-lookup"><span data-stu-id="051e9-129">Set the following parameters:</span></span>

- <span data-ttu-id="051e9-130">Description</span><span class="sxs-lookup"><span data-stu-id="051e9-130">Description</span></span>
- <span data-ttu-id="051e9-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="051e9-131">ScreenSharingMode</span></span>
- <span data-ttu-id="051e9-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="051e9-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="051e9-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="051e9-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="051e9-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="051e9-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="051e9-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="051e9-135">AllowWhiteboard</span></span>
- <span data-ttu-id="051e9-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="051e9-136">AllowSharedNotes</span></span>

<span data-ttu-id="051e9-137">[En savoir plus sur l’utilisation de l’applet de passe csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="051e9-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

