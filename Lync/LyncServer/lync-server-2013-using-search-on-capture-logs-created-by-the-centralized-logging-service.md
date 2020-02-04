---
title: Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edfc176934479aef04d6850a8ebbae3b38a553a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="a1ffe-102">Utilisation de la recherche dans les journaux de capture créés par le service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1ffe-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1ffe-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="a1ffe-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="a1ffe-104">Les fonctionnalités de recherche du service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="a1ffe-105">Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="a1ffe-p101">Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur. Vous effectuez vos recherches sur les mêmes journaux et n’avez pas besoin d’exécuter une autre session de journalisation lorsque vos critères de recherche changent.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="a1ffe-p102">Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="a1ffe-p103">Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="a1ffe-116">Après chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers cache gérés par CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="a1ffe-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="a1ffe-117">Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="a1ffe-118">Pour tirer le meilleur parti du service de journalisation centralisé, vous devez comprendre comment configurer la recherche pour renvoyer uniquement les messages de suivi des journaux d’ordinateur et de pool pertinents pour le problème que vous recherchez.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="a1ffe-119">aspects</span><span class="sxs-lookup"><span data-stu-id="a1ffe-119">issues</span></span>

<span data-ttu-id="a1ffe-120">Pour exécuter les fonctions de recherche du service de journalisation centralisées à l’aide de Lync Server Management Shell, vous devez être membre du groupe de sécurité CsAdministrator ou CsServerAdministrator de contrôle d’accès basé sur les rôles (RBAC) ou d’un rôle RBAC personnalisé contenant l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="a1ffe-121">Pour renvoyer la liste de tous les rôles RBAC auxquels cette cmdlet a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="a1ffe-122">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="a1ffe-123">Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="a1ffe-124">Pour effectuer une recherche de base à l’aide du service de journalisation centralisé</span><span class="sxs-lookup"><span data-stu-id="a1ffe-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="a1ffe-125">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1ffe-126">Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a1ffe-127">Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="a1ffe-128">Si vous voulez enregistrer les résultats de la recherche dans un fichier, utilisez la &lt;chaîne-OutputFilePath de nom&gt;complet.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="a1ffe-129">Pour définir le paramètre –OutputFilePath, indiquez un chemin d’accès et un nom de fichier dans un format de chaîne entouré de guillemets (par exemple : C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="a1ffe-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="a1ffe-130">Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="a1ffe-131">Les résultats sont ajoutés et ne sont pas remplacés.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="a1ffe-132">Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="a1ffe-133">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="a1ffe-134">Pour effectuer une recherche de base sur un pool ou un ordinateur à l’aide du service de journalisation centralisé</span><span class="sxs-lookup"><span data-stu-id="a1ffe-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="a1ffe-135">Pour limiter la recherche à un pool ou à un ordinateur en particulier, utilisez le paramètre –Computers en définissant l’ordinateur par un nom complet, entouré de guillemets et séparé par une virgule, comme suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="a1ffe-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="a1ffe-137">Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="a1ffe-138">Pour effectuer une recherche dans un pool entier au lieu d’un seul ordinateur, modifiez le paramètre –Computers en –Pools, supprimez le nom de l’ordinateur et remplacez-le par le ou les pools entourés de guillemets et séparés par des virgules.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="a1ffe-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="a1ffe-140">Lors de l’utilisation des commandes de recherche, il peut s’agir de n’importe quel pool dans votre déploiement (par exemple, des pools frontaux, des pools de serveurs de chat permanent ou d’autres personnes définies comme pools dans votre déploiement).</span><span class="sxs-lookup"><span data-stu-id="a1ffe-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="a1ffe-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="a1ffe-142">Pour exécuter une recherche à l’aide des paramètres d’heure</span><span class="sxs-lookup"><span data-stu-id="a1ffe-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="a1ffe-143">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1ffe-144">Par défaut, l’heure de début des paramètres spécifiques d’une recherche est 30 minutes avant le moment où vous commencez la recherche.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-144">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search.</span></span> <span data-ttu-id="a1ffe-145">En d’autres termes, si vous lancez votre recherche sur 4:00:00 PM, la recherche effectue une recherche dans les journaux pour les ordinateurs et les groupes que vous définissez à partir de 3:30:00 PM jusqu’à 4:00:00 PM.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-145">In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM.</span></span> <span data-ttu-id="a1ffe-146">Si vous devez effectuer une recherche 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre –StartTime et définissez la date et l’heure de manière à indiquer l’heure à laquelle vous souhaitez que la recherche débute.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-146">If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="a1ffe-147">Par exemple, en utilisant –StartTime et –EndTime pour définir une plage horaire et de dates, vous pouvez définir une recherche entre 8 h 00 00 et 9 h 00 00 le 20/11/2012 sur votre pool.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="a1ffe-148">Vous pouvez définir le chemin de sortie pour écrire les résultats dans un fichier nommé c\\: logfile. txt comme suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="a1ffe-149">La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ».</span><span class="sxs-lookup"><span data-stu-id="a1ffe-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="a1ffe-150">"La commande analyse la chaîne et utilise les valeurs appropriées pour la date et l’heure.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="a1ffe-p111">Si vous souhaitez extraire les journaux à partir de 11 h 00 00 le 20/11/2012, définissez l’heure de début (paramètre –StartTime). La plage horaire par défaut pour la recherche est de 30 minutes sauf si vous définissez une heure de fin (paramètre –EndTime) spécifique. La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p111">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime. The default time range for the search is 30 minutes unless you define a specific –EndTime. The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="a1ffe-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="a1ffe-p112">Pour réaliser une recherche sur des journaux dans une période donnée, définissez une heure de début (paramètre –StartTime) et une heure de fin (paramètre –EndTime). Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p112">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime. You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="a1ffe-157">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="a1ffe-158">Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance</span><span class="sxs-lookup"><span data-stu-id="a1ffe-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="a1ffe-159">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1ffe-160">Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="a1ffe-161">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="a1ffe-162">La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.</span><span class="sxs-lookup"><span data-stu-id="a1ffe-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="a1ffe-163">Pour limiter la recherche avec les mêmes composants uniquement au pool frontal nommé pool01.contoso.net, tapez :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="a1ffe-p113">La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis. Vous pouvez modifier ce comportement en spécifiant le paramètre **–MatchAll**. Pour ce faire, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p113">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters. You can change this behavior by specifying the **–MatchAll** parameter. To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="a1ffe-p114">Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :</span><span class="sxs-lookup"><span data-stu-id="a1ffe-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

