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
ms.openlocfilehash: 468f0f67743f7cd0e11ff28e4484f70a71af3b64
ms.sourcegitcommit: 67c686810d37bffda72a6e92155d9c8ec86bfae6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47766758"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="9576c-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9576c-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="9576c-104">Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9576c-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="9576c-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="9576c-105">Debug logs</span></span>

-   <span data-ttu-id="9576c-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="9576c-106">Media logs</span></span>

-   <span data-ttu-id="9576c-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="9576c-107">Desktop logs</span></span>

<span data-ttu-id="9576c-p101">Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9576c-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="9576c-p102">Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="9576c-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="9576c-113">Client</span><span class="sxs-lookup"><span data-stu-id="9576c-113">Client</span></span> |<span data-ttu-id="9576c-114">Debug</span><span class="sxs-lookup"><span data-stu-id="9576c-114">Debug</span></span>|<span data-ttu-id="9576c-115">Bureau</span><span class="sxs-lookup"><span data-stu-id="9576c-115">Desktop</span></span>|<span data-ttu-id="9576c-116">Media</span><span class="sxs-lookup"><span data-stu-id="9576c-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="9576c-117">Web</span><span class="sxs-lookup"><span data-stu-id="9576c-117">Web</span></span>    |<span data-ttu-id="9576c-118">X</span><span class="sxs-lookup"><span data-stu-id="9576c-118">X</span></span>         |-         |-         |
|<span data-ttu-id="9576c-119">Windows</span><span class="sxs-lookup"><span data-stu-id="9576c-119">Windows</span></span>     |<span data-ttu-id="9576c-120">X</span><span class="sxs-lookup"><span data-stu-id="9576c-120">X</span></span>         |<span data-ttu-id="9576c-121">X</span><span class="sxs-lookup"><span data-stu-id="9576c-121">X</span></span>         |<span data-ttu-id="9576c-122">X</span><span class="sxs-lookup"><span data-stu-id="9576c-122">X</span></span>         |
|<span data-ttu-id="9576c-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9576c-123">Mac OSX</span></span>     |<span data-ttu-id="9576c-124">X</span><span class="sxs-lookup"><span data-stu-id="9576c-124">X</span></span>         |<span data-ttu-id="9576c-125">X</span><span class="sxs-lookup"><span data-stu-id="9576c-125">X</span></span>         |<span data-ttu-id="9576c-126">X</span><span class="sxs-lookup"><span data-stu-id="9576c-126">X</span></span>         |
|<span data-ttu-id="9576c-127">Linux</span><span class="sxs-lookup"><span data-stu-id="9576c-127">Linux</span></span>     |<span data-ttu-id="9576c-128">X</span><span class="sxs-lookup"><span data-stu-id="9576c-128">X</span></span>         |<span data-ttu-id="9576c-129">X</span><span class="sxs-lookup"><span data-stu-id="9576c-129">X</span></span>         |<span data-ttu-id="9576c-130">X</span><span class="sxs-lookup"><span data-stu-id="9576c-130">X</span></span>         |
|<span data-ttu-id="9576c-131">iOS</span><span class="sxs-lookup"><span data-stu-id="9576c-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="9576c-132">Android</span><span class="sxs-lookup"><span data-stu-id="9576c-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="9576c-133">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9576c-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="9576c-134">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="9576c-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="9576c-135">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9576c-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="9576c-136">Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients reposant sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="9576c-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="9576c-137">Il s’agit de fichiers texte qui sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="9576c-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="9576c-138">Ils peuvent être lus à l’aide de n’importe quel éditeur de texte. En outre, des journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="9576c-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="9576c-139">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="9576c-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="9576c-140">Connexion</span><span class="sxs-lookup"><span data-stu-id="9576c-140">Login</span></span>

-   <span data-ttu-id="9576c-141">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="9576c-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="9576c-142">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="9576c-142">Call/conversation</span></span>

<span data-ttu-id="9576c-143">Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="9576c-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="9576c-144">Windows :</span><span class="sxs-lookup"><span data-stu-id="9576c-144">Windows:</span></span>

      <span data-ttu-id="9576c-145">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="9576c-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="9576c-146">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="9576c-146">Mac OSX:</span></span>

      <span data-ttu-id="9576c-147">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="9576c-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="9576c-148">\*</span><span class="sxs-lookup"><span data-stu-id="9576c-148">Linux:</span></span>

      <span data-ttu-id="9576c-149">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="9576c-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="9576c-150">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.</span><span class="sxs-lookup"><span data-stu-id="9576c-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="9576c-151">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="9576c-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="9576c-152">Mac OSX : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="9576c-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="9576c-153">Linux : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="9576c-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="9576c-154">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="9576c-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="9576c-155">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="9576c-155">Media logs</span></span>
---------------------------

<span data-ttu-id="9576c-156">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran dans les réunions Teams.</span><span class="sxs-lookup"><span data-stu-id="9576c-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="9576c-157">Ils sont requis pour les cas d’assistance uniquement en cas de demande et ne peuvent être vérifiés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9576c-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> 

