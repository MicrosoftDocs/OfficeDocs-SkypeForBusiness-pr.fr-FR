---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux de débogage, multimédias et de bureau produits par Microsoft Teams, où ils sont trouvés et comment ils peuvent vous aider dans la surveillance et la résolution des problèmes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337741"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="6b1be-103">Utilisez les fichiers journaux pour surveiller les données et résoudre les Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6b1be-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="6b1be-104">Il existe trois types de fichiers journaux produits automatiquement par le client, qui peuvent être mis à profit pour faciliter la surveillance et la résolution des Teams :</span><span class="sxs-lookup"><span data-stu-id="6b1be-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="6b1be-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="6b1be-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="6b1be-106">Journaux multimédias</span><span class="sxs-lookup"><span data-stu-id="6b1be-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="6b1be-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="6b1be-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="6b1be-108">Cet article décrit les trois journaux et leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="6b1be-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="6b1be-109">Pour plus d’informations sur la résolution de problèmes spécifiques, voir : [Teams résolution des problèmes.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="6b1be-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="6b1be-110">Pour plus d’informations sur la façon de contacter le support technique, voir [Obtenir de l’aide.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="6b1be-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="6b1be-111">Lorsque vous créez une demande de support auprès du Support Microsoft, l’ingénieur support a besoin des journaux de débogage.</span><span class="sxs-lookup"><span data-stu-id="6b1be-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="6b1be-112">Disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de rapidement commencer à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="6b1be-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="6b1be-113">**Les journaux** **multimédias ou** de bureau ne sont requis que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="6b1be-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="6b1be-114">Dans cet article, les journaux **de débogage** font référence aux journaux utilisés pour le dépannage.</span><span class="sxs-lookup"><span data-stu-id="6b1be-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="6b1be-115">Toutefois, les fichiers générés pour ces journaux contiennent les journaux **de diagnostic de terme** dans leurs noms.</span><span class="sxs-lookup"><span data-stu-id="6b1be-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="6b1be-116">Le tableau suivant présente les différents clients et les journaux associés.</span><span class="sxs-lookup"><span data-stu-id="6b1be-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="6b1be-117">Les fichiers journaux sont stockés à des emplacements spécifiques au client et au système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="6b1be-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="6b1be-118">Client</span><span class="sxs-lookup"><span data-stu-id="6b1be-118">Client</span></span> |<span data-ttu-id="6b1be-119">Debug</span><span class="sxs-lookup"><span data-stu-id="6b1be-119">Debug</span></span>|<span data-ttu-id="6b1be-120">Bureau</span><span class="sxs-lookup"><span data-stu-id="6b1be-120">Desktop</span></span>|<span data-ttu-id="6b1be-121">Media</span><span class="sxs-lookup"><span data-stu-id="6b1be-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="6b1be-122">Web</span><span class="sxs-lookup"><span data-stu-id="6b1be-122">Web</span></span>    |<span data-ttu-id="6b1be-123">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-123">X</span></span>         |-         |-         |
|<span data-ttu-id="6b1be-124">Windows</span><span class="sxs-lookup"><span data-stu-id="6b1be-124">Windows</span></span>     |<span data-ttu-id="6b1be-125">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-125">X</span></span>         |<span data-ttu-id="6b1be-126">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-126">X</span></span>         |<span data-ttu-id="6b1be-127">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-127">X</span></span>         |
|<span data-ttu-id="6b1be-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6b1be-128">Mac OSX</span></span>     |<span data-ttu-id="6b1be-129">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-129">X</span></span>         |<span data-ttu-id="6b1be-130">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-130">X</span></span>         |<span data-ttu-id="6b1be-131">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-131">X</span></span>         |
|<span data-ttu-id="6b1be-132">Linux</span><span class="sxs-lookup"><span data-stu-id="6b1be-132">Linux</span></span>     |<span data-ttu-id="6b1be-133">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-133">X</span></span>         |<span data-ttu-id="6b1be-134">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-134">X</span></span>         |<span data-ttu-id="6b1be-135">X</span><span class="sxs-lookup"><span data-stu-id="6b1be-135">X</span></span>         |
|<span data-ttu-id="6b1be-136">iOS</span><span class="sxs-lookup"><span data-stu-id="6b1be-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="6b1be-137">Android</span><span class="sxs-lookup"><span data-stu-id="6b1be-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="6b1be-138">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="6b1be-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="6b1be-139">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="6b1be-139">Debug logs</span></span>

<span data-ttu-id="6b1be-140">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b1be-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="6b1be-141">Les journaux de débogage sont produits par les clients Windows bureau Mac et les clients de bureau basés sur le navigateur.</span><span class="sxs-lookup"><span data-stu-id="6b1be-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="6b1be-142">Les journaux sont basés sur du texte et sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="6b1be-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="6b1be-143">Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="6b1be-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="6b1be-144">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="6b1be-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="6b1be-145">Connexion</span><span class="sxs-lookup"><span data-stu-id="6b1be-145">Login</span></span>

-   <span data-ttu-id="6b1be-146">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="6b1be-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="6b1be-147">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="6b1be-147">Call/conversation</span></span>

<span data-ttu-id="6b1be-148">Les journaux de débogage sont produits à l’aide des méthodes de système d’exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="6b1be-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="6b1be-149">Windows :</span><span class="sxs-lookup"><span data-stu-id="6b1be-149">Windows:</span></span>

      <span data-ttu-id="6b1be-150">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="6b1be-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="6b1be-151">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="6b1be-151">Mac OSX:</span></span>

      <span data-ttu-id="6b1be-152">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="6b1be-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="6b1be-153">Linux :</span><span class="sxs-lookup"><span data-stu-id="6b1be-153">Linux:</span></span>

      <span data-ttu-id="6b1be-154">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="6b1be-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="6b1be-155">Les journaux de débogage sont téléchargés automatiquement dans les dossiers suivants :</span><span class="sxs-lookup"><span data-stu-id="6b1be-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="6b1be-156">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="6b1be-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="6b1be-157">Mac OSX : ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="6b1be-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="6b1be-158">Linux : ~/Téléchargements</span><span class="sxs-lookup"><span data-stu-id="6b1be-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="6b1be-159">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="6b1be-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="6b1be-160">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="6b1be-160">Media logs</span></span>

<span data-ttu-id="6b1be-161">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran Teams réunions.</span><span class="sxs-lookup"><span data-stu-id="6b1be-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="6b1be-162">Ils sont requis pour les cas de support liés à des problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="6b1be-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="6b1be-163">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="6b1be-163">Media logging is turned off by default.</span></span> <span data-ttu-id="6b1be-164">Pour enregistrer des données de diagnostic pour Teams réunions, les utilisateurs doivent activer l’option dans le Teams client.</span><span class="sxs-lookup"><span data-stu-id="6b1be-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="6b1be-165">Allez à **Paramètres,** activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de  >   **Teams),** redémarrez Teams et reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="6b1be-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="6b1be-166">Le tableau suivant présente les emplacements des journaux multimédias.</span><span class="sxs-lookup"><span data-stu-id="6b1be-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="6b1be-167">Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’heure et l’heure des fichiers journaux pour vous assurer que les journaux couvrent la période lors de la reproduction du problème.</span><span class="sxs-lookup"><span data-stu-id="6b1be-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="6b1be-168">Client</span><span class="sxs-lookup"><span data-stu-id="6b1be-168">Client</span></span> |<span data-ttu-id="6b1be-169">Lieu</span><span class="sxs-lookup"><span data-stu-id="6b1be-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="6b1be-170">Windows</span><span class="sxs-lookup"><span data-stu-id="6b1be-170">Windows</span></span>     |<span data-ttu-id="6b1be-171">%appdata%\Microsoft\Teams\media-stack \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="6b1be-172">%appdata%\Microsoft\Teams\skylib \\ \*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="6b1be-173">%appdata%\Microsoft\Teams\media-stack \\ \*.etl</span><span class="sxs-lookup"><span data-stu-id="6b1be-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="6b1be-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6b1be-174">Mac OSX</span></span>     |<span data-ttu-id="6b1be-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="6b1be-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="6b1be-177">Linux</span><span class="sxs-lookup"><span data-stu-id="6b1be-177">Linux</span></span>       |<span data-ttu-id="6b1be-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="6b1be-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="6b1be-180">Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="6b1be-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="6b1be-181">Nom du fichier journal</span><span class="sxs-lookup"><span data-stu-id="6b1be-181">Log file name</span></span>  |<span data-ttu-id="6b1be-182">Description</span><span class="sxs-lookup"><span data-stu-id="6b1be-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6b1be-183">Teams,msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="6b1be-184">Contient des informations relatives à la pile de médias.</span><span class="sxs-lookup"><span data-stu-id="6b1be-184">Contains information related to the media stack.</span></span> <span data-ttu-id="6b1be-185">Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).</span><span class="sxs-lookup"><span data-stu-id="6b1be-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="6b1be-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="6b1be-187">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="6b1be-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="6b1be-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="6b1be-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="6b1be-189">Événements de suivi de pile de fichiers multimédias d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="6b1be-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="6b1be-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="6b1be-191">Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="6b1be-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="6b1be-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="6b1be-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="6b1be-193">Enregistre les événements dans l’API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="6b1be-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="6b1be-194">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="6b1be-194">Desktop logs</span></span>

<span data-ttu-id="6b1be-195">Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur.</span><span class="sxs-lookup"><span data-stu-id="6b1be-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="6b1be-196">Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="6b1be-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="6b1be-197">Les journaux sont basés sur du texte et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="6b1be-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="6b1be-198">Windows :</span><span class="sxs-lookup"><span data-stu-id="6b1be-198">Windows:</span></span>

 - <span data-ttu-id="6b1be-199">Cliquez avec le bouton droit **sur l Microsoft Teams** de connexion dans votre bac système, puis **sélectionnez Obtenir les journaux.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="6b1be-200">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="6b1be-200">Mac OsX:</span></span>

 - <span data-ttu-id="6b1be-201">Sélectionnez **Obtenir les journaux** dans **le** menu déroulant Aide.</span><span class="sxs-lookup"><span data-stu-id="6b1be-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="6b1be-202">Linux :</span><span class="sxs-lookup"><span data-stu-id="6b1be-202">Linux:</span></span>

 - <span data-ttu-id="6b1be-203">Cliquez sur **l’Microsoft Teams** dans votre bac système, puis **sélectionnez Obtenir les journaux.**</span><span class="sxs-lookup"><span data-stu-id="6b1be-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="6b1be-204">Client</span><span class="sxs-lookup"><span data-stu-id="6b1be-204">Client</span></span> |<span data-ttu-id="6b1be-205">Lieu</span><span class="sxs-lookup"><span data-stu-id="6b1be-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="6b1be-206">Windows</span><span class="sxs-lookup"><span data-stu-id="6b1be-206">Windows</span></span>     |<span data-ttu-id="6b1be-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="6b1be-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="6b1be-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="6b1be-208">Mac OSX</span></span>     |<span data-ttu-id="6b1be-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="6b1be-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="6b1be-210">Linux</span><span class="sxs-lookup"><span data-stu-id="6b1be-210">Linux</span></span>       |<span data-ttu-id="6b1be-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="6b1be-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="6b1be-212">Suivi du navigateur</span><span class="sxs-lookup"><span data-stu-id="6b1be-212">Browser trace</span></span>

<span data-ttu-id="6b1be-213">Pour certaines catégories d’erreurs, le Support Microsoft peut exiger que vous collectiez un suivi du navigateur.</span><span class="sxs-lookup"><span data-stu-id="6b1be-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="6b1be-214">Ces informations peuvent fournir des détails importants sur l’état du client Teams lorsque l’erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="6b1be-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="6b1be-215">Avant de commencer la trace du navigateur, assurez-vous que vous êtes bien inscrit à Teams.</span><span class="sxs-lookup"><span data-stu-id="6b1be-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="6b1be-216">Il est important de le faire avant de commencer la trace de sorte que celle-ci ne contienne pas d’informations de signature sensibles.</span><span class="sxs-lookup"><span data-stu-id="6b1be-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="6b1be-217">Une fois que vous êtes inscrit, sélectionnez l’un des liens suivants, le cas échéant, pour votre navigateur, puis suivez les étapes fournies.</span><span class="sxs-lookup"><span data-stu-id="6b1be-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="6b1be-218">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="6b1be-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="6b1be-219">Edge</span><span class="sxs-lookup"><span data-stu-id="6b1be-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="6b1be-220">Safari</span><span class="sxs-lookup"><span data-stu-id="6b1be-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="6b1be-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="6b1be-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="6b1be-222">Au cours des étapes, remplacez toutes les références au portail Azure par le client Teams client.</span><span class="sxs-lookup"><span data-stu-id="6b1be-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6b1be-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b1be-223">Related topics</span></span>

[<span data-ttu-id="6b1be-224">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="6b1be-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
