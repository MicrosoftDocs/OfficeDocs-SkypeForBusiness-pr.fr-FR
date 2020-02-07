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
description: Configurer une stratégie de réunion pour permettre aux utilisateurs de partager leur bureau dans des conversations ou des réunions teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825542"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="75e3a-103">Configurer le partage du bureau dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75e3a-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="75e3a-104">Le partage de bureau permet aux utilisateurs de présenter un écran ou une application pendant une réunion ou une conversation.</span><span class="sxs-lookup"><span data-stu-id="75e3a-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="75e3a-105">Les administrateurs peuvent configurer le partage d’écran dans Microsoft teams pour permettre aux utilisateurs de partager tout l’écran, une application ou un fichier.</span><span class="sxs-lookup"><span data-stu-id="75e3a-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="75e3a-106">Vous pouvez permettre aux utilisateurs de donner ou de demander le contrôle, d’autoriser le partage PowerPoint, d’ajouter un tableau blanc et de permettre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="75e3a-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="75e3a-107">Vous pouvez également configurer la possibilité pour les utilisateurs anonymes ou externes d’exiger le contrôle de l’écran partagé.</span><span class="sxs-lookup"><span data-stu-id="75e3a-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="75e3a-108">Pour configurer le partage d’écran, vous devez créer une nouvelle stratégie de réunion, puis l’affecter aux utilisateurs que vous voulez gérer.</span><span class="sxs-lookup"><span data-stu-id="75e3a-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="75e3a-109">**Dans le [Centre d’administration Microsoft teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="75e3a-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="75e3a-110">Sélectionnez \*\*\*\* > **stratégies de réunion**pour les réunions.</span><span class="sxs-lookup"><span data-stu-id="75e3a-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Capture d’écran montrant les stratégies de réunion sélectionnées](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="75e3a-112">Dans la page stratégies de la **réunion** , sélectionnez **nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="75e3a-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Capture d’écran montrant le message stratégies de réunion](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="75e3a-114">Donnez un titre unique à votre politique et entrez une brève description.</span><span class="sxs-lookup"><span data-stu-id="75e3a-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="75e3a-115">Sous **partage de contenu**, choisissez un **mode de partage d’écran** dans la liste déroulante :</span><span class="sxs-lookup"><span data-stu-id="75e3a-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="75e3a-116">**Tout l’écran** : permet aux utilisateurs de partager leur bureau entier.</span><span class="sxs-lookup"><span data-stu-id="75e3a-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="75e3a-117">**Application unique** -permet aux utilisateurs de limiter le partage d’écran à une seule application active.</span><span class="sxs-lookup"><span data-stu-id="75e3a-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="75e3a-118">**Désactivé** -désactive le partage d’écran.</span><span class="sxs-lookup"><span data-stu-id="75e3a-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Capture d’écran montrant les options du mode de partage](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="75e3a-120">Activer ou désactiver les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="75e3a-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="75e3a-121">**Permettre à un participant de donner ou demander le contrôle** – permet aux membres de l’équipe de donner ou demander le contrôle de l’application ou du Bureau du présentateur.</span><span class="sxs-lookup"><span data-stu-id="75e3a-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="75e3a-122">**Autoriser un participant externe à céder ou demander le contrôle** – permet aux invités et aux utilisateurs externes d’octroyer le contrôle du bureau ou de l’application du présentateur.</span><span class="sxs-lookup"><span data-stu-id="75e3a-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="75e3a-123">**Autoriser le partage PowerPoint** -permet aux utilisateurs de créer des réunions permettant de télécharger et de partager des présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="75e3a-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="75e3a-124">**Autoriser le tableau blanc** : permet aux utilisateurs de partager un tableau blanc.</span><span class="sxs-lookup"><span data-stu-id="75e3a-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="75e3a-125">**Autoriser les notes partagées** : permet aux utilisateurs de prendre des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="75e3a-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="75e3a-126">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="75e3a-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="75e3a-127">Utiliser PowerShell pour configurer le bureau partagé</span><span class="sxs-lookup"><span data-stu-id="75e3a-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="75e3a-128">Vous pouvez également utiliser l’applet de commande [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) pour contrôler le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="75e3a-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="75e3a-129">Définissez les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="75e3a-129">Set the following parameters:</span></span>

- <span data-ttu-id="75e3a-130">Description</span><span class="sxs-lookup"><span data-stu-id="75e3a-130">Description</span></span>
- <span data-ttu-id="75e3a-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="75e3a-131">ScreenSharingMode</span></span>
- <span data-ttu-id="75e3a-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="75e3a-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="75e3a-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="75e3a-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="75e3a-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="75e3a-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="75e3a-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="75e3a-135">AllowWhiteboard</span></span>
- <span data-ttu-id="75e3a-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="75e3a-136">AllowSharedNotes</span></span>

<span data-ttu-id="75e3a-137">[En savoir plus sur l’utilisation de l’applet de passe csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="75e3a-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

