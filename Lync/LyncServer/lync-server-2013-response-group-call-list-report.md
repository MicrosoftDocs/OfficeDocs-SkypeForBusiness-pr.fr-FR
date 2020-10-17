---
title: 'Lync Server 2013 : rapport de liste d’appels Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511761"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="1dcb3-102">Rapport de liste d’appels Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1dcb3-102">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dcb3-103">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="1dcb3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="1dcb3-104">L’application Response Group permet à Microsoft Lync Server 2013 de répondre et d’acheminer les appels téléphoniques en fonction du numéro composé et, éventuellement, des réponses de l’appelant à une série de questions.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="1dcb3-105">En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="1dcb3-106">Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement acheminer cet appel vers le premier agent de support disponible.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="1dcb3-107">En guise d’alternative, Lync Server peut poser une série de questions («appuyez sur 1 si vous rencontrez des problèmes de matériel.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="1dcb3-108">Appuyez sur 2 pour des problèmes logiciels.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="1dcb3-109">Appuyez sur 3 Si vous rencontrez des problèmes réseau. ") puis Acheminez l’appel vers l’agent du support technique le plus approprié en fonction de la réponse à ces questions.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="1dcb3-p102">Le Rapport des listes d’appels Response Group représente une collection d’appels effectués pendant une période spécifiée et pour un type d’appel spécifié. Le Rapport d’utilisation de Response Group (qui doit être ouvert au préalable pour que vous puissiez ouvrir le Rapport des listes d’appels Response Group) reconnaît les types d’appels suivants :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="1dcb3-p103">**Appels reçus**. Nombre total d’appels reçus par toutes les instances de l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="1dcb3-114">**Appels réussis**.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-114">**Successful calls**.</span></span> <span data-ttu-id="1dcb3-115">Nombre total d’appels qui ont été sélectionnés par l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="1dcb3-p105">**Appels offerts** : nombre total d’appels transférés à un agent Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="1dcb3-p106">**Appels ayant obtenu une réponse** : nombre total d’appels auxquels un agent Response Group a effectivement répondu.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="1dcb3-120">Pourcentage d’appels abandonnés.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="1dcb3-121">Pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="1dcb3-122">Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="1dcb3-123">Par exemple, si vous avez reçu dix appels et sept avec réponse, vous soustrayez sept de dix et obtenez donc trois appels sans réponse.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="1dcb3-124">Divisez ensuite cette valeur par dix, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="1dcb3-p108">**Appels transférés**. Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="1dcb3-127">Accès au Rapport des listes d’appels Response Group</span><span class="sxs-lookup"><span data-stu-id="1dcb3-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="1dcb3-128">Le rapport de liste d’appels Response Group est accessible uniquement en cliquant sur l’une des mesures suivantes figurant dans le [rapport d’utilisation de Response Group dans Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span><span class="sxs-lookup"><span data-stu-id="1dcb3-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="1dcb3-129">Appels reçus</span><span class="sxs-lookup"><span data-stu-id="1dcb3-129">Received calls</span></span>

  - <span data-ttu-id="1dcb3-130">Appels réussis</span><span class="sxs-lookup"><span data-stu-id="1dcb3-130">Successful calls</span></span>

  - <span data-ttu-id="1dcb3-131">Appels offerts</span><span class="sxs-lookup"><span data-stu-id="1dcb3-131">Offered calls</span></span>

  - <span data-ttu-id="1dcb3-132">Appels ayant obtenu une réponse</span><span class="sxs-lookup"><span data-stu-id="1dcb3-132">Answered calls</span></span>

  - <span data-ttu-id="1dcb3-133">Appels transférés</span><span class="sxs-lookup"><span data-stu-id="1dcb3-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="1dcb3-134">Utilisation optimale du Rapport des listes d’appels Response Group</span><span class="sxs-lookup"><span data-stu-id="1dcb3-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="1dcb3-p109">Le Rapport des listes d’appels Response Group vous permet de limiter les données affichées aux appels impliquant un flux de travail Response Group particulier. Pour cela, vous devez entrer l’URI de flux de travail (l’adresse SIP du flux de travail) dans la zone URI du flux de travail. Avant cela, vous devez cependant être en mesure de voir cette zone URI du flux de travail. Pour afficher les options de filtrage du Rapport des listes d’appels Response Group, cliquez sur le bouton Afficher / Masquer les paramètres dans la partie supérieure gauche de la fenêtre de rapport.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="1dcb3-139">Notez que le Rapport des listes d’appels Response Group n’affiche pas d’informations relatives au code de réponse ou à l’ID de diagnostic si vous maintenez le pointeur de la souris sur l’une de ces mesures.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="1dcb3-140">Si vous avez besoin d’informations supplémentaires, vous pouvez noter le code de réponse et/ou l’ID de diagnostic, puis rechercher ces valeurs dans le [rapport des principales défaillances dans Lync Server 2013](lync-server-2013-top-failures-report.md).</span><span class="sxs-lookup"><span data-stu-id="1dcb3-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="1dcb3-141">Si vous souhaitez obtenir la réponse à une question telle que « Quel est le flux de travail ayant reçu le plus d’appels ? », vous pouvez procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="1dcb3-p111">Dans le Rapport d’utilisation de Response Group, définissez la période souhaitée, puis cliquez sur la mesure Appels reçus pour ouvrir le Rapport des listes d’appels Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="1dcb3-p112">Exportez les données affichées dans le Rapport des listes d’appels Response Group. Par exemple, vous pourriez exporter les données au format Microsoft Excel, puis utiliser Excel pour convertir ces données en un fichier de valeurs séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="1dcb3-146">Exécutez vos analyses à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="1dcb3-147">Par exemple, si vous avez enregistré les données dans un fichier nommé C : \\ données \\ Response \_ Group \_ Call \_ List \_Report.csv, vous pouvez utiliser la commande suivante pour renvoyer le nombre total d’appels reçus pour chaque flux de travail répertorié dans le rapport :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="1dcb3-148">Des informations analogues aux suivantes seront retournées :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1dcb3-149">Filtres</span><span class="sxs-lookup"><span data-stu-id="1dcb3-149">Filters</span></span>

