---
title: 'Lync Server 2013 : rapport d’enregistrement de l’utilisateur'
description: 'Lync Server 2013 : rapport d’enregistrement de l’utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569750"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="967f9-103">Rapport d’enregistrement de l’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="967f9-103">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="967f9-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="967f9-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="967f9-105">Le rapport d’enregistrement de l’utilisateur fournit une vue d’ensemble de l’activité d’ouverture de session de l’utilisateur, notamment des informations sur le nombre d’utilisateurs connectés à Microsoft Lync Server 2013 pendant une période spécifiée (toutes les heures, tous les jours, toutes les semaines, tous les mois).</span><span class="sxs-lookup"><span data-stu-id="967f9-105">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="967f9-106">N’oubliez pas que le rapport vous indique uniquement le nombre de personnes qui ont ouvert une session.</span><span class="sxs-lookup"><span data-stu-id="967f9-106">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="967f9-107">Il ne vous apprend pas *qui* a ouvert une session.</span><span class="sxs-lookup"><span data-stu-id="967f9-107">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="967f9-108">Les rapports de surveillance ne fournissent pas d’informations sur les utilisateurs spécifiques qui utilisent Lync Server 2013 (et ceux qui ne le sont pas).</span><span class="sxs-lookup"><span data-stu-id="967f9-108">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="967f9-109">Vous pouvez toutefois obtenir des informations approximatives sur les utilisateurs à l’aide du rapport d’activité de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967f9-109">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="967f9-110">Lorsqu’il donne des informations sur les ouvertures de session d’utilisateurs, le rapport d’enregistrement de l’utilisateur établit deux distinctions importantes.</span><span class="sxs-lookup"><span data-stu-id="967f9-110">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="967f9-111">Tout d’abord, il décompose les ouvertures de session en deux catégories principales : ouvertures de session internes et ouvertures de session externes.</span><span class="sxs-lookup"><span data-stu-id="967f9-111">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="967f9-112">Les ouvertures de session internes représentent les utilisateurs qui ont ouvert une session à l’intérieur du pare-feu de votre organisation (c’est-à-dire tout en étant connecté au réseau d’entreprise).</span><span class="sxs-lookup"><span data-stu-id="967f9-112">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="967f9-113">Les ouvertures de session externes représentent les utilisateurs qui se sont connectés depuis l’extérieur du pare-feu via un serveur Edge (par exemple, un utilisateur qui a ouvert une session à partir d’un cybercafé sur Internet compte comme une ouverture de session externe).</span><span class="sxs-lookup"><span data-stu-id="967f9-113">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="967f9-114">Si vous devez connaître le nombre d’utilisateurs qui ouvrent une session à l’extérieur du pare-feu, le rapport d’enregistrement de l’utilisateur peut vous donner cette information.</span><span class="sxs-lookup"><span data-stu-id="967f9-114">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="967f9-115">En outre, le rapport d’enregistrement de l’utilisateur note le nombre d’utilisateurs *actifs* qui étaient présents pendant une période donnée.</span><span class="sxs-lookup"><span data-stu-id="967f9-115">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="967f9-116">Un utilisateur actif est un utilisateur qui a participé à une session de messagerie instantanée (IM), a participé à une réunion Lync, a effectué ou reçu un appel téléphonique ou utilisé Lync Server pendant cette période de temps.</span><span class="sxs-lookup"><span data-stu-id="967f9-116">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="967f9-117">Un utilisateur actif est différent d’un utilisateur qui a ouvert une session, mais qui n’a jamais utilisé le système.</span><span class="sxs-lookup"><span data-stu-id="967f9-117">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="967f9-118">Accès au rapport d’enregistrement de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="967f9-118">Accessing the User Registration Report</span></span>

