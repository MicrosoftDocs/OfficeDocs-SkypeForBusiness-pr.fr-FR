---
title: 'Lync Server 2013 : vérification des journaux des événements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking event logs
ms:assetid: 5500720d-c628-4dbd-84bc-a5becc39b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720914(v=OCS.15)
ms:contentKeyID: 63969602
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862d419d9db5d8465b3507c40fde32acd01bb659
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-event-logs-in-lync-server-2013"></a><span data-ttu-id="7b6ce-102">Vérification des journaux des événements dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b6ce-102">Checking event logs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b6ce-103">_**Dernière modification de la rubrique :** 2014-08-06_</span><span class="sxs-lookup"><span data-stu-id="7b6ce-103">_**Topic Last Modified:** 2014-08-06_</span></span>

<span data-ttu-id="7b6ce-104">Vous pouvez utiliser l' [Observateur d’événements Windows](http://go.microsoft.com/fwlink/p/?linkid=314067) pour afficher les journaux d’événements et obtenir des informations sur les échecs de service, les erreurs de réplication dans les services de domaine Active Directory et les avertissements relatifs aux ressources système, tels que la mémoire virtuelle et l’espace disque.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-104">You can use [Windows Event Viewer](http://go.microsoft.com/fwlink/p/?linkid=314067) to view event logs and obtain information about service failures, replication errors in the AD DS, and warnings about system resources such as virtual memory and disk space.</span></span> <span data-ttu-id="7b6ce-105">Le visionneuse d’événements est incluse dans Windows Server 2008 et 2012.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-105">Event Viewer is included with Windows Server 2008 and 2012.</span></span>

<span data-ttu-id="7b6ce-106">Dans l’outil de journalisation de Lync Server 2013, lorsque vous mettez fin à la session de débogage, cliquez sur **analyser les fichiers journaux** pour afficher les fichiers journaux à l’aide de l’outil Snoop.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-106">In the Lync Server 2013 Logging Tool, when you end the debug session, click **Analyze Log Files** to view the log files by using the Snooper tool.</span></span>

<span data-ttu-id="7b6ce-107">L’observateur d’événements gère les journaux des événements d’application, de sécurité et de système sur l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-107">Event Viewer maintains logs about application, security, and system events on the computer.</span></span> <span data-ttu-id="7b6ce-108">Il s’agit de Lync Server 2013 et de Windows, et de signaler des erreurs aux journaux des événements.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-108">Both Lync Server 2013 and Windows report warnings and error conditions to the event logs.</span></span> <span data-ttu-id="7b6ce-109">Par conséquent, révisez les journaux d’événements quotidiennement.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-109">Therefore, review event logs daily.</span></span>

<span data-ttu-id="7b6ce-110">Utilisez l’observateur d’événements pour :</span><span class="sxs-lookup"><span data-stu-id="7b6ce-110">Use Event Viewer to:</span></span>

  - <span data-ttu-id="7b6ce-111">Afficher et gérer les journaux d’événements.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-111">View and manage event logs.</span></span>

  - <span data-ttu-id="7b6ce-112">Obtenez des informations sur les problèmes liés au matériel, au logiciel et au système qui doivent être résolus.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-112">Obtain information about hardware, software, and system issues that must be resolved.</span></span>

  - <span data-ttu-id="7b6ce-113">Identifiez les tendances qui nécessitent une action ultérieure.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-113">Identify trends that require future action.</span></span>

