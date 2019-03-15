---
title: Utiliser les fichiers journaux pour le dépannage de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Découvrez les journaux de débogage, des médias et du bureau générés par Microsoft Teams, où les trouver et comment ils peuvent vous assister dans vos opérations de dépannage.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 018247ba7f5f7ac088226bd505f6bf11737533c2
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640705"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="b83d8-103">Utiliser les fichiers journaux pour le dépannage de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b83d8-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="b83d8-104">Il existe trois types de fichiers journaux générés par le client et qui peuvent être utilisés pour le dépannage de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b83d8-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="b83d8-105">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="b83d8-105">Debug logs</span></span>

-   <span data-ttu-id="b83d8-106">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="b83d8-106">Media logs</span></span>

-   <span data-ttu-id="b83d8-107">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="b83d8-107">Desktop logs</span></span>

<span data-ttu-id="b83d8-p101">Lors de la création d'une demande de support auprès du Support Microsoft, l'ingénieur de support sollicitera les journaux de débogage. Préparer ces journaux avant de créer la demande de support permet à Microsoft de résoudre rapidement le problème. Les journaux des médias ou du bureau sont requis uniquement sur demande de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b83d8-p101">When creating a support request with Microsoft Support, the support engineer will require the debug logs. Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem. Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="b83d8-p102">Le tableau suivant présente les différents clients et les journaux associés. Les fichiers journaux sont stockés dans des emplacements spécifiques au client et au système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="b83d8-p102">The following table outlines the various clients, and their associated logs. Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="b83d8-113">Client</span><span class="sxs-lookup"><span data-stu-id="b83d8-113">Client</span></span> |<span data-ttu-id="b83d8-114">Debug</span><span class="sxs-lookup"><span data-stu-id="b83d8-114">Debug</span></span>|<span data-ttu-id="b83d8-115">Bureau</span><span class="sxs-lookup"><span data-stu-id="b83d8-115">Desktop</span></span>|<span data-ttu-id="b83d8-116">Media</span><span class="sxs-lookup"><span data-stu-id="b83d8-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="b83d8-117">Web</span><span class="sxs-lookup"><span data-stu-id="b83d8-117">Web</span></span>    |<span data-ttu-id="b83d8-118">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-118">X</span></span>         |-         |-         |
|<span data-ttu-id="b83d8-119">Windows</span><span class="sxs-lookup"><span data-stu-id="b83d8-119">Windows</span></span>     |<span data-ttu-id="b83d8-120">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-120">X</span></span>         |<span data-ttu-id="b83d8-121">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-121">X</span></span>         |<span data-ttu-id="b83d8-122">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-122">X</span></span>         |
|<span data-ttu-id="b83d8-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b83d8-123">Mac OSX</span></span>     |<span data-ttu-id="b83d8-124">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-124">X</span></span>         |<span data-ttu-id="b83d8-125">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-125">X</span></span>         |<span data-ttu-id="b83d8-126">X</span><span class="sxs-lookup"><span data-stu-id="b83d8-126">X</span></span>         |
|<span data-ttu-id="b83d8-127">iOS</span><span class="sxs-lookup"><span data-stu-id="b83d8-127">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="b83d8-128">Android</span><span class="sxs-lookup"><span data-stu-id="b83d8-128">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="b83d8-129">Pour obtenir la liste complète des systèmes d’exploitation et navigateurs pris en charge, consultez la rubrique [Obtenir des clients pour Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="b83d8-129">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="b83d8-130">Journaux de débogage</span><span class="sxs-lookup"><span data-stu-id="b83d8-130">Debug logs</span></span>
---------------------------

<span data-ttu-id="b83d8-131">Il s’agit des journaux les plus courants. Ils sont requis pour tous les cas de support Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b83d8-131">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="b83d8-132">Les journaux de débogage sont générés par les clients de bureau Windows et Mac, ainsi que par les clients reposant sur un navigateur.</span><span class="sxs-lookup"><span data-stu-id="b83d8-132">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="b83d8-133">Il s’agit de fichiers texte qui sont lus de bas en haut.</span><span class="sxs-lookup"><span data-stu-id="b83d8-133">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="b83d8-134">Ils peuvent être lus à l’aide de n’importe quel éditeur de texte. En outre, des journaux sont créés lors de la connexion au client.</span><span class="sxs-lookup"><span data-stu-id="b83d8-134">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="b83d8-135">Les journaux de débogage contiennent les flux de données suivants :</span><span class="sxs-lookup"><span data-stu-id="b83d8-135">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="b83d8-136">Connexion</span><span class="sxs-lookup"><span data-stu-id="b83d8-136">Login</span></span>

-   <span data-ttu-id="b83d8-137">Demandes de connexion à des services de niveau intermédiaire</span><span class="sxs-lookup"><span data-stu-id="b83d8-137">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="b83d8-138">Appel/conversation</span><span class="sxs-lookup"><span data-stu-id="b83d8-138">Call/conversation</span></span>

<span data-ttu-id="b83d8-139">Les journaux de débogage sont générés à l'aide des méthodes propres aux systèmes d'exploitation suivantes :</span><span class="sxs-lookup"><span data-stu-id="b83d8-139">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="b83d8-140">Windows :</span><span class="sxs-lookup"><span data-stu-id="b83d8-140">Windows:</span></span>

      <span data-ttu-id="b83d8-141">Raccourci clavier : Ctrl + Alt + Maj + 1</span><span class="sxs-lookup"><span data-stu-id="b83d8-141">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="b83d8-142">Mac OSX :</span><span class="sxs-lookup"><span data-stu-id="b83d8-142">Mac OSX:</span></span>

      <span data-ttu-id="b83d8-143">Raccourci clavier : Option + Commande + Maj t+1</span><span class="sxs-lookup"><span data-stu-id="b83d8-143">Keyboard shortcut: Option + Command + Shift+1</span></span>

<span data-ttu-id="b83d8-144">Les journaux de débogage sont automatiquement téléchargés dans les dossiers suivants.</span><span class="sxs-lookup"><span data-stu-id="b83d8-144">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="b83d8-145">Windows : %userprofile%\\Téléchargements</span><span class="sxs-lookup"><span data-stu-id="b83d8-145">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="b83d8-146">Mac OSX : Téléchargements</span><span class="sxs-lookup"><span data-stu-id="b83d8-146">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="b83d8-147">Navigateur : Vous serez invité à enregistrer le journal de débogage dans l'emplacement d'enregistrement par défaut.</span><span class="sxs-lookup"><span data-stu-id="b83d8-147">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="b83d8-148">Journaux des médias</span><span class="sxs-lookup"><span data-stu-id="b83d8-148">Media Logs</span></span>
---------------------------

<span data-ttu-id="b83d8-p104">Les journaux des médias contiennent des données de diagnostic sur les appels audio, vidéo et le partage d'écran. Ils sont requis pour les cas de support uniquement sur demande et seul Microsoft peut les lire. Le tableau suivant présente l'emplacement des journaux.</span><span class="sxs-lookup"><span data-stu-id="b83d8-p104">Media logs contain diagnostic data about audio, video and screen sharing. They are required for support cases only upon request and can only be inspected by Microsoft. The following table outlines the log location.</span></span>


|<span data-ttu-id="b83d8-152">Client</span><span class="sxs-lookup"><span data-stu-id="b83d8-152">Client</span></span> |<span data-ttu-id="b83d8-153">Lieu</span><span class="sxs-lookup"><span data-stu-id="b83d8-153">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b83d8-154">Windows</span><span class="sxs-lookup"><span data-stu-id="b83d8-154">Windows</span></span>     |<span data-ttu-id="b83d8-155">%appdata%\Microsoft\Teams\media-stack\*.etl</span><span class="sxs-lookup"><span data-stu-id="b83d8-155">%appdata%\Microsoft\Teams\media-stack\*.etl</span></span>         |
|<span data-ttu-id="b83d8-156">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b83d8-156">Mac OSX</span></span>     |<span data-ttu-id="b83d8-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span><span class="sxs-lookup"><span data-stu-id="b83d8-157">~/Library/Application Support/Microsoft/Teams/media-stack\*.blog</span></span>         |


<a name="desktop-logs"></a><span data-ttu-id="b83d8-158">Journaux du bureau</span><span class="sxs-lookup"><span data-stu-id="b83d8-158">Desktop logs</span></span>
---------------------

<span data-ttu-id="b83d8-p105">Les journaux du bureau, également appelés journaux de programme d'amorçage, contiennent des données d'événements survenant entre le client de bureau et le navigateur. À l'instar des journaux des médias, ces journaux sont requis uniquement sur demande de Microsoft. Il s'agit de journaux texte qui peuvent être affichés à l'aide d'un éditeur de texte et lus de haut en bas.</span><span class="sxs-lookup"><span data-stu-id="b83d8-p105">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser. Like media logs, these logs are only needed if requested by Microsoft. The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="b83d8-162">Windows :</span><span class="sxs-lookup"><span data-stu-id="b83d8-162">Windows:</span></span>

  1.  <span data-ttu-id="b83d8-163">Cliquez avec le bouton droit de la souris sur l’**icône Microsoft Teams dans la** barre d’état de votre application, puis sélectionnez **Obtenir les journaux**.</span><span class="sxs-lookup"><span data-stu-id="b83d8-163">Right-click **the Microsoft Teams icon in** your application tray, select **Get Logs**</span></span>

  2.  <span data-ttu-id="b83d8-164">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="b83d8-164">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="b83d8-165">Mac OsX :</span><span class="sxs-lookup"><span data-stu-id="b83d8-165">Mac OsX:</span></span>

1.  <span data-ttu-id="b83d8-166">Sélectionnez **Obtenir les journaux** dans le menu déroulant **Aide**.</span><span class="sxs-lookup"><span data-stu-id="b83d8-166">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

|<span data-ttu-id="b83d8-167">Client</span><span class="sxs-lookup"><span data-stu-id="b83d8-167">Client</span></span> |<span data-ttu-id="b83d8-168">Lieu</span><span class="sxs-lookup"><span data-stu-id="b83d8-168">Location</span></span> |
|---------|---------|
|<span data-ttu-id="b83d8-169">Windows</span><span class="sxs-lookup"><span data-stu-id="b83d8-169">Windows</span></span>     |<span data-ttu-id="b83d8-170">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="b83d8-170">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="b83d8-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="b83d8-171">Mac OSX</span></span>     |<span data-ttu-id="b83d8-172">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="b83d8-172">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
