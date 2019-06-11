---
title: Utiliser le service de connexion centralisé pour capturer les journaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5033b4a8dfd8121e2f0b5926623a55358188935e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a><span data-ttu-id="839d3-102">Utiliser démarrer pour le service de journalisation centralisé pour capturer les journaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="839d3-102">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="839d3-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="839d3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="839d3-104">Pour capturer les journaux de suivi à l’aide du service de journalisation centralisé, vous devez exécuter une commande pour commencer à vous connecter sur un ou plusieurs ordinateurs et pools.</span><span class="sxs-lookup"><span data-stu-id="839d3-104">To capture trace logs using the Centralized Logging Service, you issue a command to begin logging on one or more computers and pools.</span></span> <span data-ttu-id="839d3-105">Vous émettez également des paramètres qui définissent les ordinateurs ou les pools, scénarios d’exécution (par exemple, AlwaysOn, autre scénario prédéfinie ou scénario que vous avez créé), les composants serveur Lync (par exemple, S4, SipStack) à tracer.</span><span class="sxs-lookup"><span data-stu-id="839d3-105">You also issue parameters that define which computers or pools, what scenarios to run (for example, AlwaysOn, another predefined scenario, or a scenario you have created), what Lync Server components (for example, S4, SipStack) to trace.</span></span>

<span data-ttu-id="839d3-106">Pour obtenir les informations appropriées concernant un problème, vous devez utiliser le scénario adéquat.</span><span class="sxs-lookup"><span data-stu-id="839d3-106">To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem.</span></span> <span data-ttu-id="839d3-107">Dans le service de journalisation centralisé, un scénario est le concept d’activation de la journalisation en fonction d’une collection de composants serveur, de niveaux de connexion et d’indicateurs, qui est beaucoup plus efficace et utile que de définir ces éléments pour chaque serveur.</span><span class="sxs-lookup"><span data-stu-id="839d3-107">In the Centralized Logging Service, a scenario is the concept of turning logging on based on a collection of server components, logging levels, and flags, which is much more efficient and useful than having to define these elements on a per-server basis.</span></span> <span data-ttu-id="839d3-108">Vous définissez et spécifiez un scénario à exécuter et ce scénario est exécuté de la même manière sur tous les serveurs et pools de votre infrastructure.</span><span class="sxs-lookup"><span data-stu-id="839d3-108">You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.</span></span>

<span data-ttu-id="839d3-p103">Le scénario par défaut s’appelle **AlwaysOn**. Comme son nom l’indique, AlwaysOn a pour objectif d’exécuter le scénario de manière constante. Le scénario AlwaysOn collecte des informations (notez que le niveau de journalisation des messages Info comprend, en plus des messages Info, les messages Error, Fatal et Warning) concernant bon nombre des composants serveur les plus courants. AlwaysOn collecte des informations avant, pendant et après la survenue d’un problème, comportement totalement différent des précédents outils de journalisation, tels que OCSLogger. Auparavant, vous exécutiez OCSLogger une fois le problème survenu, ce qui compliquait davantage la résolution des erreurs, car les données dont vous disposiez étaient réactives, et non pas proactives. Si AlwaysOn ne contient pas les informations que vous cherchez pour identifier le composant qui pose problème et d’indiquer la procédure corrective appropriée (ce qui est peu probable, étant donné l’ampleur et la profondeur des fournisseurs dans AlwaysOn), il indiquera un niveau raisonnable d’informations permettant de déterminer les autres opérations requises, par exemple créer un scénario, collecter d’autres informations, lancer une recherche différente afin de collecter des informations plus détaillées, etc.</span><span class="sxs-lookup"><span data-stu-id="839d3-p103">The default scenario is called **AlwaysOn**. The intended purpose for AlwaysOn is to run the scenario constantly, as the name of the scenario implies. The AlwaysOn scenario collects Info level information (note that Info logging level includes Fatal, Error, and Warning in addition to Info messages) for many of the most common server components. AlwaysOn collects information before, during, and after a problem occurs. This differs dramatically from the typical behavior of previous logging tools such as OCSLogger. You ran OCSLogger after the problem had already occurred, making your troubleshooting efforts more difficult because the data that you have is reactive, not proactive. If AlwaysOn does not contain the information that you are looking for in order to point to the problem component and indicate a course of action to fix it (which is not likely given the breadth and depth of providers in AlwaysOn), it will indicate a reasonable level of information to determine what else you need to do, such as creating a new scenario, gather other information, run a different search to collect more focused details, and so on.</span></span>