<span data-ttu-id="7b6ce-114">Un serveur exécutant Lync Server sur un système d’exploitation Windows Server enregistre les événements dans quatre types de journaux :</span><span class="sxs-lookup"><span data-stu-id="7b6ce-114">A server that is running Lync Server on a Windows Server operating system records events in four types of logs:</span></span>

  - <span data-ttu-id="7b6ce-115">**Journaux d’application**   le journal de l’application contient les événements enregistrés par des applications ou des programmes.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-115">**Application logs**   The Application log contains events logged by applications or programs.</span></span> <span data-ttu-id="7b6ce-116">Les développeurs déterminent les événements à consigner.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-116">Developers determine which events to log.</span></span> <span data-ttu-id="7b6ce-117">Par exemple, un programme de base de données peut enregistrer une erreur de fichier dans le journal de l’application.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-117">For example, a database program might record a file error in the Application log.</span></span> <span data-ttu-id="7b6ce-118">La plupart des événements associés à Lync Server 2013 apparaissent dans le journal des applications.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-118">Most Lync Server 2013-related events appear in the Application log.</span></span>

  - <span data-ttu-id="7b6ce-119">**Journaux**   de sécurité le journal de sécurité enregistre les événements tels que valides et non valides pour les tentatives en plus d’événements liés à l’utilisation des ressources, comme la création, l’ouverture ou la suppression de fichiers ou d’autres objets.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-119">**Security logs**   The Security log records events such as valid and not valid logon tries in addition to events related to resource use such as creating, opening, or deleting files or other objects.</span></span> <span data-ttu-id="7b6ce-120">Par exemple, si l’audit d’ouverture de session est activé, les tentatives de connexion au système sont enregistrées dans le journal de sécurité.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-120">For example, if logon auditing is enabled, attempts to log on to the system are recorded in the Security log.</span></span>

  - <span data-ttu-id="7b6ce-121">**Journal système enregistre**   le journal système contient des événements enregistrés par les composants du système Windows.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-121">**System logs**   The System log contains events logged by Windows system components.</span></span> <span data-ttu-id="7b6ce-122">Par exemple, l’échec du chargement d’un pilote ou d’un autre composant système lors du démarrage est enregistré dans le journal système.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-122">For example, the failure of a driver or other system component to load during startup is recorded in the System log.</span></span> <span data-ttu-id="7b6ce-123">Les types d’événements enregistrés par les composants système sont prédéterminés par le serveur.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-123">The event types logged by system components are predetermined by the server.</span></span>

  - <span data-ttu-id="7b6ce-124">**Lync Server 2013**   l’outil d’enregistrement enregistre des événements importants liés à l’authentification, aux connexions et aux actions de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-124">**Lync Server 2013**   The logging tool records significant events related to authentication, connections, and user actions.</span></span> <span data-ttu-id="7b6ce-125">Après l’activation de la journalisation des diagnostics, vous pouvez afficher les entrées du journal dans l’observateur d’événements.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-125">After enabling diagnostic logging, you can view the log entries in Event Viewer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b6ce-126">Nous vous déconseillons d’utiliser les paramètres d’enregistrement maximum sauf si vous y êtes invité par les services d’assistance technique Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-126">We do not recommend that you use the maximum logging settings unless you are instructed to do this by Microsoft Customer Support Services.</span></span> <span data-ttu-id="7b6ce-127">La journalisation maximale draine les ressources importantes et peut proposer de nombreux « faux positifs », c’est-à-dire des erreurs qui ne sont pas enregistrées uniquement dans le journal maximal, mais qui ne sont pas à l’origine du problème.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-127">Maximum logging drains significant resources and can give many “false positives,” that is, errors that get logged only at maximum logging but are really expected and are not a cause of concern.</span></span> <span data-ttu-id="7b6ce-128">Nous vous recommandons également de ne pas activer la journalisation des diagnostics de manière définitive.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-128">We also recommend that you do not enable diagnostic logging permanently.</span></span> <span data-ttu-id="7b6ce-129">Utilisez-le uniquement lors de la résolution des problèmes.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-129">Use it only when troubleshooting.</span></span>



</div>

<span data-ttu-id="7b6ce-130">Dans chaque journal de l’observateur d’événements, Lync Server 2013 enregistre les événements d’information, d’avertissement et d’erreur.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-130">Within each Event Viewer log, Lync Server 2013 records informational, warning, and error events.</span></span> <span data-ttu-id="7b6ce-131">Contrôlez soigneusement ces journaux pour suivre les types de transactions effectuées sur les serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-131">Monitor these logs closely to track the types of transactions being conducted on the Lync Server 2013 servers.</span></span> <span data-ttu-id="7b6ce-132">Vous devez archiver périodiquement les journaux ou utiliser la fonctionnalité de substitution automatique pour éviter de manquer d’espace.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-132">You should periodically archive the logs or use automatic rollover to avoid running out of space.</span></span> <span data-ttu-id="7b6ce-133">Étant donné que les fichiers journaux peuvent occuper une quantité limitée d’espace, augmentez la taille du journal (par exemple, à 50 Mo) et configurez-le pour que le serveur Lync Server 2013 puisse continuer à rédiger de nouveaux événements.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-133">Because log files can occupy a finite amount of space, increase the log size (for example, to 50 MB) and set it to overwrite so that the Lync Server 2013 Server can continue to write new events.</span></span>

<span data-ttu-id="7b6ce-134">Vous pouvez également automatiser l’administration du journal des événements en utilisant les outils et technologies suivants :</span><span class="sxs-lookup"><span data-stu-id="7b6ce-134">You can also automate event log administration by using the following tools and technologies:</span></span>

  - <span data-ttu-id="7b6ce-135">System Center Operations Manager surveille l’intégrité et l’utilisation des serveurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-135">System Center Operations Manager monitors the health and use of Lync Server 2013 servers.</span></span> <span data-ttu-id="7b6ce-136">Lync Server 2013 Management Pack pour Operations Manager étend Operations Manager en fournissant un contrôle spécialisé pour les serveurs exécutant Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-136">Lync Server 2013 Management Pack for Operations Manager extends Operations Manager by providing specialized monitoring for servers that are running Lync Server 2013.</span></span>

  - <span data-ttu-id="7b6ce-137">Le pack d’administration de Lync Server 2013 pour Operations Manager surveille les éditions standard et entreprise de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-137">The Lync Server 2013 Management Pack for Operations Manager monitors Standard and Enterprise Edition of Lync Server 2013.</span></span> <span data-ttu-id="7b6ce-138">Cette version inclut également le pack d’administration de qualité de l’interface (QoE) qui était auparavant un module d’administration distinct.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-138">This release also incorporates the Quality of Experience (QoE) Management Pack which was previously a separate management pack.</span></span>

