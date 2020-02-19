---
title: Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef2900d66796ec261e7abd9c8c6d910eb6c0e81
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="4384c-102">Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4384c-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4384c-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4384c-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4384c-104">Pour capturer les journaux de suivi à l’aide du service de journalisation centralisée, vous devez émettre une commande pour commencer la journalisation sur un ou plusieurs ordinateurs et pools.</span><span class="sxs-lookup"><span data-stu-id="4384c-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="4384c-105">Vous pouvez également émettre des paramètres qui définissent les ordinateurs ou pools, les scénarios à exécuter (par exemple, AlwaysOn, un autre scénario prédéfini ou un scénario que vous avez créé), les composants Lync Server (par exemple, S4, SipStack) à suivre.</span><span class="sxs-lookup"><span data-stu-id="4384c-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="4384c-106">Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat.</span><span class="sxs-lookup"><span data-stu-id="4384c-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="4384c-107">Dans le service de journalisation centralisée, un scénario est le concept de l’ouverture de session basée sur une collection de composants serveur, de niveaux de journalisation et d’indicateurs, ce qui est bien plus efficace et utile que la définition de ces éléments sur une base par serveur.</span><span class="sxs-lookup"><span data-stu-id="4384c-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="4384c-108">Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="4384c-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="4384c-p103">Le scénario par défaut est appelé **AlwaysOn**. Comme son nom l’indique, AlwaysOn est constamment exécuté. Le scénario AlwaysOn recueille des informations de niveau de journalisation Info (notez que le niveau de journalisation Info inclut les messages d’erreur fatale, d’erreur et d’avertissement en plus des messages Info) pour de nombreux composants serveur parmi les plus courants. AlwaysOn recueille des informations avant, pendant et après qu’un problème se produit. Ce comportement est considérablement différent du comportement type des anciens outils de journalisation tels qu’OCSLogger. Vous deviez en effet exécuter OCSLogger après qu’un problème se soit produit, ce qui rendait la résolution plus difficile, car les données dont vous disposiez étaient réactives et non proactives. Si AlwaysOn ne contient pas les informations que vous recherchez concernant le composant à l’origine du problème et vous indiquant la marche à suivre pour le résoudre (ce qui ne risque pas d’être le cas étant donnée les informations fournies par AlwaysOn), il fournit un niveau raisonnable d’informations pour déterminer les autres actions que vous devez effectuer, comme créer un nouveau scénario, recueillir d’autres informations, exécuter une autre recherche pour obtenir des détails plus précis, etc.</span><span class="sxs-lookup"><span data-stu-id="4384c-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="4384c-116">Le service de journalisation centralisée offre deux méthodes d’émission de commandes.</span><span class="sxs-lookup"><span data-stu-id="4384c-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="4384c-117">Un certain nombre de sujets ont été axés sur l’utilisation de Windows PowerShell via Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4384c-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="4384c-118">La possibilité d’utiliser un certain nombre de configurations et de commandes complexes favorise Windows PowerShell pour l’utilisation du service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="4384c-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="4384c-119">Étant donné que Windows PowerShell via Lync Server Management Shell est presque omniprésent pour toutes les fonctions dans Lync Server, seules les commandes Windows PowerShell sont abordées.</span><span class="sxs-lookup"><span data-stu-id="4384c-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4384c-120">Si vous décidez d’utiliser le jeu de commandes limité disponible à partir de la ligne de commande, vous pouvez obtenir de l’aide <CODE>ClsController.exe</CODE>sur CLSController. exe en tapant.</span><span class="sxs-lookup"><span data-stu-id="4384c-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="4384c-121">Par défaut, <STRONG>ClsController. exe</STRONG> est installé dans le répertoire C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="4384c-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="4384c-122">Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes de base</span><span class="sxs-lookup"><span data-stu-id="4384c-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="4384c-123">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4384c-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4384c-124">Démarrez un scénario de journalisation avec le service de journalisation centralisée en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4384c-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="4384c-125">Par exemple, pour lancer le scénario **AlwaysOn**, tapez :</span><span class="sxs-lookup"><span data-stu-id="4384c-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4384c-126">Le scénario AlwaysOn n’a pas de durée par défaut.</span><span class="sxs-lookup"><span data-stu-id="4384c-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="4384c-127">Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4384c-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="4384c-128">Pour plus d’informations, voir <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="4384c-128">For details, see <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="4384c-129">Pour tous les autres scénarios, la durée par défaut est de 4 heures.</span><span class="sxs-lookup"><span data-stu-id="4384c-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="4384c-130">Appuyez sur Entrée pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="4384c-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4384c-131">L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peut prendre quelques instants (de 30 à 60 secondes).</span><span class="sxs-lookup"><span data-stu-id="4384c-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="4384c-132">![Exécution de Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Exécution de Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="4384c-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="4384c-133">Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging**, avec le nom de ce scénario à exécuter (par exemple, le scénario **Authentification**), comme suit :</span><span class="sxs-lookup"><span data-stu-id="4384c-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="4384c-134">Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment.</span><span class="sxs-lookup"><span data-stu-id="4384c-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="4384c-135">Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux.</span><span class="sxs-lookup"><span data-stu-id="4384c-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="4384c-136">Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="4384c-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="4384c-137">Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools.</span><span class="sxs-lookup"><span data-stu-id="4384c-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="4384c-138">Pour plus d’informations sur la gestion des scénarios en cours d’exécution, voir <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation de stop pour le service de journalisation centralisée dans Lync Server 2013</A> et <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="4384c-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="4384c-139">Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées</span><span class="sxs-lookup"><span data-stu-id="4384c-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="4384c-140">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4384c-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4384c-141">Il existe d’autres paramètres pour gérer les commandes de journalisation.</span><span class="sxs-lookup"><span data-stu-id="4384c-141">Additional parameters are available to manage the logging commands.</span></span> <span data-ttu-id="4384c-142">Vous pouvez utiliser –Duration pour définir la durée d’exécution d’un scénario.</span><span class="sxs-lookup"><span data-stu-id="4384c-142">You can use –Duration to adjust the length of time for the scenario to run.</span></span> <span data-ttu-id="4384c-143">Vous pouvez également définir –Computers, une liste de noms complets d’ordinateurs séparés par une virgule ou –Pools, une liste de noms complets de pools séparés par une virgule sur lesquels vous souhaitez exécuter la journalisation.</span><span class="sxs-lookup"><span data-stu-id="4384c-143">You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="4384c-144">Vous démarrez une session de journalisation pour le scénario *UserReplicator* sur le pool « pool01.contoso.net ».</span><span class="sxs-lookup"><span data-stu-id="4384c-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="4384c-145">Vous définissez également la durée de la session de journalisation à 8 heures.</span><span class="sxs-lookup"><span data-stu-id="4384c-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="4384c-146">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="4384c-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="4384c-147">L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="4384c-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="4384c-148">![Exécution de Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Exécution de Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="4384c-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="4384c-149">Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés.</span><span class="sxs-lookup"><span data-stu-id="4384c-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4384c-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4384c-150">See Also</span></span>


[<span data-ttu-id="4384c-151">Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4384c-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