<span data-ttu-id="9576c-158">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="9576c-158">Media logging is turned off by default.</span></span> <span data-ttu-id="9576c-159">Pour consigner les données de diagnostic pour les réunions d’équipes, les utilisateurs doivent activer l’option dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="9576c-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="9576c-160">Accédez à **paramètres**  >  **généraux**, activez la case à cocher **activer la journalisation des diagnostics de réunion (nécessite le redémarrage de l’équipe**), puis redémarrez Teams.</span><span class="sxs-lookup"><span data-stu-id="9576c-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams.</span></span>

<span data-ttu-id="9576c-161">Le tableau suivant présente les emplacements du journal.</span><span class="sxs-lookup"><span data-stu-id="9576c-161">The following table outlines the log locations.</span></span>

|<span data-ttu-id="9576c-162">Client</span><span class="sxs-lookup"><span data-stu-id="9576c-162">Client</span></span> |<span data-ttu-id="9576c-163">Lieu</span><span class="sxs-lookup"><span data-stu-id="9576c-163">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9576c-164">Windows</span><span class="sxs-lookup"><span data-stu-id="9576c-164">Windows</span></span>     |<span data-ttu-id="9576c-165">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-165">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="9576c-166">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-166">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="9576c-167">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="9576c-167">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="9576c-168">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9576c-168">Mac OSX</span></span>     |<span data-ttu-id="9576c-169">~/Library/Application Support/Microsoft/teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-169">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="9576c-170">~/Library/Application Support/Microsoft/teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-170">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="9576c-171">Linux</span><span class="sxs-lookup"><span data-stu-id="9576c-171">Linux</span></span>       |<span data-ttu-id="9576c-172">~/.config/Microsoft/Microsoft teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-172">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="9576c-173">~/.config/Microsoft/Microsoft teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-173">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="9576c-174">Vous trouverez ci-dessous la liste des fichiers journaux générés ainsi que les informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="9576c-174">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="9576c-175">Nom de fichier journal</span><span class="sxs-lookup"><span data-stu-id="9576c-175">Log file name</span></span>  |<span data-ttu-id="9576c-176">Description</span><span class="sxs-lookup"><span data-stu-id="9576c-176">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9576c-177">Teams. msRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-177">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="9576c-178">Contient des informations relatives à la pile multimédia.</span><span class="sxs-lookup"><span data-stu-id="9576c-178">Contains information related to the media stack.</span></span> <span data-ttu-id="9576c-179">Il s’agit de l’état du canal, tel que la résolution, les décodeurs et les encodeurs utilisés, ainsi que le nombre de trames envoyés et reçus, ainsi que l’état de session du partage d’écran vidéo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="9576c-179">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="9576c-180">rtmcontrol. msRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-180">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="9576c-181">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’horodatage lorsque le contrôle est fourni et les informations sur le pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="9576c-181">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="9576c-182">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="9576c-182">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="9576c-183">Enregistre les événements de suivi des piles de médias.</span><span class="sxs-lookup"><span data-stu-id="9576c-183">Records media stack trace events.</span></span>         |
|<span data-ttu-id="9576c-184">Debug-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-184">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="9576c-185">Contient des informations relatives à l’agent de média, y compris la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="9576c-185">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="9576c-186">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="9576c-186">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="9576c-187">Enregistre les événements dans l’API d’appel TS.</span><span class="sxs-lookup"><span data-stu-id="9576c-187">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="9576c-188">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="9576c-188">Desktop logs</span></span>
---------------------

<span data-ttu-id="9576c-p107">Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="9576c-p107">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="9576c-192">Windows :</span><span class="sxs-lookup"><span data-stu-id="9576c-192">Windows:</span></span>

1.  <span data-ttu-id="9576c-193">Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="9576c-193">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="9576c-194">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="9576c-194">Mac OsX:</span></span>

1.  <span data-ttu-id="9576c-195">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="9576c-195">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="9576c-196">\*</span><span class="sxs-lookup"><span data-stu-id="9576c-196">Linux:</span></span>

1.  <span data-ttu-id="9576c-197">Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="9576c-197">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="9576c-198">Client</span><span class="sxs-lookup"><span data-stu-id="9576c-198">Client</span></span> |<span data-ttu-id="9576c-199">Lieu</span><span class="sxs-lookup"><span data-stu-id="9576c-199">Location</span></span> |
|---------|---------|
|<span data-ttu-id="9576c-200">Windows</span><span class="sxs-lookup"><span data-stu-id="9576c-200">Windows</span></span>     |<span data-ttu-id="9576c-201">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="9576c-201">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="9576c-202">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="9576c-202">Mac OSX</span></span>     |<span data-ttu-id="9576c-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="9576c-203">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="9576c-204">Linux</span><span class="sxs-lookup"><span data-stu-id="9576c-204">Linux</span></span>       |<span data-ttu-id="9576c-205">~/.config/Microsoft/Microsoft équipes/logs.txt</span><span class="sxs-lookup"><span data-stu-id="9576c-205">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="9576c-206">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9576c-206">Related topics</span></span>

[<span data-ttu-id="9576c-207">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="9576c-207">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

