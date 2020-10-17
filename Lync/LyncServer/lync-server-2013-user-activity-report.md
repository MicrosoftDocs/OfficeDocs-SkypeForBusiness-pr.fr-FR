---
title: 'Lync Server 2013 : rapport d’activité de l’utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36001aaf38dc39d0bb4eb7524e41c616b0a1c160
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530231"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="4b17a-102">Rapport d’activité de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b17a-102">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b17a-103">_**Dernière modification de la rubrique :** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="4b17a-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="4b17a-p101">Le rapport d’activité de l’utilisateur fournit une liste détaillée des sessions d’égal à égal et des sessions de conférence exécutées par vos utilisateurs au cours d’une période donnée. Contrairement à la plupart des rapports de surveillance, le rapport d’activité de l’utilisateur lie chaque appel à des utilisateurs individuels. Par exemple, les sessions d’égal à égal spécifient l’URI SIP de la personne à l’origine de l’appel (utilisateur d’origine) et celle de la personne qui a été appelée (utilisateur de destination). Si vous développez les informations sur une conférence, vous obtiendrez la liste de tous les participants à la conférence, ainsi que le rôle qu’ils ont eu à cette occasion.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="4b17a-p102">Le rapport d’activité de l’utilisateur est parfois appelé « rapport de support technique ». En effet, ce rapport est souvent utilisé par les équipes de support technique pour récupérer les informations de session d’un utilisateur spécifique. Vous pouvez filtrer les appels à destination ou en provenance d’un utilisateur individuel en tapant simplement son URI SIP dans la zone Préfixe d’URI d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="4b17a-111">Dans ce cas, le rapport d’activité de l’utilisateur renverra des informations sur tous les utilisateurs dont l’URI SIP commence par la chaîne spécifiée.</span><span class="sxs-lookup"><span data-stu-id="4b17a-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="4b17a-112">Par exemple, si vous tapez **Ken** dans la zone URI, le rapport d’activité de l’utilisateur localisera **Ken**. Myer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4b17a-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="4b17a-113">Toutefois, il localise également les utilisateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="4b17a-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="4b17a-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b17a-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="4b17a-115">**ken**Burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b17a-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="4b17a-116">**Ken**. Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b17a-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="4b17a-117">**Ken**Nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b17a-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="4b17a-118">Pour vous assurer que les informations uniquement pour Ken Myer sont renvoyées, tapez son URI complet (Ken.Myer@litwareinc.com) dans la zone de recherche ou au moins un type d’URI de Ken afin de le différencier des autres utilisateurs de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b17a-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="4b17a-119">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4b17a-119">For example:</span></span>

<span data-ttu-id="4b17a-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="4b17a-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="4b17a-121">Pour accéder au rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b17a-121">To access the user activity report</span></span>

