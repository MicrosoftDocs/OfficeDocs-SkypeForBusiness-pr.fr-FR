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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650827"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="2e634-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e634-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="2e634-104">Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2e634-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="2e634-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="2e634-105">Debug logs</span></span>

-   <span data-ttu-id="2e634-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="2e634-106">Media logs</span></span>

-   <span data-ttu-id="2e634-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="2e634-107">Desktop logs</span></span>

<span data-ttu-id="2e634-p101">Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e634-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="2e634-p102">Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="2e634-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="2e634-113">Client</span><span class="sxs-lookup"><span data-stu-id="2e634-113">Client</span></span> |<span data-ttu-id="2e634-114">Debug</span><span class="sxs-lookup"><span data-stu-id="2e634-114">Debug</span></span>|<span data-ttu-id="2e634-115">Bureau</span><span class="sxs-lookup"><span data-stu-id="2e634-115">Desktop</span></span>|<span data-ttu-id="2e634-116">Media</span><span class="sxs-lookup"><span data-stu-id="2e634-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="2e634-117">Web</span><span class="sxs-lookup"><span data-stu-id="2e634-117">Web</span></span>    |<span data-ttu-id="2e634-118">X</span><span class="sxs-lookup"><span data-stu-id="2e634-118">X</span></span>         |-         |-         |
|<span data-ttu-id="2e634-119">Windows</span><span class="sxs-lookup"><span data-stu-id="2e634-119">Windows</span></span>     |<span data-ttu-id="2e634-120">X</span><span class="sxs-lookup"><span data-stu-id="2e634-120">X</span></span>         |<span data-ttu-id="2e634-121">X</span><span class="sxs-lookup"><span data-stu-id="2e634-121">X</span></span>         |<span data-ttu-id="2e634-122">X</span><span class="sxs-lookup"><span data-stu-id="2e634-122">X</span></span>         |
|<span data-ttu-id="2e634-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2e634-123">Mac OSX</span></span>     |<span data-ttu-id="2e634-124">X</span><span class="sxs-lookup"><span data-stu-id="2e634-124">X</span></span>         |<span data-ttu-id="2e634-125">X</span><span class="sxs-lookup"><span data-stu-id="2e634-125">X</span></span>         |<span data-ttu-id="2e634-126">X</span><span class="sxs-lookup"><span data-stu-id="2e634-126">X</span></span>         |
|<span data-ttu-id="2e634-127">Linux</span><span class="sxs-lookup"><span data-stu-id="2e634-127">Linux</span></span>     |<span data-ttu-id="2e634-128">X</span><span class="sxs-lookup"><span data-stu-id="2e634-128">X</span></span>         |<span data-ttu-id="2e634-129">X</span><span class="sxs-lookup"><span data-stu-id="2e634-129">X</span></span>         |<span data-ttu-id="2e634-130">X</span><span class="sxs-lookup"><span data-stu-id="2e634-130">X</span></span>         |
|<span data-ttu-id="2e634-131">iOS</span><span class="sxs-lookup"><span data-stu-id="2e634-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="2e634-132">Android</span><span class="sxs-lookup"><span data-stu-id="2e634-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="2e634-133">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="2e634-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="2e634-134">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="2e634-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="2e634-135">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e634-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="2e634-136">Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients reposant sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="2e634-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="2e634-137">Il s’agit de fichiers texte qui sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="2e634-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="2e634-138">Ils peuvent être lus à l’aide de n’importe quel éditeur de texte. En outre, des journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="2e634-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="2e634-139">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="2e634-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="2e634-140">Connexion</span><span class="sxs-lookup"><span data-stu-id="2e634-140">Login</span></span>

-   <span data-ttu-id="2e634-141">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="2e634-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="2e634-142">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="2e634-142">Call/conversation</span></span>

<span data-ttu-id="2e634-143">Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e634-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="2e634-144">Windows :</span><span class="sxs-lookup"><span data-stu-id="2e634-144">Windows:</span></span>

      <span data-ttu-id="2e634-145">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="2e634-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="2e634-146">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="2e634-146">Mac OSX:</span></span>

      <span data-ttu-id="2e634-147">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="2e634-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="2e634-148">\*</span><span class="sxs-lookup"><span data-stu-id="2e634-148">Linux:</span></span>

      <span data-ttu-id="2e634-149">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="2e634-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="2e634-150">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.</span><span class="sxs-lookup"><span data-stu-id="2e634-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="2e634-151">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="2e634-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="2e634-152">Mac OSX : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="2e634-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="2e634-153">Linux : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="2e634-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="2e634-154">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="2e634-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="2e634-155">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="2e634-155">Media logs</span></span>
---------------------------

