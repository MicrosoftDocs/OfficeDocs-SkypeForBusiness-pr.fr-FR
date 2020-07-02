---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
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
ms.openlocfilehash: 7ad44af297cdfe375f28485e1c4c4e223f616666
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012190"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="b548b-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b548b-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="b548b-104">Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b548b-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="b548b-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="b548b-105">Debug logs</span></span>

-   <span data-ttu-id="b548b-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="b548b-106">Media logs</span></span>

-   <span data-ttu-id="b548b-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="b548b-107">Desktop logs</span></span>

<span data-ttu-id="b548b-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span><span class="sxs-lookup"><span data-stu-id="b548b-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="b548b-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span><span class="sxs-lookup"><span data-stu-id="b548b-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="b548b-110">Media or desktop logs are only required if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b548b-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="b548b-111">The following table outlines the various clients, and their associated logs.</span><span class="sxs-lookup"><span data-stu-id="b548b-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="b548b-112">Log files are stored in locations specific to the client and operating system.</span><span class="sxs-lookup"><span data-stu-id="b548b-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b548b-113">Client</span><span class="sxs-lookup"><span data-stu-id="b548b-113">Client</span></span> |<span data-ttu-id="b548b-114">Debug</span><span class="sxs-lookup"><span data-stu-id="b548b-114">Debug</span></span>|<span data-ttu-id="b548b-115">Bureau</span><span class="sxs-lookup"><span data-stu-id="b548b-115">Desktop</span></span>|<span data-ttu-id="b548b-116">Media</span><span class="sxs-lookup"><span data-stu-id="b548b-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b548b-117">Web</span><span class="sxs-lookup"><span data-stu-id="b548b-117">Web</span></span>    |<span data-ttu-id="b548b-118">X</span><span class="sxs-lookup"><span data-stu-id="b548b-118">X</span></span>         |-         |-         |
|<span data-ttu-id="b548b-119">Windows</span><span class="sxs-lookup"><span data-stu-id="b548b-119">Windows</span></span>     |<span data-ttu-id="b548b-120">X</span><span class="sxs-lookup"><span data-stu-id="b548b-120">X</span></span>         |<span data-ttu-id="b548b-121">X</span><span class="sxs-lookup"><span data-stu-id="b548b-121">X</span></span>         |<span data-ttu-id="b548b-122">X</span><span class="sxs-lookup"><span data-stu-id="b548b-122">X</span></span>         |
|<span data-ttu-id="b548b-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b548b-123">Mac OSX</span></span>     |<span data-ttu-id="b548b-124">X</span><span class="sxs-lookup"><span data-stu-id="b548b-124">X</span></span>         |<span data-ttu-id="b548b-125">X</span><span class="sxs-lookup"><span data-stu-id="b548b-125">X</span></span>         |<span data-ttu-id="b548b-126">X</span><span class="sxs-lookup"><span data-stu-id="b548b-126">X</span></span>         |
|<span data-ttu-id="b548b-127">Linux</span><span class="sxs-lookup"><span data-stu-id="b548b-127">Linux</span></span>     |<span data-ttu-id="b548b-128">X</span><span class="sxs-lookup"><span data-stu-id="b548b-128">X</span></span>         |<span data-ttu-id="b548b-129">X</span><span class="sxs-lookup"><span data-stu-id="b548b-129">X</span></span>         |<span data-ttu-id="b548b-130">X</span><span class="sxs-lookup"><span data-stu-id="b548b-130">X</span></span>         |
|<span data-ttu-id="b548b-131">iOS</span><span class="sxs-lookup"><span data-stu-id="b548b-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b548b-132">Android</span><span class="sxs-lookup"><span data-stu-id="b548b-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b548b-133">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b548b-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="b548b-134">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="b548b-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="b548b-135">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b548b-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="b548b-136">Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients reposant sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="b548b-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="b548b-137">Il s’agit de fichiers texte qui sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="b548b-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="b548b-138">Ils peuvent être lus à l’aide de n’importe quel éditeur de texte. En outre, des journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="b548b-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b548b-139">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="b548b-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b548b-140">Connexion</span><span class="sxs-lookup"><span data-stu-id="b548b-140">Login</span></span>