<span data-ttu-id="967f9-p104">Vous ne pouvez accéder au rapport d’enregistrement de l’utilisateur qu’à partir de la page d’accueil des rapports de surveillance. Le rapport d’enregistrement de l’utilisateur n’est lié à aucun autre rapport.</span><span class="sxs-lookup"><span data-stu-id="967f9-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="967f9-121">Utilisation optimale du rapport d’enregistrement de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="967f9-121">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="967f9-122">Une fois que vous avez déployé Lync Server, une question fréquemment posée est la suivante : Comment savoir si mes utilisateurs utilisent réellement cette nouvelle technologie ?</span><span class="sxs-lookup"><span data-stu-id="967f9-122">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="967f9-123">Bien qu’il soit quelque peu limité à cet égard, le rapport d’enregistrement de l’utilisateur peut vous aider à répondre à cette question.</span><span class="sxs-lookup"><span data-stu-id="967f9-123">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="967f9-124">Pour déterminer si les utilisateurs utilisent ou non Lync Server, vous devez effectuer deux opérations.</span><span class="sxs-lookup"><span data-stu-id="967f9-124">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="967f9-125">Récupérez d’abord la valeur de la mesure Utilisateurs uniques par ouverture de session dans le rapport d’enregistrement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967f9-125">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="967f9-126">Cette valeur indique le nombre de personnes qui ont ouvert une session sur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="967f9-126">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="967f9-127">Par comparaison, la mesure nombre total d’ouvertures de session indique le nombre total de fois qu’une personne s’est connectée à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="967f9-127">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="967f9-128">Par exemple, supposons que Ken Myer s’est connecté à Lync Server cinq fois par jour.</span><span class="sxs-lookup"><span data-stu-id="967f9-128">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="967f9-129">Dans ce cas, cinq ouvertures de session distinctes sont comptabilisées pour Ken Myer dans la mesure Nombre total d’ouvertures de session, mais une seule ouverture de session est comptabilisée dans la mesure Utilisateurs uniques par ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="967f9-129">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="967f9-130">De même, il n’est pas rare qu’un utilisateur ouvre une session sur plusieurs périphériques ou depuis plusieurs emplacements.</span><span class="sxs-lookup"><span data-stu-id="967f9-130">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="967f9-131">Par exemple, un utilisateur peut se connecter à l’aide de son ordinateur de bureau, son ordinateur portable, et il peut disposer d’un téléphone IP qui se connecte automatiquement à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="967f9-131">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="967f9-132">Dans cet exemple, nous avons un utilisateur unique avec trois ouvertures de session.</span><span class="sxs-lookup"><span data-stu-id="967f9-132">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="967f9-133">Pour mieux expliquer la différence entre le nombre total d’ouvertures de session et les utilisateurs uniques par ouverture de session, examinez les ouvertures de session pour une période donnée dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="967f9-133">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="967f9-134">Utilisateur</span><span class="sxs-lookup"><span data-stu-id="967f9-134">User</span></span></th>
<th><span data-ttu-id="967f9-135">Date/heure d’ouverture de session</span><span class="sxs-lookup"><span data-stu-id="967f9-135">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="967f9-136">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="967f9-136">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="967f9-137">7/7/2012 8 h 45</span><span class="sxs-lookup"><span data-stu-id="967f9-137">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-138">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="967f9-138">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="967f9-139">7/7/2012 8 h 46</span><span class="sxs-lookup"><span data-stu-id="967f9-139">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967f9-140">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="967f9-140">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="967f9-141">7/7/2012 9 h 17</span><span class="sxs-lookup"><span data-stu-id="967f9-141">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-142">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="967f9-142">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="967f9-143">7/7/2012 9 h 22</span><span class="sxs-lookup"><span data-stu-id="967f9-143">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967f9-144">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="967f9-144">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="967f9-145">7/7/2012 9 h 31</span><span class="sxs-lookup"><span data-stu-id="967f9-145">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="967f9-p107">Notez qu’il y a cinq ouvertures de session au total, mais qu’il n’y a que deux utilisateurs uniques par ouverture de session : Ken Myer (qui a ouvert une session trois fois) et Pilar Ackerman (qui a ouvert une session deux fois). Ceci illustre la différence entre les ouvertures de session et les utilisateurs uniques par ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="967f9-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="967f9-148">En plus de connaître le nombre d’ouvertures de session uniques, vous devez connaître le nombre total d’utilisateurs qui ont été activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="967f9-148">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="967f9-149">Cette valeur peut être récupérée en ouvrant Lync Server 2013 Management Shell et en exécutant la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="967f9-149">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="967f9-150">Si la commande précédente renvoie la valeur 1 236 et que la mesure utilisateurs uniques de l’ouverture de session renvoie une valeur moyenne de 667, cela indique qu’un peu plus de la moitié de vos utilisateurs permettent à Lync de se connecter en réalité au système chaque jour (c’est-à-dire, 667 divisé par 1 236, soit environ 54%).</span><span class="sxs-lookup"><span data-stu-id="967f9-150">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="967f9-151">Gardez à l’esprit que les mesures d’ouverture de session enregistrent les utilisateurs qui ont ouvert une session pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="967f9-151">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="967f9-152">Elles ne gardent pas trace des utilisateurs qui avaient déjà ouvert une session sur le système.</span><span class="sxs-lookup"><span data-stu-id="967f9-152">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="967f9-153">Par exemple, si votre mesure Utilisateurs uniques par ouverture de session indique 667 ouvertures de session et que vous avez 1 236 utilisateurs, cela suggère qu’environ la moitié de vos utilisateurs ouvrent une session sur le système.</span><span class="sxs-lookup"><span data-stu-id="967f9-153">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="967f9-154">Cependant, supposons que 300 utilisateurs avaient déjà ouvert une session sur le système au moment où vous avez commencé à regarder les données d’ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="967f9-154">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="967f9-155">Cela signifie que vous disposiez en réalité de près de 1 000 utilisateurs connectés à Lync Server, ce qui signifie que plus près de 80% de vos utilisateurs étaient connectés.</span><span class="sxs-lookup"><span data-stu-id="967f9-155">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="967f9-156">Vous devez également comparer la valeur Utilisateurs uniques par ouverture de session avec la valeur de la mesure Utilisateurs actifs uniques.</span><span class="sxs-lookup"><span data-stu-id="967f9-156">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="967f9-157">La mesure utilisateurs actifs uniques indique le nombre d’utilisateurs uniques qui ont réellement utilisé Lync Server : ils ont effectué un appel téléphonique, ils ont rejoint une réunion Lync ou ont participé à une session de messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="967f9-157">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="967f9-158">Il s’agit d’informations utiles, car Microsoft Lync 2013 peut être configuré pour démarrer automatiquement chaque fois qu’un utilisateur démarre Windows.</span><span class="sxs-lookup"><span data-stu-id="967f9-158">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="967f9-159">Pour cette raison, vous avez peut-être un grand nombre d’utilisateurs qui se connectent automatiquement à Lync lorsqu’ils se connectent à Windows chaque jour, mais qui n’utilisent jamais en réalité Lync Server pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="967f9-159">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="967f9-160">La mesure utilisateurs actifs uniques fournit également des données plus significatives dans une organisation où les utilisateurs ne se déconnectent généralement pas de Windows à la fin de la journée.</span><span class="sxs-lookup"><span data-stu-id="967f9-160">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="967f9-161">Au lieu de cela, ils verrouillent leur ordinateur et laissent Windows et Lync en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="967f9-161">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="967f9-162">Dans ce cas, vous pouvez vous retrouver avec un nombre d’ouvertures de session par jour très restreint, car vos utilisateurs ont ouvert leur session plusieurs jours auparavant et ne l’ont jamais fermée.</span><span class="sxs-lookup"><span data-stu-id="967f9-162">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="967f9-163">Toutefois, les utilisateurs actifs uniques indiquent si les utilisateurs utilisent Lync ou un autre client Lync Server activement.</span><span class="sxs-lookup"><span data-stu-id="967f9-163">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="967f9-164">Filtres</span><span class="sxs-lookup"><span data-stu-id="967f9-164">Filters</span></span>

<span data-ttu-id="967f9-165">Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="967f9-165">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="967f9-166">Par exemple, le rapport d’enregistrement de l’utilisateur vous permet d’afficher les données de l’ensemble de votre pool de serveurs d’inscriptions et de vos serveurs Edge ou d’afficher les données d’un pool individuel.</span><span class="sxs-lookup"><span data-stu-id="967f9-166">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="967f9-167">Vous pouvez également choisir le mode de groupement des données.</span><span class="sxs-lookup"><span data-stu-id="967f9-167">You can also choose how data should be grouped.</span></span> <span data-ttu-id="967f9-168">Dans ce cas, les enregistrements sont groupés par heure, jour, semaine ou mois.</span><span class="sxs-lookup"><span data-stu-id="967f9-168">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="967f9-169">Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’enregistrement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967f9-169">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="967f9-170">Filtres du rapport d’enregistrement de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="967f9-170">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="967f9-171">Nom</span><span class="sxs-lookup"><span data-stu-id="967f9-171">Name</span></span></th>
<th><span data-ttu-id="967f9-172">Description</span><span class="sxs-lookup"><span data-stu-id="967f9-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="967f9-173"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-173"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-p113">Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</span><span class="sxs-lookup"><span data-stu-id="967f9-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="967f9-176">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="967f9-176">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="967f9-p114">Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="967f9-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="967f9-179">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="967f9-179">7/7/2012</span></span></p>
<p><span data-ttu-id="967f9-180">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="967f9-180">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="967f9-181">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="967f9-181">7/3/2012</span></span></p>
<p><span data-ttu-id="967f9-182">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="967f9-182">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-183"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-183"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-p115">Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</span><span class="sxs-lookup"><span data-stu-id="967f9-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="967f9-186">07/07/2012 13:00</span><span class="sxs-lookup"><span data-stu-id="967f9-186">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="967f9-p116">Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</span><span class="sxs-lookup"><span data-stu-id="967f9-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="967f9-189">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="967f9-189">7/7/2012</span></span></p>
<p><span data-ttu-id="967f9-190">Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</span><span class="sxs-lookup"><span data-stu-id="967f9-190">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="967f9-191">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="967f9-191">7/3/2012</span></span></p>
<p><span data-ttu-id="967f9-192">Les semaines s’étalent toujours du dimanche au samedi.</span><span class="sxs-lookup"><span data-stu-id="967f9-192">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967f9-193"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-193"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-p117">Intervalle de temps. Sélectionnez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="967f9-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="967f9-196">Toutes les heures (il est possible d’afficher un maximum de 25 heures)</span><span class="sxs-lookup"><span data-stu-id="967f9-196">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="967f9-197">Tous les jours (il est possible d’afficher un maximum de 31 jours)</span><span class="sxs-lookup"><span data-stu-id="967f9-197">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="967f9-198">Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</span><span class="sxs-lookup"><span data-stu-id="967f9-198">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="967f9-199">Tous les mois (il est possible d’afficher un maximum de 12 mois)</span><span class="sxs-lookup"><span data-stu-id="967f9-199">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="967f9-p118">Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début de 7/8/2012 et une date de fin de 28/9/2012, les données sont affichées pour les jours compris entre le 7/8/2012 à 12 h 00 et le 7/9/2012 à 12 h 00 (c’est-à-dire un total de 31 jours de données).</span><span class="sxs-lookup"><span data-stu-id="967f9-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-202"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-202"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-203">Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="967f9-203">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="967f9-204">Vous pouvez soit sélectionner un pool individuel soit cliquer sur <strong>[Tous]</strong> pour afficher les données pour tous les pools.</span><span class="sxs-lookup"><span data-stu-id="967f9-204">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="967f9-205">La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.</span><span class="sxs-lookup"><span data-stu-id="967f9-205">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="967f9-206">Mesures</span><span class="sxs-lookup"><span data-stu-id="967f9-206">Metrics</span></span>