<span data-ttu-id="7b6ce-139">Les types surveillés sont les entrées du journal des événements, les compteurs de performance et la surveillance dynamique de QoE.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-139">Monitored types are event log entries, performance counters and stateful monitoring of QoE.</span></span> <span data-ttu-id="7b6ce-140">Cette version du pack d’administration analyse uniquement Lync Server 2013 et 2010 et ne peut pas être utilisée pour surveiller Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-140">This version of the management pack only monitors Lync Server 2013 and 2010, and cannot be used to monitor Office Communications Server 2007.</span></span>

<span data-ttu-id="7b6ce-141">Le pack d’administration offre les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="7b6ce-141">The management pack provides the following features:</span></span>

  - <span data-ttu-id="7b6ce-142">Alertes indiquant un service affectant des événements</span><span class="sxs-lookup"><span data-stu-id="7b6ce-142">Alerts indicating service affecting events</span></span>

  - <span data-ttu-id="7b6ce-143">Alertes indiquant la configuration et autres problèmes d’impact sur les autres services</span><span class="sxs-lookup"><span data-stu-id="7b6ce-143">Alerts indicating configuration, and other non-service impacting issues</span></span>

  - <span data-ttu-id="7b6ce-144">Surveiller l’état des services Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b6ce-144">State monitoring of Lync Server services</span></span>

  - <span data-ttu-id="7b6ce-145">Connaissances du produit : cause et résolution des problèmes identifiés</span><span class="sxs-lookup"><span data-stu-id="7b6ce-145">Product knowledge: Cause and resolution of identified issues</span></span>

<span data-ttu-id="7b6ce-146">Pour plus d’informations sur le pack d’administration 2013 de Lync Server, voir [analyse de Lync server 2013 avec System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span><span class="sxs-lookup"><span data-stu-id="7b6ce-146">For more information about Lync Server 2013 Management Pack, refer to [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md).</span></span>

<span data-ttu-id="7b6ce-147">**Peigne**   d’événement l’outil peignement d’événement collecte des événements spécifiques provenant des journaux d’événements de plusieurs ordinateurs à un emplacement central.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-147">**Event Comb**   The Event Comb tool collects specific events from the event logs of several computers to one central location.</span></span> <span data-ttu-id="7b6ce-148">Elle vous permet de signaler uniquement les ID d’événement ou les sources d’événements qu’elle spécifie.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-148">It lets you report on only the event IDs or event sources it specifies.</span></span> <span data-ttu-id="7b6ce-149">Pour plus d’informations sur le peigne d’événement, voir le site Web des [outils de verrouillage et de gestion des comptes](http://go.microsoft.com/fwlink/?linkid=35607) .</span><span class="sxs-lookup"><span data-stu-id="7b6ce-149">For more information about Event Comb, see the [Account Lockout and Management Tools](http://go.microsoft.com/fwlink/?linkid=35607) website.</span></span>

<span data-ttu-id="7b6ce-150">**Déclencheurs d’événements**   dans Windows Server 2012 vous pouvez « joindre une tâche à cet événement » dans l’observateur d’événements Windows, où un administrateur peut exécuter un programme, envoyer un message électronique ou afficher un message visuel.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-150">**Event triggers**   In Windows Server 2012 you can "Attach a Task to This Event" within the Windows Event Viewer—where an administrator can either run a program, send an email message or display an on-screen message.</span></span> <span data-ttu-id="7b6ce-151">Pour plus d’informations sur cette fonctionnalité, voir la rubrique Windows Server 2008 R2 [exécuter une tâche en réponse à un événement donné](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b6ce-151">For more information about this feature, see the Windows Server 2008 R2 topic [Run a Task in Response to a Given Event](http://technet.microsoft.com/en-us/library/cc748900.aspx).</span></span> <span data-ttu-id="7b6ce-152">Vous pouvez également utiliser des outils de ligne de commande tels que’EventTrigger. exe’pour créer et interroger des journaux d’événements, et associer des programmes à des événements enregistrés spécifiques.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-152">You can also use command-line tools such as ‘Eventtrigger.exe’ to create and query event logs and associate programs with particular logged events.</span></span> <span data-ttu-id="7b6ce-153">À l’aide de Eventtriggers. exe, vous pouvez créer des déclencheurs d’événements qui exécutent des programmes lorsque des événements spécifiques se produisent.</span><span class="sxs-lookup"><span data-stu-id="7b6ce-153">By using Eventtriggers.exe, you can create event triggers that run programs when specific events occur.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7b6ce-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b6ce-154">See Also</span></span>


[<span data-ttu-id="7b6ce-155">Observateur d’événements Windows</span><span class="sxs-lookup"><span data-stu-id="7b6ce-155">Windows Event Viewer</span></span>](http://go.microsoft.com/fwlink/p/?linkid=314067)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

