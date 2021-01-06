---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761092"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="1037e-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1037e-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="1037e-104">Il existe trois types de fichiers journaux créés automatiquement par le client, qui peuvent être utilisés pour aider à résoudre les problèmes liés à Microsoft teams :</span><span class="sxs-lookup"><span data-stu-id="1037e-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="1037e-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="1037e-105">Debug logs</span></span>

-   <span data-ttu-id="1037e-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="1037e-106">Media logs</span></span>

-   <span data-ttu-id="1037e-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="1037e-107">Desktop logs</span></span>

<span data-ttu-id="1037e-p101">Lors de la création d’une demande de support auprès du support technique Microsoft, l’ingénieur du support technique doit avoir les journaux de débogage. Le fait de disposer des journaux de débogage avant de créer une demande de support permet à Microsoft de commencer rapidement à résoudre le problème. Les journaux de **médias** ou de **Bureau** ne sont obligatoires que si vous en êtes invité par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1037e-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. **Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="1037e-111">Dans cet article, le terme **journaux de débogage** fait référence aux journaux utilisés pour la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="1037e-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="1037e-112">Toutefois, les fichiers générés pour ces journaux contiennent le terme journaux de **diagnostic** dans leur nom.</span><span class="sxs-lookup"><span data-stu-id="1037e-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="1037e-113">Le tableau suivant présente les différents clients et leurs journaux associés.</span><span class="sxs-lookup"><span data-stu-id="1037e-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="1037e-114">Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="1037e-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="1037e-115">Client</span><span class="sxs-lookup"><span data-stu-id="1037e-115">Client</span></span> |<span data-ttu-id="1037e-116">Debug</span><span class="sxs-lookup"><span data-stu-id="1037e-116">Debug</span></span>|<span data-ttu-id="1037e-117">Bureau</span><span class="sxs-lookup"><span data-stu-id="1037e-117">Desktop</span></span>|<span data-ttu-id="1037e-118">Media</span><span class="sxs-lookup"><span data-stu-id="1037e-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="1037e-119">Web</span><span class="sxs-lookup"><span data-stu-id="1037e-119">Web</span></span>    |<span data-ttu-id="1037e-120">X</span><span class="sxs-lookup"><span data-stu-id="1037e-120">X</span></span>         |-         |-         |
|<span data-ttu-id="1037e-121">Windows</span><span class="sxs-lookup"><span data-stu-id="1037e-121">Windows</span></span>     |<span data-ttu-id="1037e-122">X</span><span class="sxs-lookup"><span data-stu-id="1037e-122">X</span></span>         |<span data-ttu-id="1037e-123">X</span><span class="sxs-lookup"><span data-stu-id="1037e-123">X</span></span>         |<span data-ttu-id="1037e-124">X</span><span class="sxs-lookup"><span data-stu-id="1037e-124">X</span></span>         |
|<span data-ttu-id="1037e-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1037e-125">Mac OSX</span></span>     |<span data-ttu-id="1037e-126">X</span><span class="sxs-lookup"><span data-stu-id="1037e-126">X</span></span>         |<span data-ttu-id="1037e-127">X</span><span class="sxs-lookup"><span data-stu-id="1037e-127">X</span></span>         |<span data-ttu-id="1037e-128">X</span><span class="sxs-lookup"><span data-stu-id="1037e-128">X</span></span>         |
|<span data-ttu-id="1037e-129">Linux</span><span class="sxs-lookup"><span data-stu-id="1037e-129">Linux</span></span>     |<span data-ttu-id="1037e-130">X</span><span class="sxs-lookup"><span data-stu-id="1037e-130">X</span></span>         |<span data-ttu-id="1037e-131">X</span><span class="sxs-lookup"><span data-stu-id="1037e-131">X</span></span>         |<span data-ttu-id="1037e-132">X</span><span class="sxs-lookup"><span data-stu-id="1037e-132">X</span></span>         |
|<span data-ttu-id="1037e-133">iOS</span><span class="sxs-lookup"><span data-stu-id="1037e-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="1037e-134">Android</span><span class="sxs-lookup"><span data-stu-id="1037e-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="1037e-135">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="1037e-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="1037e-136">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="1037e-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="1037e-137">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1037e-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="1037e-138">Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients basés sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="1037e-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="1037e-139">Les journaux sont basés sur du texte et sont lus du haut vers le bas.</span><span class="sxs-lookup"><span data-stu-id="1037e-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="1037e-140">Ils peuvent être lus à l’aide d’un éditeur de texte et de nouveaux journaux lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="1037e-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="1037e-141">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="1037e-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="1037e-142">Connexion</span><span class="sxs-lookup"><span data-stu-id="1037e-142">Login</span></span>

-   <span data-ttu-id="1037e-143">Demandes de connexion aux services de couche intermédiaire</span><span class="sxs-lookup"><span data-stu-id="1037e-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="1037e-144">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="1037e-144">Call/conversation</span></span>

<span data-ttu-id="1037e-145">Les journaux de débogage sont générés à l’aide des méthodes spécifiques au système d’exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="1037e-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="1037e-146">Windows :</span><span class="sxs-lookup"><span data-stu-id="1037e-146">Windows:</span></span>

      <span data-ttu-id="1037e-147">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="1037e-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="1037e-148">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="1037e-148">Mac OSX:</span></span>

      <span data-ttu-id="1037e-149">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="1037e-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="1037e-150">\*</span><span class="sxs-lookup"><span data-stu-id="1037e-150">Linux:</span></span>

      <span data-ttu-id="1037e-151">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="1037e-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="1037e-152">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="1037e-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="1037e-153">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="1037e-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="1037e-154">Mac OSX : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="1037e-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="1037e-155">Linux : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="1037e-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="1037e-156">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="1037e-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="1037e-157">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="1037e-157">Media logs</span></span>