<span data-ttu-id="839d3-116">Le service de journalisation centralisé fournit deux moyens d’émettre des commandes.</span><span class="sxs-lookup"><span data-stu-id="839d3-116">The Centralized Logging Service provides two ways to issue commands.</span></span> <span data-ttu-id="839d3-117">Plusieurs rubriques ont été focalisées dans le cadre de l’utilisation de Windows PowerShell par le biais de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="839d3-117">A number of topics have been focused squarely on using Windows PowerShell through the Lync Server Management Shell.</span></span> <span data-ttu-id="839d3-118">La possibilité d’utiliser un certain nombre de configurations et de commandes complexes favorise l’utilisation de Windows PowerShell pour le service de journalisation centralisée.</span><span class="sxs-lookup"><span data-stu-id="839d3-118">The ability to use a number of complex configurations and commands favors Windows PowerShell for Centralized Logging Service use.</span></span> <span data-ttu-id="839d3-119">Étant donné que Windows PowerShell via Lync Server Management Shell est presque omniprésent pour toutes les fonctions de Lync Server, seules les commandes Windows PowerShell sont abordées.</span><span class="sxs-lookup"><span data-stu-id="839d3-119">Because Windows PowerShell through the Lync Server Management Shell is nearly ubiquitous for all functions in Lync Server, only the Windows PowerShell commands are discussed.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="839d3-120">Si vous décidez d’utiliser le jeu de commandes limité disponible à partir de la ligne de commande, vous pouvez obtenir de l’aide <CODE>ClsController.exe</CODE>sur CLSController. exe en le tapant.</span><span class="sxs-lookup"><span data-stu-id="839d3-120">If you decide to use the limited command set available from the command line, you can get help with CLSController.exe by typing <CODE>ClsController.exe</CODE>.</span></span> <span data-ttu-id="839d3-121">Par défaut, <STRONG>ClsController. exe</STRONG> est installé dans le répertoire C:\Program Files\Microsoft Lync Server 2013 \ ClsAgent.</span><span class="sxs-lookup"><span data-stu-id="839d3-121">By default, <STRONG>ClsController.exe</STRONG> is installed in the directory C:\Program Files\Microsoft Lync Server 2013\ClsAgent.</span></span>



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a><span data-ttu-id="839d3-122">Pour exécuter démarrer-CsClsLogging avec Windows PowerShell en utilisant les commandes de base</span><span class="sxs-lookup"><span data-stu-id="839d3-122">To run Start-CsClsLogging with Windows PowerShell using basic commands</span></span>

1.  <span data-ttu-id="839d3-123">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="839d3-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="839d3-124">Démarrez un scénario de journalisation avec le service de journalisation centralisée en entrant la commande suivante:</span><span class="sxs-lookup"><span data-stu-id="839d3-124">Start a logging scenario with the Centralized Logging Service by typing the following:</span></span>
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    <span data-ttu-id="839d3-125">Pour lancer le scénario **AlwaysOn**, par exemple, tapez :</span><span class="sxs-lookup"><span data-stu-id="839d3-125">For example, to start the **AlwaysOn** scenario, type:</span></span>
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="839d3-126">Le scénario AlwaysOn n’a pas de durée par défaut.</span><span class="sxs-lookup"><span data-stu-id="839d3-126">The AlwaysOn scenario has no default duration.</span></span> <span data-ttu-id="839d3-127">Ce scénario s’exécutera jusqu’à ce que l’arrêtiez de façon explicite avec l’applet de commande <STRONG>Stop-CsClsLogging</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="839d3-127">This scenario will run until you explicitly stop it with the <STRONG>Stop-CsClsLogging</STRONG> cmdlet.</span></span> <span data-ttu-id="839d3-128">Pour plus d’informations, voir <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="839d3-128">For details, see <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span> <span data-ttu-id="839d3-129">Pour tous les autres scénarios, la durée par défaut est de 4 heures.</span><span class="sxs-lookup"><span data-stu-id="839d3-129">For all other scenarios, the default duration is 4 hours.</span></span>

    
    </div>

