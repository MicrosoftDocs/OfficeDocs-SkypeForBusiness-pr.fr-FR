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
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264874"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="01360-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="01360-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="01360-104">Il existe trois types de fichiers journaux produits automatiquement par le client, qui peuvent être mis à profit pour faciliter la résolution des Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="01360-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="01360-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="01360-105">Debug logs</span></span>

-   <span data-ttu-id="01360-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="01360-106">Media logs</span></span>

-   <span data-ttu-id="01360-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="01360-107">Desktop logs</span></span>

<span data-ttu-id="01360-108">Lorsque vous créez une demande de support auprès du Support Microsoft, l’ingénieur support a besoin des journaux de débogage.</span><span class="sxs-lookup"><span data-stu-id="01360-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="01360-109">Disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de rapidement commencer à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="01360-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="01360-110">**Les journaux** **multimédias ou** de bureau ne sont requis que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="01360-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="01360-111">Dans cet article, les journaux **de débogage** font référence aux journaux utilisés pour le dépannage.</span><span class="sxs-lookup"><span data-stu-id="01360-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="01360-112">Toutefois, les fichiers générés pour ces journaux contiennent les journaux **de diagnostic de terme** dans leurs noms.</span><span class="sxs-lookup"><span data-stu-id="01360-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="01360-113">Le tableau suivant présente les différents clients et les journaux associés.</span><span class="sxs-lookup"><span data-stu-id="01360-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="01360-114">Les fichiers journaux sont stockés à des emplacements spécifiques au client et au système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="01360-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="01360-115">Client</span><span class="sxs-lookup"><span data-stu-id="01360-115">Client</span></span> |<span data-ttu-id="01360-116">Debug</span><span class="sxs-lookup"><span data-stu-id="01360-116">Debug</span></span>|<span data-ttu-id="01360-117">Bureau</span><span class="sxs-lookup"><span data-stu-id="01360-117">Desktop</span></span>|<span data-ttu-id="01360-118">Media</span><span class="sxs-lookup"><span data-stu-id="01360-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="01360-119">Web</span><span class="sxs-lookup"><span data-stu-id="01360-119">Web</span></span>    |<span data-ttu-id="01360-120">X</span><span class="sxs-lookup"><span data-stu-id="01360-120">X</span></span>         |-         |-         |
|<span data-ttu-id="01360-121">Windows</span><span class="sxs-lookup"><span data-stu-id="01360-121">Windows</span></span>     |<span data-ttu-id="01360-122">X</span><span class="sxs-lookup"><span data-stu-id="01360-122">X</span></span>         |<span data-ttu-id="01360-123">X</span><span class="sxs-lookup"><span data-stu-id="01360-123">X</span></span>         |<span data-ttu-id="01360-124">X</span><span class="sxs-lookup"><span data-stu-id="01360-124">X</span></span>         |
|<span data-ttu-id="01360-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="01360-125">Mac OSX</span></span>     |<span data-ttu-id="01360-126">X</span><span class="sxs-lookup"><span data-stu-id="01360-126">X</span></span>         |<span data-ttu-id="01360-127">X</span><span class="sxs-lookup"><span data-stu-id="01360-127">X</span></span>         |<span data-ttu-id="01360-128">X</span><span class="sxs-lookup"><span data-stu-id="01360-128">X</span></span>         |
|<span data-ttu-id="01360-129">Linux</span><span class="sxs-lookup"><span data-stu-id="01360-129">Linux</span></span>     |<span data-ttu-id="01360-130">X</span><span class="sxs-lookup"><span data-stu-id="01360-130">X</span></span>         |<span data-ttu-id="01360-131">X</span><span class="sxs-lookup"><span data-stu-id="01360-131">X</span></span>         |<span data-ttu-id="01360-132">X</span><span class="sxs-lookup"><span data-stu-id="01360-132">X</span></span>         |
|<span data-ttu-id="01360-133">iOS</span><span class="sxs-lookup"><span data-stu-id="01360-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="01360-134">Android</span><span class="sxs-lookup"><span data-stu-id="01360-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="01360-135">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="01360-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="01360-136">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="01360-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="01360-137">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="01360-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="01360-138">Les journaux de débogage sont produits par les clients Windows bureau Mac et les clients de bureau basés sur le navigateur.</span><span class="sxs-lookup"><span data-stu-id="01360-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="01360-139">Les journaux sont basés sur du texte et sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="01360-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="01360-140">Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="01360-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="01360-141">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="01360-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="01360-142">Connexion</span><span class="sxs-lookup"><span data-stu-id="01360-142">Login</span></span>

