---
title: 'Lync Server 2013 : rapport d’utilisation de Response Group'
description: 'Lync Server 2013 : rapport d’utilisation de Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e541a618e8578debc84630037d530c96f4e39ea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553060"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="b3edb-103">Rapport d’utilisation de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3edb-103">Response Group Usage Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3edb-104">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b3edb-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b3edb-105">L’application Response Group permet à Microsoft Lync Server 2013 de répondre et d’acheminer les appels téléphoniques en fonction du numéro composé et, éventuellement, des réponses de l’appelant à une série de questions.</span><span class="sxs-lookup"><span data-stu-id="b3edb-105">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="b3edb-106">En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="b3edb-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="b3edb-107">Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement acheminer cet appel vers le premier agent de support disponible.</span><span class="sxs-lookup"><span data-stu-id="b3edb-107">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="b3edb-108">En guise d’alternative, Lync Server peut poser une série de questions («appuyez sur 1 si vous rencontrez des problèmes de matériel.</span><span class="sxs-lookup"><span data-stu-id="b3edb-108">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="b3edb-109">Appuyez sur 2 pour des problèmes logiciels.</span><span class="sxs-lookup"><span data-stu-id="b3edb-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="b3edb-110">Appuyez sur 3 Si vous rencontrez des problèmes réseau. ") puis Acheminez l’appel vers l’agent du support technique le plus approprié en fonction de la réponse à ces questions.</span><span class="sxs-lookup"><span data-stu-id="b3edb-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="b3edb-111">Le rapport d’utilisation de Response Group donne une vision détaillée du nombre d’appels téléphoniques reçus par tous vos flux de travail Response Group, puis répartit ces appels en catégories plus précises telles que Appels offerts, Appels ayant obtenu une réponse et Appels abandonnés.</span><span class="sxs-lookup"><span data-stu-id="b3edb-111">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="b3edb-112">La meilleure façon de tirer parti du rapport d’utilisation de Response Group est de comprendre la différence entre les types d’appel signalés :</span><span class="sxs-lookup"><span data-stu-id="b3edb-112">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="b3edb-p102">**Appels reçus** : nombre total d’appels reçus par toutes les instances de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="b3edb-115">**Appels réussis**.</span><span class="sxs-lookup"><span data-stu-id="b3edb-115">**Successful calls**.</span></span> <span data-ttu-id="b3edb-116">Nombre total d’appels qui ont été sélectionnés par l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-116">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="b3edb-p104">**Appels offerts** : nombre total d’appels transférés à un agent Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="b3edb-p105">**Appels ayant obtenu une réponse** : nombre total d’appels auxquels un agent Response Group a effectivement répondu.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="b3edb-p106">**Pourcentage d’appels abandonnés** : pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous recevez 10 appels dont 7 avec réponse, vous retranchez 7 de 10 et obtenez donc 3 appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous donne un pourcentage d’appels abandonnés de 30 %.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="b3edb-p107">**Appels transférés** : nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="b3edb-p108">Si vous examinez le rapport d’utilisation de Response Group et que vous ne vous souvenez pas de la définition des types d’appels indiqués, il suffit de pointer le curseur de la souris sur l’étiquette du type d’appel concerné et une info-bulle apparaît contenant une brève description du type de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="b3edb-p109">Le rapport d’utilisation de Response Group vous permet de filtrer sur un URI de flux de travail (l’adresse SIP associée à ce flux de travail). Toutefois, les URI de flux de travail n’apparaissent pas réellement dans le rapport. Si vous cherchez à identifier les flux de travail qui répondent le plus aux appels ou ceux qui reçoivent le plus d’appels transférés, cliquez sur la mesure appropriée pour ouvrir le rapport des listes d’appels Response Group pour la période donnée. Ce rapport, en revanche, indique les URI de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="b3edb-134">Accéder au rapport d’utilisation de Response Group</span><span class="sxs-lookup"><span data-stu-id="b3edb-134">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="b3edb-135">Le rapport d’utilisation de Response Group est accessible depuis la page d’accueil Rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="b3edb-135">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="b3edb-136">Vous pouvez accéder au [rapport liste des appels Response Group dans Lync Server 2013](lync-server-2013-response-group-call-list-report.md) en cliquant sur l’une des mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3edb-136">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="b3edb-137">Appels reçus</span><span class="sxs-lookup"><span data-stu-id="b3edb-137">Received calls</span></span>

  - <span data-ttu-id="b3edb-138">Appels réussis</span><span class="sxs-lookup"><span data-stu-id="b3edb-138">Successful calls</span></span>

  - <span data-ttu-id="b3edb-139">Appels offerts</span><span class="sxs-lookup"><span data-stu-id="b3edb-139">Offered calls</span></span>

  - <span data-ttu-id="b3edb-140">Appels ayant obtenu une réponse</span><span class="sxs-lookup"><span data-stu-id="b3edb-140">Answered calls</span></span>

  - <span data-ttu-id="b3edb-141">Appels transférés</span><span class="sxs-lookup"><span data-stu-id="b3edb-141">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="b3edb-142">Tirer le meilleur parti du rapport d’utilisation de Response Group</span><span class="sxs-lookup"><span data-stu-id="b3edb-142">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="b3edb-143">L’utilisation la plus intéressante de ce rapport n’est peut-être pas la plus évidente : il s’agit de sa capacité à recueillir des informations d’utilisation pour un seul flux de travail Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-143">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b3edb-144">Un flux de travail Response Group est fondamentalement un ensemble d’instructions qui déterminent le rôle de Lync Server lorsqu’un utilisateur compose un numéro de téléphone particulier.</span><span class="sxs-lookup"><span data-stu-id="b3edb-144">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="b3edb-145">À cette fin, chaque flux de travail est associé de manière unique à un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="b3edb-145">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="b3edb-146">Lorsqu’une personne appelle ce numéro, le flux de travail détermine la manière dont l’appel sera géré.</span><span class="sxs-lookup"><span data-stu-id="b3edb-146">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="b3edb-147">Par exemple, le flux de travail peut entraîner le routage de l’appel vers une série de questions de réponse vocale interactive (IVR) invitant l’appelant à entrer des informations supplémentaires («appuyez sur 1 pour obtenir de l’assistance matérielle.</span><span class="sxs-lookup"><span data-stu-id="b3edb-147">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="b3edb-148">Appuyez sur 2 pour obtenir une assistance logicielle. ").</span><span class="sxs-lookup"><span data-stu-id="b3edb-148">Press 2 for software support.").</span></span> <span data-ttu-id="b3edb-149">En guise d’alternative, le flux de travail peut entraîner le placement de l’appel dans une file d’attente, l’appelant étant mis en attente jusqu’à ce qu’un agent soit disponible pour répondre à l’appel.</span><span class="sxs-lookup"><span data-stu-id="b3edb-149">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="b3edb-150">La disponibilité des agents pour répondre aux appels dépend également du workflow : les workflows permettent de définir les heures ouvrées (jours de la semaine et heures pendant lesquels les agents sont disponibles pour répondre aux appels) et les congés (jours pendant lesquels aucun agent n’est disponible pour répondre aux appels).</span><span class="sxs-lookup"><span data-stu-id="b3edb-150">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="b3edb-151">Chaque fois que vous composez un numéro de téléphone qui appartient à l’application Response Group, vous appelez un flux de travail Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-151">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="b3edb-p112">Bien que les URI de flux de travail n’apparaissent pas dans le rapport d’utilisation de Response Group, il est encore possible d’afficher les statistiques d’utilisation pour un seul flux de travail, ce qui est souvent très utile. Par exemple, supposons que vous avez récemment lancé une nouvelle campagne publicitaire et que vous souhaitez savoir si des personnes appellent pour en savoir plus sur le produit. Si vous avez associé un flux de travail Response Group au numéro de téléphone indiqué dans la campagne publicitaire, vous pouvez facilement consulter le nombre de personnes (s’il y en a) qui ont appelé ce numéro.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="b3edb-155">Vous pouvez aussi utiliser une approche similaire pour évaluer le nombre d’appels gérés par votre support technique interne ou votre service client.</span><span class="sxs-lookup"><span data-stu-id="b3edb-155">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="b3edb-156">Pour passer en revue les statistiques d’utilisation d’un flux de travail en particulier, entrez l’URI du flux de travail dans la zone correspondante.</span><span class="sxs-lookup"><span data-stu-id="b3edb-156">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="b3edb-157">Comme indiqué auparavant, les URI de flux de travail (adresse SIP associée au flux de travail) n’apparaissent pas dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="b3edb-157">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="b3edb-158">Cela signifie que vous devez utiliser un autre moyen pour déterminer l’URI d’un flux de travail.</span><span class="sxs-lookup"><span data-stu-id="b3edb-158">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="b3edb-159">Pour ce faire, vous pouvez utiliser Windows PowerShell et Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b3edb-159">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="b3edb-160">Par exemple, cette commande renvoie les URI de tous vos flux de travail Response Group :</span><span class="sxs-lookup"><span data-stu-id="b3edb-160">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="b3edb-161">Les données renvoyées seront de ce type :</span><span class="sxs-lookup"><span data-stu-id="b3edb-161">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="b3edb-162">Cette commande renvoie les informations relatives à un seul flux de travail, celui qui porte le nom « New Ad Campaign » :</span><span class="sxs-lookup"><span data-stu-id="b3edb-162">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b3edb-163">Filtres</span><span class="sxs-lookup"><span data-stu-id="b3edb-163">Filters</span></span>

