---
title: Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 'Résumé : Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.'
ms.openlocfilehash: b1f049260eff7524e5a728852b3dcd99526d8742
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217466"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="d738a-103">Recherche dans les journaux de capture créés par le service de journalisation centralisée dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d738a-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d738a-104">**Résumé :** Découvrez comment rechercher et lire des journaux de Service de journalisation centralisée dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d738a-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d738a-105">Les fonctionnalités de recherche dans le Service de journalisation centralisée sont utiles et puissantes pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="d738a-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="d738a-106">Vos recherches et les résultats sont exécutés sur un seul ordinateur, un pool, un site ou une étendue globale, en fonction des critères que vous définissez.</span><span class="sxs-lookup"><span data-stu-id="d738a-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="d738a-107">Vos recherches peuvent être larges à l’origine, puis s’affiner sur des critères plus ciblés, tels que l’heure, le composant ou l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="d738a-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="d738a-108">Vous effectuer une recherche sur les mêmes journaux et que vous n’avez pas besoin exécuter à nouveau une session de journalisation lorsque les critères de recherche est modifié.</span><span class="sxs-lookup"><span data-stu-id="d738a-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="d738a-p102">Les résultats de votre recherche sont issus de tous les ordinateurs et pools de l’étendue, collectés et regroupés en un seul fichier de sortie qui représente tous les résultats des critères de recherche (limités aux scénarios qui ont été exécutés et aux données capturées par les scénarios). Vous utilisez des outils familiers, tels que **Snooper** ou **Notepad**, pour lire le fichier de sortie et les messages de suivi de tout votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d738a-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="d738a-p103">Le CLSAgent sur chaque ordinateur individuel crée les journaux en fonction du ou des scénarios (deux scénarios par ordinateur peuvent s’exécuter en même temps). Les journaux, ainsi que leurs fichiers d’index et de cache associés, sont gérés par le CLSAgent. Lorsque vous définissez et exécutez une recherche, la commande de recherche indique au CLSAgent quelles informations extraire. Le CLSAgent exécute la requête sur les fichiers journaux, les fichiers de cache et les fichiers d’index et renvoie les résultats de la recherche au CLSController. Le CLSController reçoit les résultats de la recherche en provenance de tous les ordinateurs et pools dans l’étendue de la recherche. Le CLSController regroupe ensuite (combine) les journaux et les classe en fonction de l’écart de temps : l’entrée la plus ancienne en premier et l’entrée la plus récente en dernier.</span><span class="sxs-lookup"><span data-stu-id="d738a-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="d738a-117">Après chaque recherche, l’applet de commande **Sync-CsClsLogging** est exécutée et vide le cache utilisé par les recherches (à ne pas confondre avec les fichiers cache gérés par CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="d738a-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="d738a-118">Le fait de vider le cache permet de garantir que la prochaine opération de recherche bénéficie d’une mémoire tampon nette de capture du fichier journal et du fichier de suivi sur le CLSController.</span><span class="sxs-lookup"><span data-stu-id="d738a-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="d738a-119">Pour tirer le meilleur parti du service de journalisation centralisée, vous avez besoin d’une bonne compréhension de la façon de configurer la recherche pour retourner uniquement les messages de suivi à partir des journaux d’ordinateur et le pool qui sont pertinents pour le problème que vous effectuez une recherche.</span><span class="sxs-lookup"><span data-stu-id="d738a-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="d738a-120">problèmes</span><span class="sxs-lookup"><span data-stu-id="d738a-120">issues</span></span>
  
<span data-ttu-id="d738a-121">Pour exécuter les fonctions de recherche du Service de journalisation centralisée à l’aide de la Skype pour Business Server Management Shell, vous devez être un membre de la CsAdministrator ou les groupes de sécurité CsServerAdministrator accès basé sur un rôle RBAC (contrôle) ou un rôle RBAC personnalisé qui contient une de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="d738a-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="d738a-122">Pour retourner une liste de tous les rôles RBAC cette applet de commande a été assigné à (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de la Skype Business Server Management Shell ou de l’invite de Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d738a-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="d738a-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="d738a-124">Le reste de cette rubrique se concentre sur la définition d’une recherche en vue d’optimiser la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="d738a-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="d738a-125">Pour exécuter une recherche de base en utilisant le Service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="d738a-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="d738a-126">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d738a-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d738a-127">Assurez-vous que le scénario AlwaysOn s’exécute dans votre déploiement au niveau de l’étendue globale, puis tapez ce qui suit dans une invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="d738a-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="d738a-128">Par défaut, Search-CsClsLogging envoie les résultats de la recherche à la console.</span><span class="sxs-lookup"><span data-stu-id="d738a-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="d738a-129">Si vous souhaitez enregistrer les résultats de recherche dans un fichier, utilisez - OutputFilePath _ \<chemin d’accès complet chaîne\>_.</span><span class="sxs-lookup"><span data-stu-id="d738a-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="d738a-130">Pour définir le paramètre - OutputFilePath, indiquez un chemin d’accès et un nom de fichier dans le cadre du paramètre dans un format de chaîne entouré guillemets (par exemple, C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="d738a-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="d738a-131">Dans cet exemple, vous devez vous assurer que le répertoire C:\LogFiles existe et que vous disposez des autorisations en lecture et en écriture (autorisation NTSF Modifier) sur le dossier.</span><span class="sxs-lookup"><span data-stu-id="d738a-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="d738a-132">Les résultats sont ajoutés et ne sont pas remplacés.</span><span class="sxs-lookup"><span data-stu-id="d738a-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="d738a-133">Si vous avez besoin de fichiers séparés, définissez un nom de fichier différent pour chaque recherche.</span><span class="sxs-lookup"><span data-stu-id="d738a-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="d738a-134">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="d738a-135">Pour exécuter une recherche de base sur un ordinateur ou un pool en utilisant le Service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="d738a-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="d738a-136">Pour limiter la recherche à un ordinateur ou un pool spécifique, utilisez-paramètre ordinateurs avec l’ordinateur défini par un nom complet de l’ordinateur, placé entre guillemets et séparés par une virgule, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="d738a-137">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="d738a-138">Pour rechercher plusieurs ordinateurs, tapez le nom de plusieurs ordinateurs en les entourant de guillemets et en les séparant par une virgule, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="d738a-139">Si vous avez besoin rechercher un pool entier au lieu d’un seul ordinateur, modifiez l’ordinateurs paramètre - à - Pools, supprimer le nom d’ordinateur et remplacer avec le pool ou les pools de guillemets séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="d738a-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="d738a-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="d738a-141">Lorsque vous utilisez les commandes de recherche, les pools peuvent être n’importe quel pool dans votre déploiement, telles que les pools frontaux, pools de serveurs Edge, les pools de serveurs de conversation permanente ou d’autres personnes qui sont définis comme un pool de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="d738a-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="d738a-142">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="d738a-143">Pour exécuter une recherche à l’aide des paramètres d’heure</span><span class="sxs-lookup"><span data-stu-id="d738a-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="d738a-144">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d738a-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d738a-145">Par défaut, l’heure de début pour les paramètres temporels d’une recherche est définie sur 25 minutes avant les cinq minutes après l’heure où vous lancez la recherche.</span><span class="sxs-lookup"><span data-stu-id="d738a-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="d738a-146">En d’autres mots, si nous effectuons une recherche à 16 h 00 00, la recherche s’étendra alors de 15 h 35 00 à 16 h 05 00.</span><span class="sxs-lookup"><span data-stu-id="d738a-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="d738a-147">Si vous avez besoin rechercher les 60 minutes ou 3 heures avant l’heure actuelle, utilisez le paramètre - StartTime et définir la chaîne de date et heure pour indiquer l’heure à que laquelle démarrer la recherche.</span><span class="sxs-lookup"><span data-stu-id="d738a-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="d738a-148">Par exemple, à l’aide de - StartTime et EndTime - pour définir une plage de date et heure, vous pouvez définir une recherche de 8 à 9 h 00 sur 20/11/2012 sur votre pool.</span><span class="sxs-lookup"><span data-stu-id="d738a-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="d738a-149">Vous pouvez configurer le chemin d’accès de sortie de manière à écrire les résultats dans un fichier nommé c:\logfile.txt comme suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="d738a-150">La date et l’heure que vous définissez peut s’appeler « date heure » ou « heure date ».</span><span class="sxs-lookup"><span data-stu-id="d738a-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="d738a-151">« La commande analyser la chaîne et utiliser les valeurs appropriées pour la date et heure et vos paramètres régionaux et de la culture sur l’ordinateur que vous exécutez la cmdlet à partir de.</span><span class="sxs-lookup"><span data-stu-id="d738a-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="d738a-152">Si vous souhaitez récupérer les journaux commençant à 11:00:00 AM sur 20/11/2012, vous définissez l’heure de début.</span><span class="sxs-lookup"><span data-stu-id="d738a-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="d738a-153">La plage de temps par défaut pour la recherche est de 30 minutes, sauf si vous définissez une heure de fin - spécifique.</span><span class="sxs-lookup"><span data-stu-id="d738a-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="d738a-154">La recherche obtenue renverra les journaux des ordinateurs ou pools définis entre 11 h 00 00 et 11 h 30 00.</span><span class="sxs-lookup"><span data-stu-id="d738a-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="d738a-155">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="d738a-156">Pour effectuer une recherche de journaux au sein d’une période spécifique, définissez une heure de début - et - EndTime.</span><span class="sxs-lookup"><span data-stu-id="d738a-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="d738a-157">Les journaux entre 13 h 00 et 14 h 45 doivent être présents sur l’ordinateur edge01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="d738a-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="d738a-158">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="d738a-159">Pour exécuter une recherche avancée à l’aide d’autres critères et options de correspondance</span><span class="sxs-lookup"><span data-stu-id="d738a-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="d738a-160">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d738a-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d738a-161">Pour exécuter une commande visant à collecter les suivis pour des composants en particulier, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="d738a-162">Exemple :</span><span class="sxs-lookup"><span data-stu-id="d738a-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="d738a-163">La recherche obtenue renvoie toutes les entrées de journaux qui possèdent des composants de suivi pour SIPStack, S4 et UserServices sur tous les ordinateurs et pools de votre déploiement au cours des 30 dernières minutes.</span><span class="sxs-lookup"><span data-stu-id="d738a-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="d738a-164">Pour limiter la recherche avec les mêmes composants à seulement votre pool frontal nommé pool01.contoso.net, tapez :</span><span class="sxs-lookup"><span data-stu-id="d738a-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="d738a-165">La logique de recherche par défaut pour les commandes comprenant plusieurs paramètres utilise l’opérateur logique OR avec chacun des paramètres définis.</span><span class="sxs-lookup"><span data-stu-id="d738a-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="d738a-166">Vous pouvez modifier ce comportement en spécifiant le paramètre **- MatchAll** .</span><span class="sxs-lookup"><span data-stu-id="d738a-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="d738a-167">Pour ce faire, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="d738a-p114">Si vos scénarios sont définis de manière à s’exécuter constamment (par exemple AlwaysOn) ou si vous avez défini un scénario à long terme, les journaux peuvent s’étendre de l’ordinateur local au partage de fichiers. Pour définir le partage de fichiers, utilisez le paramètre CacheFileNetworkFolder à l’aide de New-CsClsConfiguration pour créer une nouvelle configuration ou modifiez une configuration existante avec Set-CsClsConfiguration. Si vous ne souhaitez pas que la recherche englobe le partage de fichiers dans la collection des journaux à parcourir, utilisez le paramètre SkipNetworkLogs comme suit :</span><span class="sxs-lookup"><span data-stu-id="d738a-p114">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share. You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration. If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="d738a-171">Lire les journaux de capture à partir du Service de journalisation centralisée</span><span class="sxs-lookup"><span data-stu-id="d738a-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="d738a-172">Vous réalisez l’avantage réel du Service de journalisation centralisée après exécution de la recherche et que vous disposez d’un fichier que vous pouvez utiliser pour localiser un problème.</span><span class="sxs-lookup"><span data-stu-id="d738a-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="d738a-173">Il existe plusieurs méthodes que vous pouvez lire le fichier.</span><span class="sxs-lookup"><span data-stu-id="d738a-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="d738a-174">Le fichier de sortie est au format texte standard et vous pouvez utiliser Notepad.exe ou autres programmes qui vous permettra d’ouvrir et de lire un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="d738a-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="d738a-175">Pour les fichiers de grande taille et problèmes plus complexes, vous pouvez utiliser un outil tel que Snooper.exe est conçu pour lire et analyser la sortie d’enregistrement à partir du Service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="d738a-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="d738a-176">Snooper est inclus dans les outils de débogage qui sont disponibles en tant que téléchargement séparé.</span><span class="sxs-lookup"><span data-stu-id="d738a-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="d738a-177">Vous pouvez télécharger les outils de débogage ici : [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span><span class="sxs-lookup"><span data-stu-id="d738a-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="d738a-178">Lorsque vous installez les outils de débogage, les raccourcis et les éléments de menu ne sont pas créés.</span><span class="sxs-lookup"><span data-stu-id="d738a-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="d738a-179">Après avoir installé les outils de débogage, ouvrez l’Explorateur Windows, une fenêtre de ligne de commande ou Skype pour Business Server Management Shell et accédez au répertoire (emplacement par défaut) C:\Program Files\Skype pour Business Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="d738a-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="d738a-180">Double-cliquez sur Snooper.exe ou tapez Snooper.exe, puis appuyez sur entrée si vous utilisez la ligne de commande ou Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d738a-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d738a-181">Cette rubrique n’a pas pour objectif de détailler et de discuter des techniques de résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="d738a-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="d738a-182">Le dépannage et les processus associés constituent un sujet complexe.</span><span class="sxs-lookup"><span data-stu-id="d738a-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="d738a-183">Pour plus d’informations sur les notions élémentaires de dépannage et de résolution des problèmes de charges de travail spécifiques, consultez le Kit de ressources de Microsoft Lync Server 2010 à [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span><span class="sxs-lookup"><span data-stu-id="d738a-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="d738a-184">Les processus et procédures toujours s’appliquent à Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d738a-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="d738a-185">Pour ouvrir un fichier journal dans Snooper</span><span class="sxs-lookup"><span data-stu-id="d738a-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="d738a-p117">Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="d738a-p117">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="d738a-188">Après l’installation des outils de débogage (LyncDebugTools.msi), définissez le répertoire sur l’emplacement de Snooper.exe à l’aide de l’Explorateur Windows ou à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="d738a-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="d738a-189">Par défaut, les outils de débogage sont situés dans C:\Program Files\Skype pour Business Server 2015\Debugging Tools.</span><span class="sxs-lookup"><span data-stu-id="d738a-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="d738a-190">Double-cliquez ou exécutez Snooper.exe.</span><span class="sxs-lookup"><span data-stu-id="d738a-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="d738a-191">Après avoir ouvert Snooper, cliquez avec le bouton droit sur **Fichier**, cliquez sur **Ouvrir un fichier**, recherchez vos fichiers journaux, sélectionnez un fichier dans la boîte de dialogue **Ouvrir**, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="d738a-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="d738a-192">Messages de **suivi** du fichier journal sont affichés dans le **suivi** de l' onglet, cliquez sur l’onglet **Messages** pour afficher le contenu du message des traces collectés.</span><span class="sxs-lookup"><span data-stu-id="d738a-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="d738a-193">Pour afficher un diagramme de flux des appels</span><span class="sxs-lookup"><span data-stu-id="d738a-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="d738a-p119">Pour utiliser Snooper pour ouvrir des fichiers journaux, vous devez disposer de l’accès en lecture à ces fichiers. Pour utiliser Snooper et accéder aux fichiers journaux, vous devez être membre du groupe de sécurité RBAC CsAdministrator ou CsServerAdministrator, ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="d738a-p119">To use Snooper and open log files, you need read access to the log files. To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="d738a-196">Ouvrez un fichier journal, cliquez sur l’onglet **Messages**, puis sélectionnez une conversation dans la vue des messages ou un composant de suivi dans l’onglet **Suivi**.</span><span class="sxs-lookup"><span data-stu-id="d738a-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="d738a-197">Cliquez sur **Flux des appels**.</span><span class="sxs-lookup"><span data-stu-id="d738a-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d738a-198">Si vous cliquez sur un message ou de suivi qui ne fait pas partie d’un flux d’appel, le diagramme n’apparaît pas et un message d’état apparaît en bas de Snooper indiquant « ce message n’est pas éligible pour callfow ».</span><span class="sxs-lookup"><span data-stu-id="d738a-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="d738a-199">Choisissez un autre message ou suivi et le flux d’appels s’affiche si le message ou le suivi fait partie d’un flux d’appels.</span><span class="sxs-lookup"><span data-stu-id="d738a-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="d738a-200">Parcourez les messages ou lignes de trace et vérifiez si le diagramme de flux des appels est mis à jour ou modifié pour afficher un nouveau diagramme.</span><span class="sxs-lookup"><span data-stu-id="d738a-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="d738a-201">Placez le curseur sur les éléments pour obtenir des informations sur les messages d’appel, les points de terminaison et les autres composants.</span><span class="sxs-lookup"><span data-stu-id="d738a-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