<span data-ttu-id="4b17a-122">Le rapport d’activité de l’utilisateur est accessible via la page d’accueil des rapports de surveillance.</span><span class="sxs-lookup"><span data-stu-id="4b17a-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4b17a-123">Vous pouvez également accéder au rapport d’activité de l’utilisateur en cliquant sur la mesure URI de l’utilisateur sur le [rapport d’inventaire de téléphonie IP dans Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span><span class="sxs-lookup"><span data-stu-id="4b17a-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="4b17a-124">Si vous cliquez sur URI de la conférence (pour une conférence) dans le rapport d’activité de l’utilisateur, vous accèderez au rapport détaillé de conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="4b17a-125">De même, le fait de cliquer sur la mesure détail pour un appel P2P vous permet d’accéder au [rapport détaillé de session P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span><span class="sxs-lookup"><span data-stu-id="4b17a-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="4b17a-126">Utilisation optimale du rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b17a-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="4b17a-127">Bien que le rapport d’activité de l’utilisateur contienne des informations utiles, il peut parfois être difficile de les localiser.</span><span class="sxs-lookup"><span data-stu-id="4b17a-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="4b17a-128">Par exemple, toutes les activités de l’utilisateur qui ont lieu dans votre organisation pendant une période spécifiée sont incluses dans le rapport d’activité de l’utilisateur ; Cela signifie que, lorsqu’il est inclus dans le rapport, des informations sur les utilisateurs qui ont réellement utilisé Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4b17a-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4b17a-129">Techniquement, il est possible que certaines activités utilisateur ne soient pas enregistrées : tandis que Lync Server s’efforce de conserver des informations sur tous les appels téléphoniques, il est possible qu’un appel ait été effectué sans que les informations relatives à cet appel soient écrites dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4b17a-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="4b17a-130">Lync Server est conçu pour donner un aperçu extrêmement précis mais pas nécessairement parfait de la façon dont Lync Server 2013 est utilisé.</span><span class="sxs-lookup"><span data-stu-id="4b17a-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="4b17a-131">(Le fait qu’il n’existe aucune garantie que 100% de tous les appels sont enregistrés explique pourquoi la surveillance Lync Server ne doit pas être utilisée comme système de facturation.)</span><span class="sxs-lookup"><span data-stu-id="4b17a-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="4b17a-p108">En deuxième lieu, un rapport de surveillance ne peut afficher que 1 000 enregistrements, tout au plus. Ainsi, selon le volume d’activité de vos utilisateurs et la période considérée, votre requête risque de ne pas retourner toutes les données effectivement stockées dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="4b17a-134">Quels sont les utilisateurs qui ont utilisé le système au cours de cette période ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="4b17a-135">Parmi les différents utilisateurs, quels sont ceux qui se sont montrés les plus actifs au cours de cette période ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="4b17a-136">Les utilisateurs qui passent le plus grand nombre d’appels sont-ils aussi ceux qui participent le plus aux sessions de messagerie instantanée ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="4b17a-137">Si vous avez besoin de répondre à ce type de question, vous pouvez exporter les données récupérées par les rapports de surveillance dans une feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="4b17a-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="4b17a-138">Vous pouvez alors vous servir de cette feuille de calcul et/ou d’un fichier de valeurs séparées par des virgules (CSV) pour analyser les données de façon plus poussée que dans le rapport d’activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b17a-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="4b17a-139">Par exemple, supposons que vous avez exporté les données du rapport dans Excel, puis dans un fichier CSV.</span><span class="sxs-lookup"><span data-stu-id="4b17a-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="4b17a-140">À ce stade, vous pouvez importer les données à partir du. CSV vers Windows PowerShell à l’aide d’une commande semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="4b17a-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="4b17a-141">Une fois que les données ont été importées, vous pouvez utiliser des commandes Windows PowerShell simples pour répondre à vos questions.</span><span class="sxs-lookup"><span data-stu-id="4b17a-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="4b17a-142">Par exemple, cette commande retourne une liste d’utilisateurs uniques qui ont fait office d’expéditeur (« From user ») dans au moins une session :</span><span class="sxs-lookup"><span data-stu-id="4b17a-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="4b17a-143">En voici le résultat :</span><span class="sxs-lookup"><span data-stu-id="4b17a-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="4b17a-144">Cette commande dresse la liste des utilisateurs individuels (en fonction du nombre total de sessions auxquelles ils ont participé) :</span><span class="sxs-lookup"><span data-stu-id="4b17a-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="4b17a-145">Les données retournées se présentent ainsi :</span><span class="sxs-lookup"><span data-stu-id="4b17a-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="4b17a-146">Cette commande limite les sessions recensées dans le rapport à celles qui incluaient la modalité audio :</span><span class="sxs-lookup"><span data-stu-id="4b17a-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="4b17a-147">Si vous placez le curseur de la souris sur un ID de diagnostic figurant dans le rapport, une description de cet ID apparaît dans une info-bulle.</span><span class="sxs-lookup"><span data-stu-id="4b17a-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4b17a-148">Filtres</span><span class="sxs-lookup"><span data-stu-id="4b17a-148">Filters</span></span>

<span data-ttu-id="4b17a-p111">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport d’activité de l’utilisateur vous permet de filtrer les données retournées sur la base d’éléments tels que le type d’activité (à savoir, sessions d’égal à égal ou sessions de conférence) ou l’adresse SIP de l’utilisateur (vous permettant d’afficher les activités d’un utilisateur). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4b17a-153">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b17a-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="4b17a-154">Filtres du rapport d’activité de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b17a-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b17a-155">Nom</span><span class="sxs-lookup"><span data-stu-id="4b17a-155">Name</span></span></th>
<th><span data-ttu-id="4b17a-156">Description</span><span class="sxs-lookup"><span data-stu-id="4b17a-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-157"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-p112">Date/heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4b17a-160">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4b17a-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="4b17a-p113">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4b17a-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="4b17a-163">7/17/12012</span></span></p>
<p><span data-ttu-id="4b17a-164">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4b17a-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4b17a-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="4b17a-165">7/13/2012</span></span></p>
<p><span data-ttu-id="4b17a-166">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="4b17a-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-p114">Date/heure de fin de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4b17a-170">17/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="4b17a-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="4b17a-p115">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4b17a-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="4b17a-173">7/17/12012</span></span></p>
<p><span data-ttu-id="4b17a-174">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="4b17a-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4b17a-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="4b17a-175">7/13/2012</span></span></p>
<p><span data-ttu-id="4b17a-176">Les semaines commencent le dimanche et se terminent le samedi.</span><span class="sxs-lookup"><span data-stu-id="4b17a-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-177"><strong>Type d’activité</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-p116">Type d’activité. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b17a-180">Tous les</span><span class="sxs-lookup"><span data-stu-id="4b17a-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="4b17a-181">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="4b17a-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="4b17a-182">Conférence</span><span class="sxs-lookup"><span data-stu-id="4b17a-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-183"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-184">La modalité disponible varie en fonction du type d’activité Select.</span><span class="sxs-lookup"><span data-stu-id="4b17a-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="4b17a-185">Si le type d’activité est égal à égal, vous pouvez sélectionner messagerie instantanée ; Transfert de fichiers ; Partage d’application ; Vocale ou la vidéo comme modalité.</span><span class="sxs-lookup"><span data-stu-id="4b17a-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="4b17a-186">Si le type d’activité est Conférence, vous pouvez sélectionner conférence téléphonique de messagerie instantanée ; Conférence Web ; Partage d’application ; Conférence vocale/vidéo ; ou une conférence téléphonique.</span><span class="sxs-lookup"><span data-stu-id="4b17a-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-187"><strong>Catégorie de session</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-p118">Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b17a-190">Tous les</span><span class="sxs-lookup"><span data-stu-id="4b17a-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="4b17a-191">Opération réussie</span><span class="sxs-lookup"><span data-stu-id="4b17a-191">Success</span></span></p></li>
<li><p><span data-ttu-id="4b17a-192">Échec attendu</span><span class="sxs-lookup"><span data-stu-id="4b17a-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="4b17a-193">Échec inattendu</span><span class="sxs-lookup"><span data-stu-id="4b17a-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="4b17a-194">Un &quot; échec attendu &quot; est un échec qui est susceptible de se produire ; par exemple, si un utilisateur a défini son statut sur ne pas déranger, vous devez attendre l’échec de tout appel à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b17a-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="4b17a-195">Un &quot; échec inattendu &quot; est un échec qui se produit dans le cas d’un système sain.</span><span class="sxs-lookup"><span data-stu-id="4b17a-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="4b17a-196">Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente.</span><span class="sxs-lookup"><span data-stu-id="4b17a-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="4b17a-197">Si cela se produit, l’incident est marqué comme un échec inattendu.</span><span class="sxs-lookup"><span data-stu-id="4b17a-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-198"><strong>Préfixe d’URI de l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-p120">Adresse SIP pour l’utilisateur. Pour afficher exclusivement les enregistrements de l’utilisateur Ken Myer, vous devez entrer l’adresse SIP de Ken Myer. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4b17a-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="4b17a-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4b17a-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4b17a-203">Mesures pour sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="4b17a-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="4b17a-204">Le tableau suivant liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions d’égal à égal (à savoir les sessions impliquant deux participants uniquement).</span><span class="sxs-lookup"><span data-stu-id="4b17a-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="4b17a-205">Mesures pour sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="4b17a-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b17a-206">Nom</span><span class="sxs-lookup"><span data-stu-id="4b17a-206">Name</span></span></th>
<th><span data-ttu-id="4b17a-207">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b17a-208">Description</span><span class="sxs-lookup"><span data-stu-id="4b17a-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-209"><strong>Detail</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-210">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-210">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-211">Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de session d’égal à égal pour la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4b17a-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-212"><strong>De l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-213">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-214">Adresse SIP de l’utilisateur qui a initié la session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b17a-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-215"><strong>À l’utilisateur</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-216">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-217">Adresse SIP de l’utilisateur qui s’est joint à la session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b17a-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-218"><strong>Modalités</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-219">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-p121">Type de communication utilisé dans la session. Par exemple, messagerie instantanée, audio ou transfert de fichier.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-222"><strong>Heure d’invitation</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-223">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-224">Date et heure d’envoi de l’invitation initiale à se joindre à la session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b17a-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-225"><strong>Heure de réponse</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-226">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-227">Date et heure auxquelles l' &quot; &quot; utilisateur a accepté l’invitation à la session.</span><span class="sxs-lookup"><span data-stu-id="4b17a-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-228"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-229">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-230">Date et heure de fin de la session d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="4b17a-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-231"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-232">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-p122">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4b17a-235">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="4b17a-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="4b17a-236">Le tableau suivant liste les informations fournies dans le rapport d’activité de l’utilisateur pour les sessions d’égal à égal (à savoir les sessions impliquant deux participants uniquement).</span><span class="sxs-lookup"><span data-stu-id="4b17a-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="4b17a-237">Mesures pour les sessions de conférence</span><span class="sxs-lookup"><span data-stu-id="4b17a-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b17a-238">Nom</span><span class="sxs-lookup"><span data-stu-id="4b17a-238">Name</span></span></th>
<th><span data-ttu-id="4b17a-239">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b17a-240">Description</span><span class="sxs-lookup"><span data-stu-id="4b17a-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-241"><strong>URI de la conférence</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-242">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-243">Identifiant de conférence unique.</span><span class="sxs-lookup"><span data-stu-id="4b17a-243">Unique conference identifier.</span></span> <span data-ttu-id="4b17a-244">Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport détaillé de conférence pour la session sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4b17a-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="4b17a-245">Lorsque vous développez cet élément, le rapport vous montre les informations sur les participants à la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="4b17a-246">Pour plus d’informations, consultez la &quot; section mesures pour les participants à la Conférence &quot; plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4b17a-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-247"><strong>Organizer</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-248">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-249">Adresse SIP de l’utilisateur qui a organisé la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-251">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-252">Nom du serveur Edge (le cas échéant) utilisé dans la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-253"><strong>Heure de début</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-254">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-255">Date et heure de début de la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-256"><strong>Heure de fin</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-257">Oui</span><span class="sxs-lookup"><span data-stu-id="4b17a-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="4b17a-258">Date et heure de fin de la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="4b17a-259">Mesures pour les participants de la conférence</span><span class="sxs-lookup"><span data-stu-id="4b17a-259">Metrics for conference participants</span></span>

<span data-ttu-id="4b17a-260">Le tableau suivant liste les informations fournies dans le Rapport d’activité de l’utilisateur sur chaque participant d’une conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="4b17a-261">Mesures pour les participants de la conférence</span><span class="sxs-lookup"><span data-stu-id="4b17a-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b17a-262">Nom</span><span class="sxs-lookup"><span data-stu-id="4b17a-262">Name</span></span></th>
<th><span data-ttu-id="4b17a-263">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="4b17a-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b17a-264">Description</span><span class="sxs-lookup"><span data-stu-id="4b17a-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-265"><strong>Role</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-266">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-266">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-267">Rôle de conférence (par exemple, Présentateur) pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4b17a-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-268"><strong>Participant</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-269">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-269">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-270">Adresse SIP de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="4b17a-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-271"><strong>Connectivité</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-272">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-272">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-273">Type de connexion réseau.</span><span class="sxs-lookup"><span data-stu-id="4b17a-273">Network connection type.</span></span> <span data-ttu-id="4b17a-274">Par exemple &quot; from Internal &quot; pour la connexion interne ou &quot; PSTN &quot; pour les utilisateurs d’appels entrants.</span><span class="sxs-lookup"><span data-stu-id="4b17a-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-275"><strong>Heure d’arrivée</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-276">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-276">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-277">Date et heure à laquelle l’utilisateur a rejoint la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b17a-278"><strong>Heure de départ</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-279">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-279">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-280">Date et heure à laquelle l’utilisateur a quitté la conférence.</span><span class="sxs-lookup"><span data-stu-id="4b17a-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b17a-281"><strong>ID de diagnostic</strong></span><span class="sxs-lookup"><span data-stu-id="4b17a-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="4b17a-282">Non</span><span class="sxs-lookup"><span data-stu-id="4b17a-282">No</span></span></p></td>
<td><p><span data-ttu-id="4b17a-p125">Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</span><span class="sxs-lookup"><span data-stu-id="4b17a-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