<span data-ttu-id="b3edb-p114">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’utilisation de Response Group vous permet d’afficher les données de tous vos flux de travail Response Group ou d’un seul. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="b3edb-168">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’utilisation de Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-168">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="b3edb-169">Filtres du rapport d’utilisation de Response Group</span><span class="sxs-lookup"><span data-stu-id="b3edb-169">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3edb-170">Nom</span><span class="sxs-lookup"><span data-stu-id="b3edb-170">Name</span></span></th>
<th><span data-ttu-id="b3edb-171">Description</span><span class="sxs-lookup"><span data-stu-id="b3edb-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-172"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-172"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-p115">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b3edb-175">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b3edb-175">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b3edb-p116">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b3edb-178">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b3edb-178">7/7/2012</span></span></p>
<p><span data-ttu-id="b3edb-179">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="b3edb-179">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b3edb-180">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b3edb-180">7/3/2012</span></span></p>
<p><span data-ttu-id="b3edb-181">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="b3edb-181">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-182"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-182"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-p117">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b3edb-185">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b3edb-185">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b3edb-p118">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b3edb-188">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="b3edb-188">7/7/2012</span></span></p>
<p><span data-ttu-id="b3edb-189">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="b3edb-189">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b3edb-190">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="b3edb-190">7/3/2012</span></span></p>
<p><span data-ttu-id="b3edb-191">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="b3edb-191">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-192"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-192"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-p119">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b3edb-195">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="b3edb-195">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b3edb-196">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="b3edb-196">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b3edb-197">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="b3edb-197">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b3edb-198">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="b3edb-198">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b3edb-p120">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de départ le 07.08.12 et une date de fin le 28.09.12, les données sont affichées pour les jours compris entre le 07.08.12 12:00 AM et le 07.09.12 12:00 AM (soit un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="b3edb-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-201"><strong>URI de flux de travail</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-201"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-p121">Vous permet de limiter les données retournées au flux de travail de Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b3edb-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="b3edb-205">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b3edb-205">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b3edb-206">Mesures</span><span class="sxs-lookup"><span data-stu-id="b3edb-206">Metrics</span></span>

<span data-ttu-id="b3edb-207">Le tableau qui suit répertorie les informations fournies dans le rapport d’utilisation de Response Group.</span><span class="sxs-lookup"><span data-stu-id="b3edb-207">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="b3edb-208">Mesures du rapport d’utilisation de Response Group</span><span class="sxs-lookup"><span data-stu-id="b3edb-208">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3edb-209">Nom</span><span class="sxs-lookup"><span data-stu-id="b3edb-209">Name</span></span></th>
<th><span data-ttu-id="b3edb-210">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="b3edb-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b3edb-211">Description</span><span class="sxs-lookup"><span data-stu-id="b3edb-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-212"><strong>Toutes les heures</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="b3edb-213"><strong>Journalière</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="b3edb-214"><strong>Hebdomadaire</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="b3edb-215"><strong>Mensuelle</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-216">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-216">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p122">Indique l’intervalle de temps sélectionné. Si applicable, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées sur l’intervalle en question. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 07.07.12, vous affichez une répartition horaire de l’activité d’inscription de l’utilisateur à cette date.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-220"><strong>Appels reçus</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-220"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-221">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-221">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p123">Nombre total d’appels reçus par toutes les instances de l’application Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-224"><strong>Appels réussis</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-224"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-225">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-225">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p124">Nombre total d’appels auxquels l’application Response Group a répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-228"><strong>Appels offerts</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-228"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-229">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-229">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p125">Nombre total d’appels qui ont été transférés à un agent Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-232"><strong>Appels ayant obtenu une réponse</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-232"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-233">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-233">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p126">Nombre total d’appels auxquels un agent Response Group a effectivement répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-236"><strong>Pourcentage d’appels abandonnés</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-236"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-237">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-237">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p127">Nombre total d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Ce chiffre est calculé en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez 10 appels reçus et sept avec réponse, vous soustrayez sept de 10, et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous fournit un pourcentage d’appels abandonnés de 30%.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3edb-242"><strong>Minutes d’appel moyennes par agent</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-242"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-243">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-243">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-244">Temps moyen consacré par un agent Response Group à un appel.</span><span class="sxs-lookup"><span data-stu-id="b3edb-244">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3edb-245"><strong>Appels transférés</strong></span><span class="sxs-lookup"><span data-stu-id="b3edb-245"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b3edb-246">Non</span><span class="sxs-lookup"><span data-stu-id="b3edb-246">No</span></span></p></td>
<td><p><span data-ttu-id="b3edb-p128">Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="b3edb-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

