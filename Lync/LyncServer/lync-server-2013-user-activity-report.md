---
title: 'Lync Server 2013: rapport d’activité de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04a7dd3dd1f2a061a327cc2a0bac79ee05f21d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846457"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="ed2a9-102">Rapport d’activité de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed2a9-102">User Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed2a9-103">_**Dernière modification de la rubrique:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="ed2a9-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="ed2a9-p101">Le rapport d’activité de l’utilisateur fournit une liste détaillée des sessions P2P et des sessions de conférence exécutées par vos utilisateurs au cours d’une période donnée. Contrairement à la plupart des rapports de surveillance, le rapport d’activité de l’utilisateur lie chaque appel à des utilisateurs individuels. Par exemple, les sessions P2P spécifient les URI SIP de la personne à l’origine de l’appel (utilisateur d’origine) et celles de la personne qui a été appelée (utilisateur de destination). Si vous développez les informations sur une conférence, vous obtiendrez la liste de tous les participants à la conférence, ainsi que leur rôle à cette occasion.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="ed2a9-p102">Le rapport d’activité de l’utilisateur est parfois appelé « rapport de support technique ». En effet, ce rapport est souvent utilisé par les équipes de support technique pour récupérer les informations de session d’un utilisateur spécifique. Vous pouvez filtrer les appels à destination ou en provenance d’un utilisateur individuel en tapant simplement son URI SIP dans la zone Préfixe d’URI d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="ed2a9-111">Dans ce cas, le rapport activité de l’utilisateur renvoie des informations pour tout utilisateur dont l’URI SIP commence par la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="ed2a9-112">Par exemple, si vous saisissez **ken** dans la zone URI, le rapport d’activité de l’utilisateur trouvera **Ken**.Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="ed2a9-113">Cependant, Il trouvera aussi les utilisateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="ed2a9-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed2a9-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="ed2a9-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed2a9-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="ed2a9-116">**Ken**.Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed2a9-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="ed2a9-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed2a9-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="ed2a9-p104">Pour faire en sorte que seules les informations concernant Ken Myer soient renvoyées, tapez son URI complet (Ken.Myer@litwareinc.com) dans la zone de recherche ou au moins suffisamment de caractères pour que l’URI soit distinguée de façon unique dans votre organisation. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p104">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization. For example:</span></span>

<span data-ttu-id="ed2a9-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="ed2a9-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="ed2a9-121">Pour accéder au rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed2a9-121">To access the user activity report</span></span>

