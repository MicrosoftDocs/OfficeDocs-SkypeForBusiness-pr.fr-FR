---
title: 'Lync Server 2013 : utilisation de stop pour le service de journalisation centralisée'
description: 'Lync Server 2013 : utilisation de stop pour le service de journalisation centralisée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114530d976b623bd4e5d75555a91a0ec3240ba07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560220"
---
# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="0a13a-103">Utilisation de stop pour le service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a13a-103">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a13a-104">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a13a-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a13a-105">Vous pouvez arrêter une session de journalisation en cours avec l’applet de commande Stop-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="0a13a-105">You can stop a currently running logging session with the Stop-CsClsLogging cmdlet.</span></span> <span data-ttu-id="0a13a-106">En général, vous rencontrerez peu de situations vous obligeant à arrêter une session de journalisation.</span><span class="sxs-lookup"><span data-stu-id="0a13a-106">Generally, there aren’t many situations in which you would need to stop a logging session.</span></span> <span data-ttu-id="0a13a-107">Par exemple, vous pouvez faire des recherches dans les journaux et modifier des configurations sans devoir arrêter d’abord la journalisation.</span><span class="sxs-lookup"><span data-stu-id="0a13a-107">For example, you can search logs and change configurations without first needing to stop logging.</span></span> <span data-ttu-id="0a13a-108">Si deux scénarios sont en cours d’exécution, par exemple AlwaysOn et UserReplicator, alors que vous devez recueillir des informations relatives à l’authentification, vous devez arrêter un de ces deux scénarios (au niveau global, du site, du pool ou de l’ordinateur) avant de pouvoir lancer l’exécution du scénario  d’authentification.</span><span class="sxs-lookup"><span data-stu-id="0a13a-108">If you have two scenarios running, for example AlwaysOn and UserReplicator, and you need to collect information related to Authentication, you will need to stop one of the other scenarios (at a global, site, pool or computer scope) before you can start running to Authentication scenario.</span></span> <span data-ttu-id="0a13a-109">Pour plus d’informations, voir [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="0a13a-109">For details, see [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a13a-110">Lorsque vous souhaitez déterminer les scénarios que vous pouvez exécuter sur un déploiement, un pool ou un ordinateur donné, gardez à l’esprit que vous ne pouvez exécuter que deux scénarios <STRONG>par ordinateur</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0a13a-110">When determining what scenarios you can run on a given deployment, pool or computer, you need to remember that you are limited to running two scenarios <STRONG>per computer</STRONG>.</span></span> <span data-ttu-id="0a13a-111">Si vous procédez à la journalisation de l’activité d’un pool, vous devez traiter ce pool globalement.</span><span class="sxs-lookup"><span data-stu-id="0a13a-111">If you are logging activity on a pool, you should treat a pool as a single entity.</span></span> <span data-ttu-id="0a13a-112">Dans la plupart des cas, il n’est pas judicieux d’exécuter différents scénarios sur chaque ordinateur dans un pool.</span><span class="sxs-lookup"><span data-stu-id="0a13a-112">In most cases, it would not make sense to run different scenarios on each computer in a pool.</span></span> <span data-ttu-id="0a13a-113">Il n’est pas non plus logique d’examiner le problème pour lequel vous recherchez des données et vous demander alors quel scénario convient le mieux pour un ordinateur donné dans le déploiement entier.</span><span class="sxs-lookup"><span data-stu-id="0a13a-113">It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment.</span></span> <span data-ttu-id="0a13a-114">Par exemple, si vous envisagez d’utiliser le scénario UserReplicator, l’exécution de UserReplicator sur un serveur Edge ou un pool de serveurs est très peu importante.</span><span class="sxs-lookup"><span data-stu-id="0a13a-114">For example, if you consider the UserReplicator scenario, there would be very little value in running UserReplicator on an Edge Server or Edge pool.</span></span><BR><span data-ttu-id="0a13a-p103">Une fois que vous avez compris l’origine du problème et avez déterminé son impact, vous devez choisir soigneusement les scénarios à exécuter sur quels ordinateurs et pools. Bien qu’il soit judicieux d’exécuter le scénario AlwaysOn pour une application large, car il recueille des informations sur une grande variété de fournisseurs, certains scénarios ne sont utiles que sur certains ordinateurs ou pools. De plus, lorsque vous lancez une session de journalisation vous devez choisir au préalable le scénario offrant les meilleurs résultats. Si vous utilisez un scénario inapproprié, ou si vous utilisez un scénario qui est approprié pour la tâche mais pas adapté au niveau d’application envisagé (global, site, pool ou ordinateur), vous risquez d’obtenir des données inutiles, comme si vous n’aviez pas exécuté de scénario du tout.</span><span class="sxs-lookup"><span data-stu-id="0a13a-p103">After you understand the problem and the scope of the impact, you should make careful choices about what scenarios to run on which computers and pools. While the AlwaysOn scenario makes sense for a wide scope application because it collects information on a wide variety of providers, specific scenarios only have application value on specific computers or pools. Also, you should take caution when randomly starting up a logging session without first understanding the value of a given scenario. If you use the wrong scenario, or if you use a scenario that is appropriate for the task and you apply the scenario at the wrong scope (be it global, site, pool, or computer), you can get questionable data that is not very useful—as if you didn't run the scenario at all.</span></span>



