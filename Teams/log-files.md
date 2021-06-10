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
ms.openlocfilehash: a18dbef0441055c1202c2b77ce4f8af87040e561
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689692"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="ead61-103">Utilisez les fichiers journaux pour surveiller les données et résoudre les Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ead61-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="ead61-104">Il existe trois types de fichiers journaux produits automatiquement par le client, qui peuvent être mis à profit pour faciliter la surveillance et la résolution des Teams :</span><span class="sxs-lookup"><span data-stu-id="ead61-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="ead61-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="ead61-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="ead61-106">Journaux multimédias</span><span class="sxs-lookup"><span data-stu-id="ead61-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="ead61-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="ead61-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="ead61-108">Cet article décrit ces journaux et leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="ead61-108">This article describes these logs and how they are used.</span></span> <span data-ttu-id="ead61-109">Pour plus d’informations sur la résolution de problèmes spécifiques, voir : [Teams résolution des problèmes.](/MicrosoftTeams/troubleshoot/teams)</span><span class="sxs-lookup"><span data-stu-id="ead61-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="ead61-110">Pour plus d’informations sur la façon de contacter le support technique, voir [Obtenir de l’aide.](/microsoft-365/business-video/get-help-support)</span><span class="sxs-lookup"><span data-stu-id="ead61-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span> <span data-ttu-id="ead61-111">Lorsque vous créez une demande de support auprès du Support Microsoft, l’ingénieur support a besoin des journaux de débogage.</span><span class="sxs-lookup"><span data-stu-id="ead61-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="ead61-112">Disposer des journaux de débogage avant de créer la demande de support permet à Microsoft de rapidement commencer à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="ead61-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="ead61-113">**Les journaux** **multimédias ou** de bureau ne sont requis que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="ead61-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="ead61-114">Dans cet article, les journaux **de débogage** font référence aux journaux utilisés pour le dépannage.</span><span class="sxs-lookup"><span data-stu-id="ead61-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="ead61-115">Toutefois, les fichiers générés pour ces journaux contiennent les journaux **de diagnostic de terme** dans leurs noms.</span><span class="sxs-lookup"><span data-stu-id="ead61-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

## <a name="collect-and-enable-logging"></a><span data-ttu-id="ead61-116">Collecter et activer la journalisation</span><span class="sxs-lookup"><span data-stu-id="ead61-116">Collect and enable logging</span></span>

<span data-ttu-id="ead61-117">Il est important de collecter les journaux dès qu’un problème se produit.</span><span class="sxs-lookup"><span data-stu-id="ead61-117">It’s important to collect logs as soon as an issue occurs.</span></span> <span data-ttu-id="ead61-118">Les journaux peuvent être collectés en quelques clics seulement.</span><span class="sxs-lookup"><span data-stu-id="ead61-118">The logs can be collected together with just a couple of clicks.</span></span>

<span data-ttu-id="ead61-119">Windows : Cliquez avec le bouton droit sur l’icône Teams dans la tray système, puis **sélectionnez Recueillir les fichiers de support.**</span><span class="sxs-lookup"><span data-stu-id="ead61-119">Windows: Right-click on the Teams icon in the system tray and choose **Collect support files**.</span></span> 

<span data-ttu-id="ead61-120">Mac : sélectionnez le menu Aide, puis **sélectionnez Recueillir les fichiers de support.**</span><span class="sxs-lookup"><span data-stu-id="ead61-120">Mac: Select the Help menu and choose **Collect support files**.</span></span>

<span data-ttu-id="ead61-121">Les journaux de débogage, de bureau et multimédia sont collectés dans un dossier avec le nom Journal de diagnostic MSTeams. <local data and time></span><span class="sxs-lookup"><span data-stu-id="ead61-121">Debug, Desktop, and Media logs will be collected in one folder with the name MSTeams Diagnostics Log <local data and time>.</span></span> <span data-ttu-id="ead61-122">Ce dossier peut être compressé et partagé lorsque vous ouvrez une demande de support auprès du Support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ead61-122">This folder can be compressed and shared when you open a support request with Microsoft Support.</span></span> <span data-ttu-id="ead61-123">Le dossier contiendra des dossiers pour bureau, réunion (média) et débogage (web).</span><span class="sxs-lookup"><span data-stu-id="ead61-123">The folder will contain folders for Desktop, Meeting (Media), and Debug (web).</span></span> <span data-ttu-id="ead61-124">Vous pouvez collecter les fichiers à l’aide des raccourcis clavier suivants :</span><span class="sxs-lookup"><span data-stu-id="ead61-124">You can collect the files using the following keyboard shortcuts:</span></span>