---------------------------

<span data-ttu-id="1037e-158">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="1037e-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="1037e-159">Ils sont requis pour les cas de support liés aux problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="1037e-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="1037e-160">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="1037e-160">Media logging is turned off by default.</span></span> <span data-ttu-id="1037e-161">Pour consigner les données de diagnostic pour les réunions d’équipes, les utilisateurs doivent activer l’option dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="1037e-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="1037e-162">Accédez à **paramètres**  >  **généraux**, activez la case à cocher **activer la journalisation des diagnostics de réunion (nécessite le redémarrage d’équipes**), redémarrez Teams, puis reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="1037e-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="1037e-163">Le tableau suivant présente les emplacements du journal multimédia.</span><span class="sxs-lookup"><span data-stu-id="1037e-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="1037e-164">Lorsque vous envoyez les fichiers journaux au support Microsoft, veuillez vérifier l’horodatage des fichiers journaux pour vous assurer que les journaux dépassent la période pendant laquelle vous reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="1037e-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="1037e-165">Client</span><span class="sxs-lookup"><span data-stu-id="1037e-165">Client</span></span> |<span data-ttu-id="1037e-166">Lieu</span><span class="sxs-lookup"><span data-stu-id="1037e-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="1037e-167">Windows</span><span class="sxs-lookup"><span data-stu-id="1037e-167">Windows</span></span>     |<span data-ttu-id="1037e-168">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="1037e-169">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="1037e-170">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="1037e-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="1037e-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1037e-171">Mac OSX</span></span>     |<span data-ttu-id="1037e-172">~/Library/Application Support/Microsoft/teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="1037e-173">~/Library/Application Support/Microsoft/teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="1037e-174">Linux</span><span class="sxs-lookup"><span data-stu-id="1037e-174">Linux</span></span>       |<span data-ttu-id="1037e-175">~/.config/Microsoft/Microsoft teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="1037e-176">~/.config/Microsoft/Microsoft teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="1037e-177">Vous trouverez ci-dessous la liste des fichiers journaux générés ainsi que les informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="1037e-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="1037e-178">Nom de fichier journal</span><span class="sxs-lookup"><span data-stu-id="1037e-178">Log file name</span></span>  |<span data-ttu-id="1037e-179">Description</span><span class="sxs-lookup"><span data-stu-id="1037e-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1037e-180">Teams. msRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="1037e-181">Contient des informations relatives à la pile multimédia.</span><span class="sxs-lookup"><span data-stu-id="1037e-181">Contains information related to the media stack.</span></span> <span data-ttu-id="1037e-182">Il s’agit de l’état du canal, tel que la résolution, les décodeurs et les encodeurs utilisés, ainsi que le nombre de trames envoyés et reçus, ainsi que l’état de session du partage d’écran vidéo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="1037e-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="1037e-183">rtmcontrol. msRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="1037e-184">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’horodatage lorsque le contrôle est fourni et les informations sur le pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="1037e-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="1037e-185">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="1037e-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="1037e-186">Enregistre les événements de suivi des piles de médias.</span><span class="sxs-lookup"><span data-stu-id="1037e-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="1037e-187">Debug-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="1037e-188">Contient des informations relatives à l’agent de média, y compris la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="1037e-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="1037e-189">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="1037e-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="1037e-190">Enregistre les événements dans l’API d’appel TS.</span><span class="sxs-lookup"><span data-stu-id="1037e-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="1037e-191">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="1037e-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="1037e-192">Les journaux de bureau, également appelés journaux de programme d’amorçage, contiennent les données de journalisation qui se produisent entre le client de bureau et le navigateur.</span><span class="sxs-lookup"><span data-stu-id="1037e-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="1037e-193">Comme les journaux multimédias, ces journaux sont uniquement nécessaires si Microsoft est demandé.</span><span class="sxs-lookup"><span data-stu-id="1037e-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="1037e-194">Les journaux sont basés sur du texte et peuvent être lus à l’aide d’un éditeur de texte dans un format de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="1037e-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="1037e-195">Windows :</span><span class="sxs-lookup"><span data-stu-id="1037e-195">Windows:</span></span>

 - <span data-ttu-id="1037e-196">Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**.</span><span class="sxs-lookup"><span data-stu-id="1037e-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="1037e-197">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="1037e-197">Mac OsX:</span></span>

 - <span data-ttu-id="1037e-198">Dans le menu déroulant **aide** , sélectionnez **obtenir les journaux** .</span><span class="sxs-lookup"><span data-stu-id="1037e-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="1037e-199">\*</span><span class="sxs-lookup"><span data-stu-id="1037e-199">Linux:</span></span>

 - <span data-ttu-id="1037e-200">Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**.</span><span class="sxs-lookup"><span data-stu-id="1037e-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="1037e-201">Client</span><span class="sxs-lookup"><span data-stu-id="1037e-201">Client</span></span> |<span data-ttu-id="1037e-202">Lieu</span><span class="sxs-lookup"><span data-stu-id="1037e-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="1037e-203">Windows</span><span class="sxs-lookup"><span data-stu-id="1037e-203">Windows</span></span>     |<span data-ttu-id="1037e-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="1037e-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="1037e-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="1037e-205">Mac OSX</span></span>     |<span data-ttu-id="1037e-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="1037e-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="1037e-207">Linux</span><span class="sxs-lookup"><span data-stu-id="1037e-207">Linux</span></span>       |<span data-ttu-id="1037e-208">~/.config/Microsoft/Microsoft équipes/logs.txt</span><span class="sxs-lookup"><span data-stu-id="1037e-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="1037e-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1037e-209">Related topics</span></span>

[<span data-ttu-id="1037e-210">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="1037e-210">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