</div>

<span data-ttu-id="0a13a-119">Pour contrôler les fonctions du service de journalisation centralisée à l’aide de Lync Server Management Shell, vous devez être membre des groupes de sécurité CsAdministrator ou RBAC (contrôle d’accès basé sur un rôle CsServerAdministrator), ou d’un rôle RBAC personnalisé qui contient l’un de ces deux groupes.</span><span class="sxs-lookup"><span data-stu-id="0a13a-119">To control the Centralized Logging Service functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="0a13a-120">Pour renvoyer la liste de tous les rôles RBAC auxquels cette applet de commande a été affectée (y compris les rôles RBAC personnalisés que vous avez créés vous-même), exécutez la commande suivante à partir de Lync Server Management Shell ou de l’invite Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="0a13a-120">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="0a13a-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0a13a-121">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a><span data-ttu-id="0a13a-122">Pour arrêter une session de service de journalisation centralisée en cours d’exécution</span><span class="sxs-lookup"><span data-stu-id="0a13a-122">To stop a currently running Centralized Logging Service session</span></span>

1.  <span data-ttu-id="0a13a-123">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0a13a-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0a13a-124">Interrogez le service de journalisation centralisée pour savoir quels scénarios sont en cours d’exécution en tapant ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0a13a-124">Query the Centralized Logging Service to find out what scenarios are currently running by typing the following:</span></span>
    
        Show-CsClsLogging
    
    <span data-ttu-id="0a13a-125">![Console Windows PowerShell après l’appel de Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Console Windows PowerShell après l’appel de Show-CsCl")</span><span class="sxs-lookup"><span data-stu-id="0a13a-125">![Windows PowerShell console after calling Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Windows PowerShell console after calling Show-CsCl")</span></span>
    
    <span data-ttu-id="0a13a-126">Le résultat de Show-CsClsLogging est un résumé des scénarios en cours d’exécution et de leur étendue d’application.</span><span class="sxs-lookup"><span data-stu-id="0a13a-126">The result of Show-CsClsLogging is a summary of the scenarios that are running and what scope they are running in.</span></span> <span data-ttu-id="0a13a-127">Pour plus d’informations, voir [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span><span class="sxs-lookup"><span data-stu-id="0a13a-127">For details, see [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).</span></span>

3.  <span data-ttu-id="0a13a-128">Pour arrêter une session de journalisation en cours avec un scénario spécifique, tapez :</span><span class="sxs-lookup"><span data-stu-id="0a13a-128">To stop a currently running logging session with a specific scenario, type:</span></span>
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    <span data-ttu-id="0a13a-129">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="0a13a-129">For example:</span></span>
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    <span data-ttu-id="0a13a-130">Cette commande arrête la journalisation avec le scénario UserReplicatior sur pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="0a13a-130">This command will stop logging with the UserReplicatior scenario on pool01.contoso.net.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a13a-131">Les journaux créés au cours de cette session de journalisation avec le scénario UserReplicator ne sont pas supprimés.</span><span class="sxs-lookup"><span data-stu-id="0a13a-131">Logs created during this logging session using the UserReplicator scenario are not deleted.</span></span> <span data-ttu-id="0a13a-132">Vous pouvez continuer à effectuer des recherches avec la journalisation au lieu d’utiliser la commande Search-CsClsLogging.</span><span class="sxs-lookup"><span data-stu-id="0a13a-132">The logging is still available for you to execute searches against using the Search-CsClsLogging command.</span></span> <span data-ttu-id="0a13a-133">Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span><span class="sxs-lookup"><span data-stu-id="0a13a-133">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.</span></span>

    
    </div>

<span data-ttu-id="0a13a-p107">Faisant pendant à l’applet de commande Start-CsClsLogging, l’applet de commande Stop-CsClsLogging arrête la session de journalisation, définie par des scénarios, et conserve les journaux créés par celle-ci. Vous pouvez exécuter deux scénarios sur un ordinateur donné à tout moment. La méthode d’arrêt d’un scénario pour recueillir des informations à l’aide d’un autre scénario est une tâche courante que vous pouvez effectuer au cours du dépannage de la plupart des charges de travail.</span><span class="sxs-lookup"><span data-stu-id="0a13a-p107">Acting as the companion command to Start-CsClsLogging, the Stop-CsClsLogging cmdlet ends the logging session, defined by scenarios, and retains the logs created by the logging session. You can run two scenarios on a given computer at any time. The method of stopping one scenario to gather information using another scenario is a common task that you can perform during most workload troubleshooting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a13a-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a13a-137">See Also</span></span>


[<span data-ttu-id="0a13a-138">Utilisation de Start pour le service de journalisation centralisée pour la capture des journaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a13a-138">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[<span data-ttu-id="0a13a-139">Vue d’ensemble du service de journalisation centralisée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a13a-139">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="0a13a-140">Show-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="0a13a-140">Show-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[<span data-ttu-id="0a13a-141">Start-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="0a13a-141">Start-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[<span data-ttu-id="0a13a-142">Stop-CsClsLogging</span><span class="sxs-lookup"><span data-stu-id="0a13a-142">Stop-CsClsLogging</span></span>](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

