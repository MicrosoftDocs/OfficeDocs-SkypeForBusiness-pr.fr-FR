---
title: Utiliser des fichiers journaux pour le dépannage de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a14d6db6c03b540a6495b9028a4f0342ff92636
ms.sourcegitcommit: 336a9c95602d58ff069e4990b340e376a2d0d809
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26716334"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="25249-103">Utiliser des fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25249-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="25249-104">Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="25249-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="25249-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="25249-105">Debug logs</span></span>

-   <span data-ttu-id="25249-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="25249-106">Media logs</span></span>

-   <span data-ttu-id="25249-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="25249-107">Desktop logs</span></span>

<span data-ttu-id="25249-p101">Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25249-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="25249-p102">Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="25249-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="25249-113">Client</span><span class="sxs-lookup"><span data-stu-id="25249-113">Client</span></span> |<span data-ttu-id="25249-114">Debogage</span><span class="sxs-lookup"><span data-stu-id="25249-114">Debug</span></span>|<span data-ttu-id="25249-115">Bureau</span><span class="sxs-lookup"><span data-stu-id="25249-115">Desktop</span></span>|<span data-ttu-id="25249-116">Médias</span><span class="sxs-lookup"><span data-stu-id="25249-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="25249-117">Web</span><span class="sxs-lookup"><span data-stu-id="25249-117">Web</span></span>    |<span data-ttu-id="25249-118">X</span><span class="sxs-lookup"><span data-stu-id="25249-118">X</span></span>         |-         |-         |
|<span data-ttu-id="25249-119">Windows</span><span class="sxs-lookup"><span data-stu-id="25249-119">Windows</span></span>     |<span data-ttu-id="25249-120">X</span><span class="sxs-lookup"><span data-stu-id="25249-120">X</span></span>         |<span data-ttu-id="25249-121">X</span><span class="sxs-lookup"><span data-stu-id="25249-121">X</span></span>         |<span data-ttu-id="25249-122">X</span><span class="sxs-lookup"><span data-stu-id="25249-122">X</span></span>         |
|<span data-ttu-id="25249-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="25249-123">Mac OSX</span></span>     |<span data-ttu-id="25249-124">X</span><span class="sxs-lookup"><span data-stu-id="25249-124">X</span></span>         |<span data-ttu-id="25249-125">X</span><span class="sxs-lookup"><span data-stu-id="25249-125">X</span></span>         |<span data-ttu-id="25249-126">X</span><span class="sxs-lookup"><span data-stu-id="25249-126">X</span></span>         |
|<span data-ttu-id="25249-127">iOS</span><span class="sxs-lookup"><span data-stu-id="25249-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="25249-128">Android</span><span class="sxs-lookup"><span data-stu-id="25249-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="25249-129">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="25249-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="25249-130">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="25249-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="25249-131">Ces se trouvent les journaux les plus courants et sont requis pour tous les cas de support technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="25249-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="25249-132">Déboguer les journaux sont générées par les clients de bureau Windows et Mac, ainsi que les clients basé sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="25249-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="25249-133">Les journaux sont texte et en lecture à partir du bas en.</span><span class="sxs-lookup"><span data-stu-id="25249-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="25249-134">Qu’ils peuvent être lus à l’aide de n’importe quel éditeur de texte en fonction et nouveaux journaux sont créés lors de la connexion dans le client.</span><span class="sxs-lookup"><span data-stu-id="25249-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="25249-135">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="25249-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="25249-136">Connexion</span><span class="sxs-lookup"><span data-stu-id="25249-136">Login</span></span>

-   <span data-ttu-id="25249-137">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="25249-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="25249-138">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="25249-138">Call/conversation</span></span>

<span data-ttu-id="25249-139">Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="25249-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="25249-140">Windows :</span><span class="sxs-lookup"><span data-stu-id="25249-140">Windows:</span></span>

    1.  <span data-ttu-id="25249-141">Cliquez avec le bouton droit sur l'**icône de Microsoft Teams dans** la barre d'applications et sélectionnez **Obtenir les journaux**.</span><span class="sxs-lookup"><span data-stu-id="25249-141">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

    2.  <span data-ttu-id="25249-142">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="25249-142">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    3.  <span data-ttu-id="25249-143">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="25249-143">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="25249-144">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="25249-144">Mac OSX:</span></span>

    1.  <span data-ttu-id="25249-145">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="25249-145">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

    2.  <span data-ttu-id="25249-146">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="25249-146">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="25249-147">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.</span><span class="sxs-lookup"><span data-stu-id="25249-147">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="25249-148">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="25249-148">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="25249-149">Mac OSX : Téléchargements</span><span class="sxs-lookup"><span data-stu-id="25249-149">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="25249-150">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="25249-150">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="25249-151">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="25249-151">Media Logs</span></span>
---------------------------

<span data-ttu-id="25249-p104">Les journaux des médias contiennent des données de diagnostic sur les appels audio, vidéo et le partage d'écran. Ils sont requis pour les cas de support uniquement sur demande et seul Microsoft peut les lire. Le tableau suivant présente l'emplacement des journaux.</span><span class="sxs-lookup"><span data-stu-id="25249-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="25249-155">Client</span><span class="sxs-lookup"><span data-stu-id="25249-155">Client</span></span> |<span data-ttu-id="25249-156">Emplacement</span><span class="sxs-lookup"><span data-stu-id="25249-156">Location</span></span> |
|---------|---------|
|<span data-ttu-id="25249-157">Windows</span><span class="sxs-lookup"><span data-stu-id="25249-157">Windows</span></span>     |<span data-ttu-id="25249-158">%AppData%\Microsoft\Teams\media-Stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="25249-158">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="25249-159">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="25249-159">Mac OSX</span></span>     |<span data-ttu-id="25249-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="25249-160">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="25249-161">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="25249-161">Desktop logs</span></span>
---------------------

<span data-ttu-id="25249-p105">Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="25249-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

|<span data-ttu-id="25249-165">Client</span><span class="sxs-lookup"><span data-stu-id="25249-165">Client</span></span> |<span data-ttu-id="25249-166">Emplacement</span><span class="sxs-lookup"><span data-stu-id="25249-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="25249-167">Windows</span><span class="sxs-lookup"><span data-stu-id="25249-167">Windows</span></span>     |<span data-ttu-id="25249-168">%AppData%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="25249-168">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="25249-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="25249-169">Mac OSX</span></span>     |<span data-ttu-id="25249-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="25249-170">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