3.  <span data-ttu-id="839d3-130">Appuyez sur Entrée pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="839d3-130">Press Enter to run the command.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="839d3-131">L’exécution de la commande et la réception du statut des ordinateurs par celle-ci dans votre déploiement peuvent prendre quelques instants (de 30 à 60 secondes).</span><span class="sxs-lookup"><span data-stu-id="839d3-131">It may take a short amount of time (30 to 60 seconds) for the commands to run and to receive the status back from the computers in your deployment.</span></span>

    
    </div>
    
    <span data-ttu-id="839d3-132">![Exécution de Start-CsClsLogging.] (images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Exécution de Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="839d3-132">![Running Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>

4.  <span data-ttu-id="839d3-133">Pour lancer un autre scénario, utilisez l’applet de commande **Start-CsClsLogging** associée au nom du scénario supplémentaire à exécuter (par exemple, le scénario **Authentification**) :</span><span class="sxs-lookup"><span data-stu-id="839d3-133">To start another scenario, use the **Start-CsClsLogging** cmdlet with the name of the additional scenario to run as follows (for example, the scenario **Authentication**):</span></span>
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="839d3-134">Deux scénarios peuvent s’exécuter sur un ordinateur donné à tout moment.</span><span class="sxs-lookup"><span data-stu-id="839d3-134">You can have a total of two scenarios running on any given computer at any time.</span></span> <span data-ttu-id="839d3-135">Si l’étendue de la commande est globale, tous les ordinateurs dans votre déploiement exécuteront un scénario ou les deux.</span><span class="sxs-lookup"><span data-stu-id="839d3-135">If the command is global in scope, all of the computers in your deployment will run the scenario or scenarios.</span></span> <span data-ttu-id="839d3-136">Pour lancer un troisième scénario, vous devez arrêter la journalisation sur l’ordinateur, le pool, le site ou l’étendue globale sur lequel vous souhaitez exécuter le nouveau scénario.</span><span class="sxs-lookup"><span data-stu-id="839d3-136">To start a third scenario, you must stop logging on the computer, pool, site, or global scope that you want to run the new scenario on.</span></span> <span data-ttu-id="839d3-137">Si vous avez lancé la commande pour une étendue globale, vous pouvez arrêter la journalisation pour un scénario ou les deux sur un ou plusieurs ordinateurs et pools.</span><span class="sxs-lookup"><span data-stu-id="839d3-137">If you have started a global scope, you can stop logging for one or both of the scenarios on one or more computers and pools.</span></span> <span data-ttu-id="839d3-138">Pour plus d’informations sur la gestion des scénarios en cours d’exécution, voir <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">utilisation de l’application arrêt pour le service de journalisation centralisée dans Lync Server 2013</A> et <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">arrêt-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="839d3-138">For details about managing which scenarios are running, see <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A> and <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a><span data-ttu-id="839d3-139">Pour exécuter Start-CsClsLogging avec Windows PowerShell à l’aide de commandes avancées</span><span class="sxs-lookup"><span data-stu-id="839d3-139">To run Start-CsClsLogging with Windows PowerShell using advanced commands</span></span>

1.  <span data-ttu-id="839d3-140">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="839d3-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="839d3-p108">Il existe d’autres paramètres pour gérer les commandes de journalisation. Vous pouvez utiliser –Duration pour définir la durée d’exécution d’un scénario. Vous pouvez également définir –Computers, une liste de noms complets d’ordinateurs séparés par une virgule ou –Pools, une liste de noms complets de pools séparés par une virgule sur lesquels vous souhaitez exécuter la journalisation.</span><span class="sxs-lookup"><span data-stu-id="839d3-p108">Additional parameters are available to manage the logging commands. You can use –Duration to adjust the length of time for the scenario to run. You also can define –Computers, a list of computer fully qualified domain names (FQDNs) separated by a comma, or –Pools, a comma separated list of FQDNs for pools that you want to run logging on.</span></span>
    
    <span data-ttu-id="839d3-144">Vous démarrez une session de journalisation pour le scénario *UserReplicator* sur le pool «pool01.contoso.net».</span><span class="sxs-lookup"><span data-stu-id="839d3-144">You start a logging session for the *UserReplicator* scenario on the pool "pool01.contoso.net".</span></span> <span data-ttu-id="839d3-145">Vous pouvez également définir la durée de la session de journalisation à 8 heures.</span><span class="sxs-lookup"><span data-stu-id="839d3-145">You also define the duration of the logging session at 8 hours.</span></span> <span data-ttu-id="839d3-146">Pour cela, tapez :</span><span class="sxs-lookup"><span data-stu-id="839d3-146">To do this, type:</span></span>
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    <span data-ttu-id="839d3-147">L’exécution de ce scénario renvoie un résultat similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="839d3-147">The successful execution of this scenario returns a result like the following:</span></span>
    
    <span data-ttu-id="839d3-148">![Exécution de Start-CsClsLogging.] (images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Exécution de Start-CsClsLogging.")</span><span class="sxs-lookup"><span data-stu-id="839d3-148">![Running Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Running Start-CsClsLogging.")</span></span>
    
    <span data-ttu-id="839d3-149">Notez que dans cet exemple, les scénarios AlwaysOn et UserReplicator sont exécutés.</span><span class="sxs-lookup"><span data-stu-id="839d3-149">Note that in this example, the AlwaysOn scenario is running and the UserReplicator scenario is running.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="839d3-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="839d3-150">See Also</span></span>


[<span data-ttu-id="839d3-151">Présentation du service de journalisation centralisé dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="839d3-151">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