<span data-ttu-id="2e634-156">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="2e634-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="2e634-157">Ils sont requis pour les cas de support liés aux problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="2e634-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="2e634-158">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2e634-158">Media logging is turned off by default.</span></span> <span data-ttu-id="2e634-159">Pour consigner les données de diagnostic pour les réunions d’équipes, les utilisateurs doivent activer l’option dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="2e634-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="2e634-160">Accédez à **paramètres**  >  **généraux**, activez la case à cocher **activer la journalisation des diagnostics de réunion (nécessite le redémarrage de l’équipe**), puis redémarrez teams et reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="2e634-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="2e634-161">Le tableau suivant présente les emplacements du journal multimédia.</span><span class="sxs-lookup"><span data-stu-id="2e634-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="2e634-162">Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’horodatage des fichiers journaux pour vous assurer que les journaux dépassent la plage de temps pendant laquelle vous avez reproduire le problème.</span><span class="sxs-lookup"><span data-stu-id="2e634-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="2e634-163">Client</span><span class="sxs-lookup"><span data-stu-id="2e634-163">Client</span></span> |<span data-ttu-id="2e634-164">Lieu</span><span class="sxs-lookup"><span data-stu-id="2e634-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="2e634-165">Windows</span><span class="sxs-lookup"><span data-stu-id="2e634-165">Windows</span></span>     |<span data-ttu-id="2e634-166">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="2e634-167">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="2e634-168">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="2e634-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="2e634-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2e634-169">Mac OSX</span></span>     |<span data-ttu-id="2e634-170">~/Library/Application Support/Microsoft/teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="2e634-171">~/Library/Application Support/Microsoft/teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="2e634-172">Linux</span><span class="sxs-lookup"><span data-stu-id="2e634-172">Linux</span></span>       |<span data-ttu-id="2e634-173">~/.config/Microsoft/Microsoft teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="2e634-174">~/.config/Microsoft/Microsoft teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="2e634-175">Vous trouverez ci-dessous la liste des fichiers journaux générés ainsi que les informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="2e634-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="2e634-176">Nom de fichier journal</span><span class="sxs-lookup"><span data-stu-id="2e634-176">Log file name</span></span>  |<span data-ttu-id="2e634-177">Description</span><span class="sxs-lookup"><span data-stu-id="2e634-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2e634-178">Teams. msRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="2e634-179">Contient des informations relatives à la pile multimédia.</span><span class="sxs-lookup"><span data-stu-id="2e634-179">Contains information related to the media stack.</span></span> <span data-ttu-id="2e634-180">Il s’agit de l’état du canal, tel que la résolution, les décodeurs et les encodeurs utilisés, ainsi que le nombre de trames envoyés et reçus, ainsi que l’état de session du partage d’écran vidéo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="2e634-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="2e634-181">rtmcontrol. msRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="2e634-182">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’horodatage lorsque le contrôle est fourni et les informations sur le pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="2e634-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="2e634-183">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="2e634-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="2e634-184">Enregistre les événements de suivi des piles de médias.</span><span class="sxs-lookup"><span data-stu-id="2e634-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="2e634-185">Debug-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="2e634-186">Contient des informations relatives à l’agent de média, y compris la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="2e634-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="2e634-187">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="2e634-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="2e634-188">Enregistre les événements dans l’API d’appel TS.</span><span class="sxs-lookup"><span data-stu-id="2e634-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="2e634-189">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="2e634-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="2e634-p108">Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="2e634-p108">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="2e634-193">Windows :</span><span class="sxs-lookup"><span data-stu-id="2e634-193">Windows:</span></span>

1.  <span data-ttu-id="2e634-194">Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="2e634-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="2e634-195">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="2e634-195">Mac OsX:</span></span>

1.  <span data-ttu-id="2e634-196">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="2e634-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="2e634-197">\*</span><span class="sxs-lookup"><span data-stu-id="2e634-197">Linux:</span></span>

1.  <span data-ttu-id="2e634-198">Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="2e634-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="2e634-199">Client</span><span class="sxs-lookup"><span data-stu-id="2e634-199">Client</span></span> |<span data-ttu-id="2e634-200">Lieu</span><span class="sxs-lookup"><span data-stu-id="2e634-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="2e634-201">Windows</span><span class="sxs-lookup"><span data-stu-id="2e634-201">Windows</span></span>     |<span data-ttu-id="2e634-202">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="2e634-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="2e634-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="2e634-203">Mac OSX</span></span>     |<span data-ttu-id="2e634-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="2e634-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="2e634-205">Linux</span><span class="sxs-lookup"><span data-stu-id="2e634-205">Linux</span></span>       |<span data-ttu-id="2e634-206">~/.config/Microsoft/Microsoft équipes/logs.txt</span><span class="sxs-lookup"><span data-stu-id="2e634-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="2e634-207">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e634-207">Related topics</span></span>

[<span data-ttu-id="2e634-208">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="2e634-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