<span data-ttu-id="ead61-125">Windows : Crtl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="ead61-125">Windows: Crtl + Alt + Shift + 1</span></span>

<span data-ttu-id="ead61-126">Mac : Option + Commande + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="ead61-126">Mac: Option + Command + Shift + 1</span></span>

<span data-ttu-id="ead61-127">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ead61-127">Media logging is turned off by default.</span></span> <span data-ttu-id="ead61-128">Pour activer la journalisation des médias, les utilisateurs doivent activer l’option dans Teams client.</span><span class="sxs-lookup"><span data-stu-id="ead61-128">To enable Media logging, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="ead61-129">Allez à **Paramètres,** puis sélectionnez Activer la journalisation pour les diagnostics de réunion  >   **(nécessite un redémarrage Teams).**</span><span class="sxs-lookup"><span data-stu-id="ead61-129">Go to **Settings** > **General**, and select **Enable logging for meeting diagnostics (requires restarting Teams)**.</span></span> <span data-ttu-id="ead61-130">Le Teams client doit être redémarré pour que la journalisation commence.</span><span class="sxs-lookup"><span data-stu-id="ead61-130">The Teams client must be restarted for logging to begin.</span></span>

> [!NOTE]
> <span data-ttu-id="ead61-131">Si la journalisation multimédia est activée, des fichiers supplémentaires seront inclus dans le dossier Réunion, lesquels seront nécessaires pour examiner les problèmes audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="ead61-131">If Media logging is enabled, there will be additional files included in the Meeting folder which are necessary for investigating audio and video issues.</span></span> <span data-ttu-id="ead61-132">Si la journalisation multimédia n’est pas activée, le nombre de journaux sera limité.</span><span class="sxs-lookup"><span data-stu-id="ead61-132">If Media logging is not enabled, there will be a limited number of logs available.</span></span>

<span data-ttu-id="ead61-133">Le tableau suivant présente les différents clients et les journaux associés.</span><span class="sxs-lookup"><span data-stu-id="ead61-133">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="ead61-134">Les fichiers journaux sont stockés à des emplacements spécifiques au client et au système d’exploitation.</span><span class="sxs-lookup"><span data-stu-id="ead61-134">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="ead61-135">Client</span><span class="sxs-lookup"><span data-stu-id="ead61-135">Client</span></span> |<span data-ttu-id="ead61-136">Debug</span><span class="sxs-lookup"><span data-stu-id="ead61-136">Debug</span></span>|<span data-ttu-id="ead61-137">Bureau</span><span class="sxs-lookup"><span data-stu-id="ead61-137">Desktop</span></span>|<span data-ttu-id="ead61-138">Media</span><span class="sxs-lookup"><span data-stu-id="ead61-138">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="ead61-139">Web</span><span class="sxs-lookup"><span data-stu-id="ead61-139">Web</span></span>    |<span data-ttu-id="ead61-140">X</span><span class="sxs-lookup"><span data-stu-id="ead61-140">X</span></span>         |-         |-         |
|<span data-ttu-id="ead61-141">Windows</span><span class="sxs-lookup"><span data-stu-id="ead61-141">Windows</span></span>     |<span data-ttu-id="ead61-142">X</span><span class="sxs-lookup"><span data-stu-id="ead61-142">X</span></span>         |<span data-ttu-id="ead61-143">X</span><span class="sxs-lookup"><span data-stu-id="ead61-143">X</span></span>         |<span data-ttu-id="ead61-144">X</span><span class="sxs-lookup"><span data-stu-id="ead61-144">X</span></span>         |
|<span data-ttu-id="ead61-145">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="ead61-145">Mac OSX</span></span>     |<span data-ttu-id="ead61-146">X</span><span class="sxs-lookup"><span data-stu-id="ead61-146">X</span></span>         |<span data-ttu-id="ead61-147">X</span><span class="sxs-lookup"><span data-stu-id="ead61-147">X</span></span>         |<span data-ttu-id="ead61-148">X</span><span class="sxs-lookup"><span data-stu-id="ead61-148">X</span></span>         |
|<span data-ttu-id="ead61-149">Linux</span><span class="sxs-lookup"><span data-stu-id="ead61-149">Linux</span></span>     |<span data-ttu-id="ead61-150">X</span><span class="sxs-lookup"><span data-stu-id="ead61-150">X</span></span>         |<span data-ttu-id="ead61-151">X</span><span class="sxs-lookup"><span data-stu-id="ead61-151">X</span></span>         |<span data-ttu-id="ead61-152">X</span><span class="sxs-lookup"><span data-stu-id="ead61-152">X</span></span>         |
|<span data-ttu-id="ead61-153">iOS</span><span class="sxs-lookup"><span data-stu-id="ead61-153">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="ead61-154">Android</span><span class="sxs-lookup"><span data-stu-id="ead61-154">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="ead61-155">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="ead61-155">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="ead61-156">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="ead61-156">Debug logs</span></span>