-   <span data-ttu-id="01360-143">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="01360-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="01360-144">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="01360-144">Call/conversation</span></span>

<span data-ttu-id="01360-145">Les journaux de débogage sont produits à l’aide des méthodes de système d’exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="01360-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="01360-146">Windows :</span><span class="sxs-lookup"><span data-stu-id="01360-146">Windows:</span></span>

      <span data-ttu-id="01360-147">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="01360-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="01360-148">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="01360-148">Mac OSX:</span></span>

      <span data-ttu-id="01360-149">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="01360-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="01360-150">Linux :</span><span class="sxs-lookup"><span data-stu-id="01360-150">Linux:</span></span>

      <span data-ttu-id="01360-151">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="01360-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="01360-152">Les journaux de débogage sont téléchargés automatiquement dans les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="01360-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="01360-153">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="01360-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="01360-154">Mac OSX : ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="01360-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="01360-155">Linux : ~/Téléchargements</span><span class="sxs-lookup"><span data-stu-id="01360-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="01360-156">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="01360-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="01360-157">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="01360-157">Media logs</span></span>
---------------------------

<span data-ttu-id="01360-158">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran Teams réunions.</span><span class="sxs-lookup"><span data-stu-id="01360-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="01360-159">Ils sont requis pour les cas de support liés à des problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="01360-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="01360-160">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="01360-160">Media logging is turned off by default.</span></span> <span data-ttu-id="01360-161">Pour enregistrer des données de diagnostic pour Teams réunions, les utilisateurs doivent activer l’option dans le Teams client.</span><span class="sxs-lookup"><span data-stu-id="01360-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="01360-162">Allez à **Paramètres,** activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de  >   **Teams),** redémarrez Teams et reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="01360-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="01360-163">Le tableau suivant présente les emplacements des journaux multimédias.</span><span class="sxs-lookup"><span data-stu-id="01360-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="01360-164">Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’heure et l’heure des fichiers journaux pour vous assurer que les journaux couvrent la période lors de la reproduction du problème.</span><span class="sxs-lookup"><span data-stu-id="01360-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="01360-165">Client</span><span class="sxs-lookup"><span data-stu-id="01360-165">Client</span></span> |<span data-ttu-id="01360-166">Lieu</span><span class="sxs-lookup"><span data-stu-id="01360-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="01360-167">Windows</span><span class="sxs-lookup"><span data-stu-id="01360-167">Windows</span></span>     |<span data-ttu-id="01360-168">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="01360-169">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="01360-170">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="01360-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="01360-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="01360-171">Mac OSX</span></span>     |<span data-ttu-id="01360-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="01360-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="01360-174">Linux</span><span class="sxs-lookup"><span data-stu-id="01360-174">Linux</span></span>       |<span data-ttu-id="01360-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="01360-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="01360-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="01360-177">Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="01360-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="01360-178">Nom du fichier journal</span><span class="sxs-lookup"><span data-stu-id="01360-178">Log file name</span></span>  |<span data-ttu-id="01360-179">Description</span><span class="sxs-lookup"><span data-stu-id="01360-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="01360-180">Teams,msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="01360-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="01360-181">Contient des informations relatives à la pile de médias.</span><span class="sxs-lookup"><span data-stu-id="01360-181">Contains information related to the media stack.</span></span> <span data-ttu-id="01360-182">Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).</span><span class="sxs-lookup"><span data-stu-id="01360-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="01360-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="01360-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="01360-184">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="01360-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="01360-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="01360-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="01360-186">Événements de suivi de pile de fichiers multimédias d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="01360-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="01360-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="01360-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="01360-188">Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="01360-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="01360-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="01360-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="01360-190">Enregistre les événements dans l’API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="01360-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="01360-191">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="01360-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="01360-192">Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur.</span><span class="sxs-lookup"><span data-stu-id="01360-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="01360-193">Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="01360-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="01360-194">Les journaux sont basés sur du texte et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="01360-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="01360-195">Windows :</span><span class="sxs-lookup"><span data-stu-id="01360-195">Windows:</span></span>

 - <span data-ttu-id="01360-196">Cliquez avec le bouton droit **sur l Microsoft Teams** de connexion dans votre bac système, puis **sélectionnez Obtenir les journaux.**</span><span class="sxs-lookup"><span data-stu-id="01360-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="01360-197">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="01360-197">Mac OsX:</span></span>

 - <span data-ttu-id="01360-198">Sélectionnez **Obtenir les journaux** dans **le** menu déroulant Aide.</span><span class="sxs-lookup"><span data-stu-id="01360-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="01360-199">Linux :</span><span class="sxs-lookup"><span data-stu-id="01360-199">Linux:</span></span>

 - <span data-ttu-id="01360-200">Cliquez sur **l’Microsoft Teams** dans votre bac système, puis **sélectionnez Obtenir les journaux.**</span><span class="sxs-lookup"><span data-stu-id="01360-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="01360-201">Client</span><span class="sxs-lookup"><span data-stu-id="01360-201">Client</span></span> |<span data-ttu-id="01360-202">Lieu</span><span class="sxs-lookup"><span data-stu-id="01360-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="01360-203">Windows</span><span class="sxs-lookup"><span data-stu-id="01360-203">Windows</span></span>     |<span data-ttu-id="01360-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="01360-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="01360-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="01360-205">Mac OSX</span></span>     |<span data-ttu-id="01360-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="01360-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="01360-207">Linux</span><span class="sxs-lookup"><span data-stu-id="01360-207">Linux</span></span>       |<span data-ttu-id="01360-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="01360-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="01360-209">Suivi du navigateur</span><span class="sxs-lookup"><span data-stu-id="01360-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="01360-210">Pour certaines catégories d’erreurs, le Support Microsoft peut exiger que vous collectiez un suivi du navigateur.</span><span class="sxs-lookup"><span data-stu-id="01360-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="01360-211">Ces informations peuvent fournir des détails importants sur l’état du client Teams lorsque l’erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="01360-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="01360-212">Avant de commencer la trace du navigateur, assurez-vous que vous êtes bien inscrit à Teams.</span><span class="sxs-lookup"><span data-stu-id="01360-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="01360-213">Il est important de le faire avant de commencer la trace de sorte que celle-ci ne contienne pas d’informations de signature sensibles.</span><span class="sxs-lookup"><span data-stu-id="01360-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="01360-214">Une fois que vous êtes inscrit, sélectionnez l’un des liens suivants, le cas échéant, pour votre navigateur, puis suivez les étapes fournies.</span><span class="sxs-lookup"><span data-stu-id="01360-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="01360-215">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="01360-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="01360-216">Edge</span><span class="sxs-lookup"><span data-stu-id="01360-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="01360-217">Safari</span><span class="sxs-lookup"><span data-stu-id="01360-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="01360-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="01360-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="01360-219">Au cours des étapes, remplacez toutes les références au portail Azure par le client Teams client.</span><span class="sxs-lookup"><span data-stu-id="01360-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="01360-220">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01360-220">Related topics</span></span>

[<span data-ttu-id="01360-221">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="01360-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