<span data-ttu-id="1dcb3-p113">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de liste des appels Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="1dcb3-152">Filtres de rapport de liste des appels Response Group</span><span class="sxs-lookup"><span data-stu-id="1dcb3-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dcb3-153">Nom</span><span class="sxs-lookup"><span data-stu-id="1dcb3-153">Name</span></span></th>
<th><span data-ttu-id="1dcb3-154">Description</span><span class="sxs-lookup"><span data-stu-id="1dcb3-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dcb3-155"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-p114">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1dcb3-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1dcb3-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1dcb3-p115">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1dcb3-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1dcb3-161">7/7/2012</span></span></p>
<p><span data-ttu-id="1dcb3-162">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1dcb3-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1dcb3-163">7/3/2012</span></span></p>
<p><span data-ttu-id="1dcb3-164">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcb3-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-p116">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1dcb3-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1dcb3-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1dcb3-p117">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1dcb3-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1dcb3-171">7/7/2012</span></span></p>
<p><span data-ttu-id="1dcb3-172">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1dcb3-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1dcb3-173">7/3/2012</span></span></p>
<p><span data-ttu-id="1dcb3-174">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcb3-175"><strong>URI du flux de travail</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-p118">Vous permet de limiter les données retournées au flux de travail de Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="1dcb3-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1dcb3-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcb3-180"><strong>Appels</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-181">Vous pouvez sélectionner l’un des types d’appels suivants :</span><span class="sxs-lookup"><span data-stu-id="1dcb3-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="1dcb3-182">Appels reçus</span><span class="sxs-lookup"><span data-stu-id="1dcb3-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="1dcb3-183">Appels réussis</span><span class="sxs-lookup"><span data-stu-id="1dcb3-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="1dcb3-184">Appels offerts</span><span class="sxs-lookup"><span data-stu-id="1dcb3-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="1dcb3-185">Appels ayant obtenu une réponse</span><span class="sxs-lookup"><span data-stu-id="1dcb3-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="1dcb3-186">Appels transférés</span><span class="sxs-lookup"><span data-stu-id="1dcb3-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1dcb3-187">Mesures</span><span class="sxs-lookup"><span data-stu-id="1dcb3-187">Metrics</span></span>

<span data-ttu-id="1dcb3-188">Le tableau qui suit répertorie les informations fournies dans le rapport de liste des appels Response Group pour chaque appel reçu par l’application Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="1dcb3-189">Mesures du rapport de liste des appels Response Group</span><span class="sxs-lookup"><span data-stu-id="1dcb3-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dcb3-190">Nom</span><span class="sxs-lookup"><span data-stu-id="1dcb3-190">Name</span></span></th>
<th><span data-ttu-id="1dcb3-191">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="1dcb3-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1dcb3-192">Description</span><span class="sxs-lookup"><span data-stu-id="1dcb3-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dcb3-193"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-194">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-194">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-195">Adresse SIP de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcb3-196"><strong>Flux de travail</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-197">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-197">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-198">Adresse SIP du flux de travail Response Group.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcb3-199"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-200">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-200">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-201">Date et heure de début de l’appel.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcb3-202"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-203">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-203">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-204">Date et heure de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dcb3-205"><strong>Code de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-206">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-206">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-207">Code de réponse SIP envoyé lors de l’échec de session.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dcb3-208"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="1dcb3-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="1dcb3-209">Non</span><span class="sxs-lookup"><span data-stu-id="1dcb3-209">No</span></span></p></td>
<td><p><span data-ttu-id="1dcb3-210">Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins de dépannage.</span><span class="sxs-lookup"><span data-stu-id="1dcb3-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