<span data-ttu-id="ead61-157">Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac.</span><span class="sxs-lookup"><span data-stu-id="ead61-157">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="ead61-158">Les journaux de débogage sont produits par les clients Windows bureau Mac et les clients de bureau basés sur le navigateur.</span><span class="sxs-lookup"><span data-stu-id="ead61-158">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="ead61-159">Les journaux sont textuels et lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="ead61-159">The logs are text-based and are read from the bottom-up.</span></span> <span data-ttu-id="ead61-160">Ils peuvent être lus à l’aide de n’importe quel éditeur textuel, et de nouveaux journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="ead61-160">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="ead61-161">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="ead61-161">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="ead61-162">Connexion</span><span class="sxs-lookup"><span data-stu-id="ead61-162">Login</span></span>

-   <span data-ttu-id="ead61-163">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="ead61-163">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="ead61-164">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="ead61-164">Call/conversation</span></span>

<span data-ttu-id="ead61-165">Pour collecter les journaux pour Linux : raccourci clavier : Ctrl + Alt + Shift + 1 Les fichiers seront disponibles dans ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="ead61-165">To collect logs for Linux: Keyboard shortcut: Ctrl + Alt + Shift + 1 The files will be available in ~/Downloads</span></span>

<span data-ttu-id="ead61-166">Pour collecter des journaux pour le navigateur : Raccourci clavier : Crtl + Alt + Shift + 1 Les fichiers seront disponibles dans %userprofile%\Downloads</span><span class="sxs-lookup"><span data-stu-id="ead61-166">To collect logs for Browser: Keyboard shortcut: Crtl + Alt + Shift + 1 The files will be available in %userprofile%\Downloads</span></span>

## <a name="media-logs"></a><span data-ttu-id="ead61-167">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="ead61-167">Media logs</span></span>

<span data-ttu-id="ead61-168">Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac.</span><span class="sxs-lookup"><span data-stu-id="ead61-168">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="ead61-169">Les journaux multimédias contiennent des données de diagnostic sur l’audio, la vidéo et le partage d’écran Teams réunions.</span><span class="sxs-lookup"><span data-stu-id="ead61-169">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="ead61-170">Ils sont requis pour les cas de support liés à des problèmes liés aux appels.</span><span class="sxs-lookup"><span data-stu-id="ead61-170">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="ead61-171">La journalisation multimédia est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ead61-171">Media logging is turned off by default.</span></span> <span data-ttu-id="ead61-172">Pour enregistrer des données de diagnostic pour Teams réunions, les utilisateurs doivent activer l’option dans le Teams client.</span><span class="sxs-lookup"><span data-stu-id="ead61-172">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="ead61-173">Allez à **Paramètres,** activez la case à cocher Activer la journalisation pour les diagnostics de réunion (nécessite le redémarrage de  >   **Teams),** redémarrez Teams et reproduisez le problème.</span><span class="sxs-lookup"><span data-stu-id="ead61-173">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="ead61-174">Lorsque vous envoyez les fichiers journaux au support Microsoft, vérifiez l’heure et l’heure des fichiers journaux pour vous assurer que les journaux couvrent la période lors de la reproduction du problème.</span><span class="sxs-lookup"><span data-stu-id="ead61-174">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