-   <span data-ttu-id="b548b-141">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="b548b-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="b548b-142">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="b548b-142">Call/conversation</span></span>

<span data-ttu-id="b548b-143">Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="b548b-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="b548b-144">Windows :</span><span class="sxs-lookup"><span data-stu-id="b548b-144">Windows:</span></span>

      <span data-ttu-id="b548b-145">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="b548b-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="b548b-146">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="b548b-146">Mac OSX:</span></span>

      <span data-ttu-id="b548b-147">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="b548b-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="b548b-148">\*</span><span class="sxs-lookup"><span data-stu-id="b548b-148">Linux:</span></span>

      <span data-ttu-id="b548b-149">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="b548b-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="b548b-150">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.</span><span class="sxs-lookup"><span data-stu-id="b548b-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="b548b-151">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="b548b-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="b548b-152">Mac OSX : Téléchargements</span><span class="sxs-lookup"><span data-stu-id="b548b-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="b548b-153">Linux : ~/downloads</span><span class="sxs-lookup"><span data-stu-id="b548b-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="b548b-154">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="b548b-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="b548b-155">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="b548b-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="b548b-156">Media logs contain diagnostic data about audio, video and screen sharing.</span><span class="sxs-lookup"><span data-stu-id="b548b-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="b548b-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b548b-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="b548b-158">The following table outlines the log location.</span><span class="sxs-lookup"><span data-stu-id="b548b-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="b548b-159">Client</span><span class="sxs-lookup"><span data-stu-id="b548b-159">Client</span></span> |<span data-ttu-id="b548b-160">Lieu</span><span class="sxs-lookup"><span data-stu-id="b548b-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b548b-161">Windows</span><span class="sxs-lookup"><span data-stu-id="b548b-161">Windows</span></span>     |<span data-ttu-id="b548b-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="b548b-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="b548b-164">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="b548b-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="b548b-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b548b-165">Mac OSX</span></span>     |<span data-ttu-id="b548b-166">~/Library/Application Support/Microsoft/teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b548b-167">~/Library/Application Support/Microsoft/teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="b548b-168">Linux</span><span class="sxs-lookup"><span data-stu-id="b548b-168">Linux</span></span>       |<span data-ttu-id="b548b-169">~/.config/Microsoft/Microsoft teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="b548b-170">~/.config/Microsoft/Microsoft teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="b548b-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="b548b-171">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="b548b-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="b548b-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span><span class="sxs-lookup"><span data-stu-id="b548b-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="b548b-173">Like media logs, these logs are only needed if requested by Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b548b-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="b548b-174">The logs are text based and can be read using any text based editor in a top down format.</span><span class="sxs-lookup"><span data-stu-id="b548b-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="b548b-175">Windows :</span><span class="sxs-lookup"><span data-stu-id="b548b-175">Windows:</span></span>

1.  <span data-ttu-id="b548b-176">Cliquez avec le bouton droit sur l’icône **Microsoft teams** dans votre barre d’état système, sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="b548b-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="b548b-177">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="b548b-177">Mac OsX:</span></span>

1.  <span data-ttu-id="b548b-178">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="b548b-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="b548b-179">\*</span><span class="sxs-lookup"><span data-stu-id="b548b-179">Linux:</span></span>

1.  <span data-ttu-id="b548b-180">Cliquez sur l’icône **Microsoft teams** dans votre barre d’état système, puis sélectionnez **obtenir les journaux**</span><span class="sxs-lookup"><span data-stu-id="b548b-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="b548b-181">Client</span><span class="sxs-lookup"><span data-stu-id="b548b-181">Client</span></span> |<span data-ttu-id="b548b-182">Lieu</span><span class="sxs-lookup"><span data-stu-id="b548b-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b548b-183">Windows</span><span class="sxs-lookup"><span data-stu-id="b548b-183">Windows</span></span>     |<span data-ttu-id="b548b-184">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="b548b-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="b548b-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b548b-185">Mac OSX</span></span>     |<span data-ttu-id="b548b-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b548b-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="b548b-187">Linux</span><span class="sxs-lookup"><span data-stu-id="b548b-187">Linux</span></span>       |<span data-ttu-id="b548b-188">~/.config/Microsoft/Microsoft équipes/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b548b-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |
