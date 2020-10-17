---
title: 'Lync Server 2013 : utilisation du tableau de bord de suivi'
description: 'Lync Server 2013 : utilisation du tableau de bord de suivi.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8a68fa1e55b7d0b8305c53802ddabaa904fa214
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556040"
---
# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="1b25f-103">Utilisation du tableau de bord de suivi dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b25f-103">Using the Monitoring Dashboard in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b25f-104">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1b25f-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1b25f-105">Le tableau de bord de suivi fournit aux administrateurs une vue d’ensemble rapide de l’État et de l’utilisation du système de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b25f-105">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="1b25f-106">Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés et pour ce faire en affichant soit :</span><span class="sxs-lookup"><span data-stu-id="1b25f-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="1b25f-107">Totaux du jour actuel.</span><span class="sxs-lookup"><span data-stu-id="1b25f-107">Totals for the current day.</span></span> <span data-ttu-id="1b25f-108">Notez que les valeurs affichées pour le jour actuel représentent des données qui ont été enregistrées de minuit à l’heure actuelle (en fonction de l’heure locale du serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="1b25f-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="1b25f-109">Cela signifie que vous allez généralement consulter les données d’une journée partielle et non pendant une période de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="1b25f-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="1b25f-110">Par exemple, si l’heure locale du serveur est 8:00 AM, vous pouvez voir huit heures de données, car il y a huit heures entre minuit et l’heure actuelle de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="1b25f-110">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="1b25f-111">Les totaux de la semaine, et les totaux de la tendance des six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="1b25f-111">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="1b25f-112">Les totaux du mois, et les totaux de la tendance des six mois précédents (pour l’utilisation du système uniquement).</span><span class="sxs-lookup"><span data-stu-id="1b25f-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="1b25f-113">Notez que vous pouvez utiliser la cmdlet [Get-applet csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) pour renvoyer l’URL utilisée pour accéder aux rapports de surveillance Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="1b25f-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="1b25f-114">Par défaut, le tableau de bord de suivi affiche les données des mesures suivantes pour la semaine en cours (et les totaux de la tendance des six semaines précédentes) :</span><span class="sxs-lookup"><span data-stu-id="1b25f-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="1b25f-115">Mesures d’utilisation du système</span><span class="sxs-lookup"><span data-stu-id="1b25f-115">System Usage Metrics</span></span>

<span data-ttu-id="1b25f-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="1b25f-116">**Registration**</span></span>

  - <span data-ttu-id="1b25f-117">Ouvertures de session utilisateur uniques</span><span class="sxs-lookup"><span data-stu-id="1b25f-117">Unique user logons</span></span>

<span data-ttu-id="1b25f-118">**Pair à pair**</span><span class="sxs-lookup"><span data-stu-id="1b25f-118">**Peer-to-peer**</span></span>

  - <span data-ttu-id="1b25f-119">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="1b25f-119">Total sessions</span></span>

  - <span data-ttu-id="1b25f-120">Sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="1b25f-120">IM sessions</span></span>

  - <span data-ttu-id="1b25f-121">Sessions audio</span><span class="sxs-lookup"><span data-stu-id="1b25f-121">Audio sessions</span></span>

  - <span data-ttu-id="1b25f-122">Sessions vidéo</span><span class="sxs-lookup"><span data-stu-id="1b25f-122">Video sessions</span></span>

  - <span data-ttu-id="1b25f-123">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="1b25f-123">Application sharing</span></span>

  - <span data-ttu-id="1b25f-124">Nombre total de minutes de session audio</span><span class="sxs-lookup"><span data-stu-id="1b25f-124">Total audio session minutes</span></span>

  - <span data-ttu-id="1b25f-125">Nombre moyen de minutes par session audio</span><span class="sxs-lookup"><span data-stu-id="1b25f-125">Avg. audio session minutes</span></span>

<span data-ttu-id="1b25f-126">**Conférence**</span><span class="sxs-lookup"><span data-stu-id="1b25f-126">**Conference**</span></span>

  - <span data-ttu-id="1b25f-127">Nombre total de conférences</span><span class="sxs-lookup"><span data-stu-id="1b25f-127">Total conferences</span></span>

  - <span data-ttu-id="1b25f-128">Conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="1b25f-128">IM conferences</span></span>

  - <span data-ttu-id="1b25f-129">Conférences A/V</span><span class="sxs-lookup"><span data-stu-id="1b25f-129">A/V conferences</span></span>

  - <span data-ttu-id="1b25f-130">Conférences de partage d’application</span><span class="sxs-lookup"><span data-stu-id="1b25f-130">Application sharing conferences</span></span>

  - <span data-ttu-id="1b25f-131">Conférences Web</span><span class="sxs-lookup"><span data-stu-id="1b25f-131">Web conferences</span></span>

  - <span data-ttu-id="1b25f-132">Nombre total de organisateurs</span><span class="sxs-lookup"><span data-stu-id="1b25f-132">Total organizers</span></span>

  - <span data-ttu-id="1b25f-133">Nombre total de minutes par conférence A/V</span><span class="sxs-lookup"><span data-stu-id="1b25f-133">Total A/V conference minutes</span></span>

  - <span data-ttu-id="1b25f-134">Nbre. Minutes de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="1b25f-134">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="1b25f-135">Nombre total de conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="1b25f-135">Total PSTN conferences</span></span>

  - <span data-ttu-id="1b25f-136">Nombre total de participants PSTN</span><span class="sxs-lookup"><span data-stu-id="1b25f-136">Total PSTN participants</span></span>

  - <span data-ttu-id="1b25f-137">Nombre total de minutes par participant PSTN</span><span class="sxs-lookup"><span data-stu-id="1b25f-137">Total PSTN participant minutes</span></span>

<span data-ttu-id="1b25f-138">Outre les mesures d’utilisation du système, les mesures suivantes affichent le total du jour actuel et des six jours précédents (si vous sélectionnez **affichage hebdomadaire**) ou pour la semaine en cours et les six dernières semaines si vous sélectionnez **affichage mensuel**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="1b25f-139">Diagnostics des appels de Per-User</span><span class="sxs-lookup"><span data-stu-id="1b25f-139">Per-User Call Diagnostics</span></span>

<span data-ttu-id="1b25f-140">**Utilisateurs avec des échecs d’appel**</span><span class="sxs-lookup"><span data-stu-id="1b25f-140">**Users with call failures**</span></span>

  - <span data-ttu-id="1b25f-141">Nombre total d’utilisateurs avec des échecs d’appel</span><span class="sxs-lookup"><span data-stu-id="1b25f-141">Total users with call failures</span></span>

  - <span data-ttu-id="1b25f-142">Organisateurs de conférence avec des échecs d’appel</span><span class="sxs-lookup"><span data-stu-id="1b25f-142">Conference organizers with call failures</span></span>

<span data-ttu-id="1b25f-143">**Utilisateurs avec des appels de qualité médiocre**</span><span class="sxs-lookup"><span data-stu-id="1b25f-143">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="1b25f-144">Nombre total d’utilisateurs avec des appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-144">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="1b25f-145">Diagnostics des appels</span><span class="sxs-lookup"><span data-stu-id="1b25f-145">Call Diagnostics</span></span>

<span data-ttu-id="1b25f-146">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="1b25f-146">Peer-to-peer</span></span>

  - <span data-ttu-id="1b25f-147">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="1b25f-147">Total failures</span></span>

  - <span data-ttu-id="1b25f-148">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="1b25f-148">Overall failure rate</span></span>

  - <span data-ttu-id="1b25f-149">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="1b25f-149">IM failure rate</span></span>

  - <span data-ttu-id="1b25f-150">Taux d’échec audio</span><span class="sxs-lookup"><span data-stu-id="1b25f-150">Audio failure rate</span></span>

  - <span data-ttu-id="1b25f-151">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="1b25f-151">Application sharing failure rate</span></span>

<span data-ttu-id="1b25f-152">Conférence</span><span class="sxs-lookup"><span data-stu-id="1b25f-152">Conference</span></span>

  - <span data-ttu-id="1b25f-153">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="1b25f-153">Total failures</span></span>

  - <span data-ttu-id="1b25f-154">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="1b25f-154">Overall failure rate</span></span>

  - <span data-ttu-id="1b25f-155">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="1b25f-155">IM failure rate</span></span>

  - <span data-ttu-id="1b25f-156">Taux d’échec A/V</span><span class="sxs-lookup"><span data-stu-id="1b25f-156">A/V failure rate</span></span>

  - <span data-ttu-id="1b25f-157">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="1b25f-157">Application sharing failure rate</span></span>

<span data-ttu-id="1b25f-158">Cinq principaux serveurs par sessions ayant échoué</span><span class="sxs-lookup"><span data-stu-id="1b25f-158">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="1b25f-159">Diagnostic de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="1b25f-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="1b25f-160">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="1b25f-160">Peer-to-peer</span></span>

  - <span data-ttu-id="1b25f-161">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-161">Total poor quality calls</span></span>

  - <span data-ttu-id="1b25f-162">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-162">Poor quality call percentage</span></span>

  - <span data-ttu-id="1b25f-163">Appels RTC avec une qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-163">PSTN calls with poor quality</span></span>

<span data-ttu-id="1b25f-164">Conférence</span><span class="sxs-lookup"><span data-stu-id="1b25f-164">Conference</span></span>

  - <span data-ttu-id="1b25f-165">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-165">Total poor quality calls</span></span>

  - <span data-ttu-id="1b25f-166">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-166">Poor quality call percentage</span></span>

  - <span data-ttu-id="1b25f-167">Appels RTC avec une qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-167">PSTN calls with poor quality</span></span>

<span data-ttu-id="1b25f-168">Serveurs les plus défavorables par pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="1b25f-168">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="1b25f-169">Utilisation du tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="1b25f-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="1b25f-170">Comme indiqué plus haut, par défaut, les totaux sont affichés pour la semaine en cours et les valeurs de tendance sont affichées pour les six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="1b25f-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="1b25f-171">Si vous préférez afficher les totaux pour le mois en cours (ainsi que les valeurs de tendance pour les six derniers mois), cliquez sur le lien **affichage mensuel** dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="1b25f-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="1b25f-172">Si vous décidez d’afficher les totaux mensuels, le texte du lien prend la forme **affichage hebdomadaire**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="1b25f-173">Vous pouvez revenir à la vue hebdomadaire en cliquant sur ce lien.</span><span class="sxs-lookup"><span data-stu-id="1b25f-173">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1b25f-174">Le tableau de bord de suivi vous limite à consulter les totaux de la semaine (ou du mois) en cours et les valeurs de tendance pour les six semaines (ou les mois précédents).</span><span class="sxs-lookup"><span data-stu-id="1b25f-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="1b25f-175">Vous ne pouvez pas modifier ces dates et heures.</span><span class="sxs-lookup"><span data-stu-id="1b25f-175">You cannot change these dates and times.</span></span> <span data-ttu-id="1b25f-176">Par exemple, vous ne pouvez pas utiliser le tableau de bord pour afficher les totaux du rapport pour la période commençant neuf mois plus tôt.</span><span class="sxs-lookup"><span data-stu-id="1b25f-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="1b25f-177">Les valeurs affichées dans les colonnes **cette semaine**, **ce mois**-ci ou **aujourd’hui** vous permettent d’accéder à des informations plus détaillées sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="1b25f-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="1b25f-178">N’oubliez pas que le nom de la colonne et les valeurs affichées dans cette colonne diffèrent souvent en fonction de la mesure choisie et selon que vous avez sélectionné la vue hebdomadaire ou mensuelle.</span><span class="sxs-lookup"><span data-stu-id="1b25f-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="1b25f-179">Par exemple, si vous cliquez sur les totaux affichés pour la mesure **ouvertures de session utilisateur uniques** , le **rapport d’enregistrement** de l’utilisateur s’affiche pour la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="1b25f-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="1b25f-180">Vous pouvez revenir au tableau de bord de suivi à tout moment en cliquant sur **tableau de bord**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1b25f-181">Vous pouvez également accéder à la page d’accueil des rapports du serveur de surveillance en cliquant sur le lien <STRONG>rapports</STRONG> dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="1b25f-181">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="1b25f-182">La colonne **tendance** affiche un graphique linéaire qui indique les totaux des six dernières semaines (ou, en fonction de la mesure et de l’intervalle de temps, des six derniers jours ou des six derniers mois).</span><span class="sxs-lookup"><span data-stu-id="1b25f-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="1b25f-183">Ces graphiques linéaires affichent un point de données sans nom pour chaque période (par exemple, un point de données sans nom pour chacune des six semaines précédentes).</span><span class="sxs-lookup"><span data-stu-id="1b25f-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="1b25f-184">Toutefois, vous pouvez récupérer les valeurs réelles de ces graphiques en maintenant le pointeur de la souris sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="1b25f-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="1b25f-185">Dans ce cas, une info-bulle vous indique les valeurs maximale et minimale dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="1b25f-185">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="1b25f-186">Exportation de données à partir du tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="1b25f-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="1b25f-187">Le tableau de bord de suivi offre plusieurs méthodes pour exporter l’affichage actuel du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="1b25f-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="1b25f-188">Dans la barre d’outils Tableau de bord, une icône ressemblant à une disquette avec une flèche verte s’affiche.</span><span class="sxs-lookup"><span data-stu-id="1b25f-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="1b25f-189">Si vous cliquez sur cette icône, une liste déroulante s’affiche pour vous donner les formats d’exportation de données suivants :</span><span class="sxs-lookup"><span data-stu-id="1b25f-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="1b25f-190">fichier XML avec données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="1b25f-190">XML file with report data</span></span>

  - <span data-ttu-id="1b25f-191">fichier CSV (valeurs séparées par des virgules) ;</span><span class="sxs-lookup"><span data-stu-id="1b25f-191">CSV (comma delimited)</span></span>

  - <span data-ttu-id="1b25f-192">PDF</span><span class="sxs-lookup"><span data-stu-id="1b25f-192">PDF</span></span>

  - <span data-ttu-id="1b25f-193">fichier MHTML (archive web) ;</span><span class="sxs-lookup"><span data-stu-id="1b25f-193">MHTML (web archive)</span></span>

  - <span data-ttu-id="1b25f-194">Excel</span><span class="sxs-lookup"><span data-stu-id="1b25f-194">Excel</span></span>

  - <span data-ttu-id="1b25f-195">fichier TIFF ;</span><span class="sxs-lookup"><span data-stu-id="1b25f-195">TIFF file</span></span>

  - <span data-ttu-id="1b25f-196">Word</span><span class="sxs-lookup"><span data-stu-id="1b25f-196">Word</span></span>

<span data-ttu-id="1b25f-197">Pour exporter l’affichage actuel du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée.</span><span class="sxs-lookup"><span data-stu-id="1b25f-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="1b25f-198">Lync Server 2013 génère un rapport au format spécifié, puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="1b25f-198">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="1b25f-199">Notez que, par défaut, Lync Server titres le **tableau de bord de suivi** des rapports et l’enregistre dans votre dossier téléchargements.</span><span class="sxs-lookup"><span data-stu-id="1b25f-199">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="1b25f-200">Pour donner un nom différent à l’État ou pour le stocker dans un autre dossier, cliquez sur la flèche en regard du bouton **Enregistrer** , puis cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="1b25f-201">Si le tableau de bord de **suivi** des noms est correct et que le rapport est enregistré dans le dossier downloads, vous pouvez simplement cliquer sur le bouton **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="1b25f-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="1b25f-202">Il est possible que, lorsque vous essayez d’exporter des données de tableau de bord, une boîte de dialogue **alerte de sécurité** s’affiche en même temps que le message « vos paramètres actuels n’autorisent pas le téléchargement de ce fichier. »</span><span class="sxs-lookup"><span data-stu-id="1b25f-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="1b25f-203">Dans ce cas, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1b25f-203">If that occurs, do the following:</span></span>

  - <span data-ttu-id="1b25f-204">Dans Internet Explorer, sélectionnez **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-204">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="1b25f-205">Dans la boîte de dialogue **Options Internet** , sous l’onglet **sécurité** , cliquez sur **sites de confiance** , puis sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="1b25f-206">Dans la boîte de dialogue **sites de confiance** , cliquez sur **Ajouter** pour ajouter le serveur Lync Server 2013 exécutant Lync Server 2013 rapports aux collections de sites Web de confiance.</span><span class="sxs-lookup"><span data-stu-id="1b25f-206">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="1b25f-207">Cliquez sur **Fermer** , puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b25f-207">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="1b25f-208">Vous devrez ensuite actualiser le tableau de bord de suivi pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="1b25f-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="1b25f-209">Pour ce faire, appuyez sur F5 ou cliquez sur l’icône **Actualiser** de la barre d’outils Tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="1b25f-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="1b25f-210">(L’icône d' **actualisation** est un cercle avec une paire de flèches vertes.)</span><span class="sxs-lookup"><span data-stu-id="1b25f-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="1b25f-211">Vous pouvez également créer une feuille de calcul Excel qui inclut des flux de données dynamiques, qui inclut des liens vers les dernières données du tableau de bord de surveillance.</span><span class="sxs-lookup"><span data-stu-id="1b25f-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="1b25f-212">Pour créer un fichier de flux de données actives, cliquez sur l’icône orange **Exporter vers un flux de données** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="1b25f-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="1b25f-213">Si vous préférez imprimer le tableau de bord actif, cliquez sur l’icône de l’imprimante dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="1b25f-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