<span data-ttu-id="ed2a9-122">Le rapport d’activité de l’utilisateur est accessible via la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="ed2a9-123">Pour accéder au rapport d’activité de l’utilisateur, vous pouvez également cliquer sur la métrique de l’URI de l’utilisateur dans le [rapport d’inventaire des téléphones IP de Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="ed2a9-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="ed2a9-124">Si vous cliquez sur URI de la conférence (pour une conférence) dans le rapport d’activité de l’utilisateur, vous accéderez au rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="ed2a9-125">De même, le fait de cliquer sur la métrique détaillée d’un appel d’égal à égal vous permet d’accéder au [rapport détaillé de la session d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="ed2a9-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="ed2a9-126">Utilisation optimale du rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed2a9-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="ed2a9-127">Même si le rapport d’activité de l’utilisateur contient des informations utiles, il peut parfois être difficile de les rechercher.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="ed2a9-128">Par exemple, toutes les activités de l’utilisateur qui interviennent au cours d’une période donnée apparaissent dans le rapport d’activité de l’utilisateur. Cela signifie que, à l’intérieur du rapport, se trouvent les informations sur les utilisateurs qui utilisent réellement Microsoft Lync Server 2013 de quelque manière que ce soit.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="ed2a9-129">Techniquement, il est possible que certaines activités de l’utilisateur ne soient pas enregistrées: alors que Lync Server s’efforce de conserver des informations sur tous les appels téléphoniques, il est possible qu’un appel ait été effectué sans que les informations relatives à cet appel soient écrites dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="ed2a9-130">Lync Server a été conçu pour donner un aspect très précis, mais pas nécessairement parfait pour l’utilisation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="ed2a9-131">(Le fait qu’il n’y a aucune garantie que 100% de tous les appels sont enregistrés explique pourquoi le contrôle de Lync Server ne doit pas être utilisé comme système de facturation.)</span><span class="sxs-lookup"><span data-stu-id="ed2a9-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="ed2a9-132">Deuxièmement, un rapport de rapport de contrôle ne peut afficher que des enregistrements 1 000.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-132">Second, a Monitoring Report report can only display, at most, 1,000 records.</span></span> <span data-ttu-id="ed2a9-133">Ainsi, selon le volume d’activité de vos utilisateurs et la période considérée, votre requête risque de ne pas renvoyer toutes les données effectivement stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-133">Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="ed2a9-134">Quels sont les utilisateurs qui ont utilisé le système au cours de cette période ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="ed2a9-135">Parmi les différents utilisateurs, quels sont ceux qui se sont montrés les plus actifs au cours de cette période ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="ed2a9-136">Les utilisateurs qui passent le plus grand nombre d’appels sont-ils aussi ceux qui participent le plus aux sessions de messagerie instantanée ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="ed2a9-137">Si vous avez besoin de répondre à ce type de question, vous pouvez exporter les données récupérées par les rapports de surveillance dans une feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="ed2a9-138">Vous pouvez alors vous servir de cette feuille de calcul et/ou d’un fichier de valeurs séparées par des virgules (CSV) pour analyser les données de façon plus poussée que dans le rapport d’activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="ed2a9-139">Par exemple, supposons que vous ayez exporté les données du rapport dans Excel, puis dans un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="ed2a9-140">À ce stade, vous pouvez importer les données à partir du. Fichier CSV vers Windows PowerShell en utilisant une commande similaire à celle-ci:</span><span class="sxs-lookup"><span data-stu-id="ed2a9-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="ed2a9-141">Une fois les données importées, vous pouvez utiliser des commandes Windows PowerShell simples pour répondre à vos questions.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="ed2a9-142">Par exemple, cette commande renvoie une liste d’utilisateurs uniques qui ont fait office d’expéditeur (« From user ») dans au moins une session :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="ed2a9-143">En d’autres termes :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="ed2a9-144">Cette commande dresse la liste des utilisateurs individuels (en fonction du nombre total de sessions auxquelles ils ont participé) :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ed2a9-145">Les données renvoyées se présentent ainsi :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="ed2a9-146">Cette commande limite les sessions recensées dans le rapport à celles qui incluaient la modalité audio :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="ed2a9-147">Si vous placez le curseur de la souris sur un ID de diagnostic figurant dans le rapport, une description de cet ID s’affiche dans une info-bulle.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ed2a9-148">Filtres</span><span class="sxs-lookup"><span data-stu-id="ed2a9-148">Filters</span></span>

<span data-ttu-id="ed2a9-p111">Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données renvoyées sur la base d’éléments tels que le type d’activité (à savoir, sessions P2P ou sessions de conférence) ou l’adresse SIP de l’utilisateur (vous permettant d’afficher les activités d’un utilisateur). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="ed2a9-153">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="ed2a9-154">Filtres du rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="ed2a9-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed2a9-155">Nom</span><span class="sxs-lookup"><span data-stu-id="ed2a9-155">Name</span></span></th>
<th><span data-ttu-id="ed2a9-156">Description</span><span class="sxs-lookup"><span data-stu-id="ed2a9-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-157"><strong>De</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p112">Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ed2a9-160">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ed2a9-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ed2a9-p113">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ed2a9-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ed2a9-163">7/17/12012</span></span></p>
<p><span data-ttu-id="ed2a9-164">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ed2a9-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ed2a9-165">7/13/2012</span></span></p>
<p><span data-ttu-id="ed2a9-166">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-167"><strong>À</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p114">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ed2a9-170">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ed2a9-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="ed2a9-p115">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ed2a9-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="ed2a9-173">7/17/12012</span></span></p>
<p><span data-ttu-id="ed2a9-174">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ed2a9-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="ed2a9-175">7/13/2012</span></span></p>
<p><span data-ttu-id="ed2a9-176">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-177"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p116">Type d’activité. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ed2a9-180">[Tous]</span><span class="sxs-lookup"><span data-stu-id="ed2a9-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="ed2a9-181">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="ed2a9-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="ed2a9-182">Conférence</span><span class="sxs-lookup"><span data-stu-id="ed2a9-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-183"><strong>Modalité</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-184">La modalité disponible varie selon le type d’activité sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="ed2a9-185">Si le type d’activité est pair à pair, vous pouvez sélectionner mi. Transfert de fichier; Partage d’application; Téléphonique ou la vidéo comme modalité.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="ed2a9-186">Si le type d’activité est Conférence, vous pouvez sélectionner messagerie instantanée, conférence web, partage d’application; conférence audio/vidéo ou téléconférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-187"><strong>Catégorie de session</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p118">Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ed2a9-190">[Tous]</span><span class="sxs-lookup"><span data-stu-id="ed2a9-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="ed2a9-191">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="ed2a9-191">Success</span></span></p></li>
<li><p><span data-ttu-id="ed2a9-192">Échec attendu</span><span class="sxs-lookup"><span data-stu-id="ed2a9-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="ed2a9-193">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="ed2a9-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="ed2a9-194">Un &quot;échec&quot; attendu est un échec ATTENDU; par exemple, si un utilisateur a défini son statut sur ne pas déranger, vous attendiez qu’il n’y ait aucun appel.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="ed2a9-195">Un &quot;échec&quot; inattendu est une défaillance qui peut se produire dans un système de bon fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="ed2a9-196">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="ed2a9-197">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-198"><strong>Préfixe URI de l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p120">Adresse SIP pour l’utilisateur. Pour afficher exclusivement les enregistrements de l’utilisateur Ken Myer, vous devez entrer l’adresse SIP de Ken Myer. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="ed2a9-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ed2a9-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ed2a9-203">Mesures pour sessions P2P</span><span class="sxs-lookup"><span data-stu-id="ed2a9-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="ed2a9-204">Le tableau ci-dessous liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions P2P (à savoir les sessions impliquant deux participants uniquement).</span><span class="sxs-lookup"><span data-stu-id="ed2a9-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="ed2a9-205">Mesures pour sessions P2P</span><span class="sxs-lookup"><span data-stu-id="ed2a9-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed2a9-206">Nom</span><span class="sxs-lookup"><span data-stu-id="ed2a9-206">Name</span></span></th>
<th><span data-ttu-id="ed2a9-207">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ed2a9-208">Description</span><span class="sxs-lookup"><span data-stu-id="ed2a9-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-209"><strong>Détails</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-210">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-210">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-211">Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de session P2P pour la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-212"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-213">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-214">Adresse SIP de l’utilisateur qui a initié la session P2P.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-215"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-216">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-217">Adresse SIP de l’utilisateur qui s’est joint à la session P2P.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-218"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-219">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p121">Type de communication utilisé dans la session. Par exemple, messagerie instantanée, audio ou transfert de fichier.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-222"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-223">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-224">Date et heure d’envoi de l’invitation initiale à se joindre à la session P2P.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-225"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-226">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-227">Date et heure auxquelles l' &quot;utilisateur&quot; a accepté l’invitation à la session.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-228"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-229">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-230">Date et heure de fin de la session P2P.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-231"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-232">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p122">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ed2a9-235">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="ed2a9-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="ed2a9-236">Le tableau ci-dessous liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions P2P (à savoir les sessions impliquant deux participants uniquement).</span><span class="sxs-lookup"><span data-stu-id="ed2a9-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="ed2a9-237">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="ed2a9-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed2a9-238">Nom</span><span class="sxs-lookup"><span data-stu-id="ed2a9-238">Name</span></span></th>
<th><span data-ttu-id="ed2a9-239">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ed2a9-240">Description</span><span class="sxs-lookup"><span data-stu-id="ed2a9-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-241"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-242">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-243">Identifiant de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-243">Unique conference identifier.</span></span> <span data-ttu-id="ed2a9-244">Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de conférence pour la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="ed2a9-245">Lorsque vous développez cet élément, le rapport vous montre les informations sur les participants à la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="ed2a9-246">Pour plus d’informations, &quot;reportez-vous&quot; à la section métriques pour les participants à la Conférence plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-247"><strong>Organisateur</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-248">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-249">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-251">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-252">Nom du serveur Edge (le cas échéant) utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-253"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-254">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-255">Date et heure de début de la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-256"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-257">Oui</span><span class="sxs-lookup"><span data-stu-id="ed2a9-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-258">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="ed2a9-259">Mesures pour les participants de la conférence</span><span class="sxs-lookup"><span data-stu-id="ed2a9-259">Metrics for conference participants</span></span>

<span data-ttu-id="ed2a9-260">Le tableau ci-dessous répertorie les informations fournies dans le Rapport d’activité de l’utilisateur sur chaque participant d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="ed2a9-261">Mesures pour les participants de la conférence</span><span class="sxs-lookup"><span data-stu-id="ed2a9-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ed2a9-262">Nom</span><span class="sxs-lookup"><span data-stu-id="ed2a9-262">Name</span></span></th>
<th><span data-ttu-id="ed2a9-263">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="ed2a9-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ed2a9-264">Description</span><span class="sxs-lookup"><span data-stu-id="ed2a9-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-265"><strong>Rôle</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-266">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-266">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-267">Rôle de conférence (par exemple, Présentateur) pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-268"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-269">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-269">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-270">Adresse SIP de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-271"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-272">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-272">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-273">Type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-273">Network connection type.</span></span> <span data-ttu-id="ed2a9-274">Par exemple &quot;, de&quot; l’Internal pour la &quot;connexion interne&quot; ou du réseau PSTN pour les utilisateurs rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-275"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-276">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-276">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-277">Date et heure à laquelle l’utilisateur a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ed2a9-278"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-279">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-279">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-280">Date et heure à laquelle l’utilisateur a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ed2a9-281"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="ed2a9-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ed2a9-282">Non</span><span class="sxs-lookup"><span data-stu-id="ed2a9-282">No</span></span></p></td>
<td><p><span data-ttu-id="ed2a9-p125">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</span><span class="sxs-lookup"><span data-stu-id="ed2a9-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