<span data-ttu-id="ead61-175">Pour collecter des journaux pour Linux : Les fichiers seront disponibles dans ~/.config/Microsoft/Microsoft Teams/media-stack/ .blog et *~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span><span class="sxs-lookup"><span data-stu-id="ead61-175">To collect logs for Linux: The files will be available in ~/.config/Microsoft/Microsoft Teams/media-stack/*.blog and ~/.config/Microsoft/Microsoft Teams/skylib/*.blog.</span></span>

<span data-ttu-id="ead61-176">Voici une liste des fichiers journaux générés et des informations qu’ils contiennent.</span><span class="sxs-lookup"><span data-stu-id="ead61-176">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="ead61-177">Nom du fichier journal</span><span class="sxs-lookup"><span data-stu-id="ead61-177">Log file name</span></span>  |<span data-ttu-id="ead61-178">Description</span><span class="sxs-lookup"><span data-stu-id="ead61-178">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ead61-179">Teams,msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="ead61-179">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="ead61-180">Contient des informations relatives à la pile de médias.</span><span class="sxs-lookup"><span data-stu-id="ead61-180">Contains information related to the media stack.</span></span> <span data-ttu-id="ead61-181">Cela inclut l’état des canaux tels que la résolution, les décodeurs et les encodeurs utilisés, le nombre de trames envoyées et reçues, ainsi que l’état de la session de partage d’écran vidéo et de caméra (VBSS).</span><span class="sxs-lookup"><span data-stu-id="ead61-181">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="ead61-182">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="ead61-182">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="ead61-183">Enregistre les informations relatives aux actions de contrôle à distance, telles que l’heure à l’donnée du contrôle et les informations du pointeur de la souris.</span><span class="sxs-lookup"><span data-stu-id="ead61-183">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="ead61-184">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="ead61-184">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="ead61-185">Événements de suivi de pile de fichiers multimédias d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="ead61-185">Records media stack trace events.</span></span>         |
|<span data-ttu-id="ead61-186">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="ead61-186">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="ead61-187">Contient des informations relatives à l’agent multimédia, notamment la qualité de rendu.</span><span class="sxs-lookup"><span data-stu-id="ead61-187">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="ead61-188">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="ead61-188">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="ead61-189">Enregistre les événements dans l’API ts-calling.</span><span class="sxs-lookup"><span data-stu-id="ead61-189">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="ead61-190">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="ead61-190">Desktop logs</span></span>

<span data-ttu-id="ead61-191">Consultez la section _Recueillir et activer la journalisation_ pour consulter Windows instructions pour Mac.</span><span class="sxs-lookup"><span data-stu-id="ead61-191">See the _Collect and enable logging_ section for Windows and Mac instructions.</span></span> <span data-ttu-id="ead61-192">Les journaux de bureau, également appelés journaux de la pipette, contiennent des données de journal qui se produisent entre le client de bureau et le navigateur.</span><span class="sxs-lookup"><span data-stu-id="ead61-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="ead61-193">Comme les journaux multimédias, ces journaux ne sont nécessaires que si Microsoft les demande.</span><span class="sxs-lookup"><span data-stu-id="ead61-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="ead61-194">Les journaux sont textuels et peuvent être lus à l’aide de n’importe quel éditeur textuel dans un format de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="ead61-194">The logs are text-based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="ead61-195">Pour collecter des journaux pour Linux : Cliquez sur l’icône Microsoft Teams dans votre bac système, puis **sélectionnez Obtenir les journaux.**</span><span class="sxs-lookup"><span data-stu-id="ead61-195">To collect logs for Linux: Click on the Microsoft Teams icon in your system tray, and select **Get Logs**.</span></span>
<span data-ttu-id="ead61-196">Les fichiers seront disponibles dans ~/.config/Microsoft/Microsoft Teams/logs.txt.</span><span class="sxs-lookup"><span data-stu-id="ead61-196">The files will be available in ~/.config/Microsoft/Microsoft Teams/logs.txt.</span></span>  


## <a name="browser-trace"></a><span data-ttu-id="ead61-197">Suivi du navigateur</span><span class="sxs-lookup"><span data-stu-id="ead61-197">Browser trace</span></span>

<span data-ttu-id="ead61-198">Pour certaines catégories d’erreurs, le Support Microsoft peut exiger que vous collectiez un suivi du navigateur.</span><span class="sxs-lookup"><span data-stu-id="ead61-198">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="ead61-199">Ces informations peuvent fournir des détails importants sur l’état du client Teams lorsque l’erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="ead61-199">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="ead61-200">Avant de commencer la trace du navigateur, assurez-vous que vous êtes bien inscrit à Teams.</span><span class="sxs-lookup"><span data-stu-id="ead61-200">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="ead61-201">Il est important de le faire avant de commencer la trace de sorte que celle-ci ne contienne pas d’informations de signature sensibles.</span><span class="sxs-lookup"><span data-stu-id="ead61-201">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="ead61-202">Une fois que vous êtes inscrit, sélectionnez l’un des liens suivants, le cas échéant, pour votre navigateur, puis suivez les étapes fournies.</span><span class="sxs-lookup"><span data-stu-id="ead61-202">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="ead61-203">Chrome & Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="ead61-203">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="ead61-204">Edge</span><span class="sxs-lookup"><span data-stu-id="ead61-204">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="ead61-205">Safari</span><span class="sxs-lookup"><span data-stu-id="ead61-205">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="ead61-206">Firefox</span><span class="sxs-lookup"><span data-stu-id="ead61-206">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="ead61-207">Au cours des étapes, remplacez toutes les références au portail Azure par le client Teams client.</span><span class="sxs-lookup"><span data-stu-id="ead61-207">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="ead61-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ead61-208">Related topics</span></span>

[<span data-ttu-id="ead61-209">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="ead61-209">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