<span data-ttu-id="967f9-207">Le tableau qui suit répertorie les informations fournies dans le rapport d’enregistrement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="967f9-207">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="967f9-208">Mesures du rapport d’enregistrement de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="967f9-208">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="967f9-209">Nom</span><span class="sxs-lookup"><span data-stu-id="967f9-209">Name</span></span></th>
<th><span data-ttu-id="967f9-210">Est-il possible d’effectuer un tri sur cet élément ?</span><span class="sxs-lookup"><span data-stu-id="967f9-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="967f9-211">Description</span><span class="sxs-lookup"><span data-stu-id="967f9-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="967f9-212"><strong>Toutes les heures</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="967f9-213"><strong>Journalière</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="967f9-214"><strong>Hebdomadaire</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="967f9-215"><strong>Mensuelle</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-216">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-216">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-p120">Indique l’intervalle de temps que vous avez sélectionné sur la barre d’outils du filtre. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher les informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, vous voyez un décompte horaire de l’activité d’enregistrement de l’utilisateur pour cette date.</span><span class="sxs-lookup"><span data-stu-id="967f9-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-220"><strong>Nombre total d’ouvertures de sessions</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-220"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-221">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-221">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-222">Nombre total d’ouvertures de sessions réussies.</span><span class="sxs-lookup"><span data-stu-id="967f9-222">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967f9-223"><strong>Ouvertures de sessions internes</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-223"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-224">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-224">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-225">Nombre total d’ouvertures de sessions dans le réseau interne.</span><span class="sxs-lookup"><span data-stu-id="967f9-225">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-226"><strong>Ouvertures de sessions externes</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-226"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-227">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-227">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-228">Nombre total d’ouvertures de sessions de l’extérieur du réseau interne, à l’aide du serveur Edge.</span><span class="sxs-lookup"><span data-stu-id="967f9-228">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="967f9-229"><strong>Utilisateurs uniques par ouverture de session</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-229"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-230">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-230">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-p121">Nombre total d’utilisateurs qui ont ouvert au moins une session. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.</span><span class="sxs-lookup"><span data-stu-id="967f9-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="967f9-233"><strong>Utilisateurs actifs uniques</strong></span><span class="sxs-lookup"><span data-stu-id="967f9-233"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="967f9-234">Non</span><span class="sxs-lookup"><span data-stu-id="967f9-234">No</span></span></p></td>
<td><p><span data-ttu-id="967f9-p122">Nombre total d’utilisateurs qui ont été impliqués dans une session d’égal à égal ou de conférence. Un utilisateur qui a ouvert plusieurs sessions compte pour un utilisateur, exactement comme une personne qui a ouvert une seule session.</span><span class="sxs-lookup"><span data-stu-id="967f9-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

