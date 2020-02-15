---
title: 'Lync Server 2013 : utilisation du tableau de bord de suivi'
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
ms.openlocfilehash: 643cbc55730d8efb1520ed88c40977c90e35f2fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="f424a-102">Utilisation du tableau de bord de suivi dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f424a-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f424a-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="f424a-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="f424a-104">Le tableau de bord de suivi fournit aux administrateurs une vue d’ensemble rapide de l’État et de l’utilisation du système de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f424a-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="f424a-105">Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés et pour ce faire en affichant soit :</span><span class="sxs-lookup"><span data-stu-id="f424a-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="f424a-106">Totaux du jour actuel.</span><span class="sxs-lookup"><span data-stu-id="f424a-106">Totals for the current day.</span></span> <span data-ttu-id="f424a-107">Notez que les valeurs affichées pour le jour actuel représentent des données qui ont été enregistrées de minuit à l’heure actuelle (en fonction de l’heure locale du serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="f424a-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="f424a-108">Cela signifie que vous allez généralement consulter les données d’une journée partielle et non pendant une période de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="f424a-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="f424a-109">Par exemple, si l’heure locale du serveur est 8:00 AM, vous pouvez voir huit heures de données, car il y a huit heures entre minuit et l’heure actuelle de 8:00 AM.</span><span class="sxs-lookup"><span data-stu-id="f424a-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="f424a-110">Les totaux de la semaine, et les totaux de la tendance des six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="f424a-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="f424a-111">Les totaux du mois, et les totaux de la tendance des six mois précédents (pour l’utilisation du système uniquement).</span><span class="sxs-lookup"><span data-stu-id="f424a-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="f424a-112">Notez que vous pouvez utiliser la cmdlet [Get-applet csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) pour renvoyer l’URL utilisée pour accéder aux rapports de surveillance Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="f424a-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="f424a-113">Par défaut, le tableau de bord de suivi affiche les données des mesures suivantes pour la semaine en cours (et les totaux de la tendance des six semaines précédentes) :</span><span class="sxs-lookup"><span data-stu-id="f424a-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="f424a-114">Mesures d’utilisation du système</span><span class="sxs-lookup"><span data-stu-id="f424a-114">System Usage Metrics</span></span>

<span data-ttu-id="f424a-115">**Son**</span><span class="sxs-lookup"><span data-stu-id="f424a-115">**Registration**</span></span>

  - <span data-ttu-id="f424a-116">Ouvertures de session utilisateur uniques</span><span class="sxs-lookup"><span data-stu-id="f424a-116">Unique user logons</span></span>

<span data-ttu-id="f424a-117">**Pair à pair**</span><span class="sxs-lookup"><span data-stu-id="f424a-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="f424a-118">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="f424a-118">Total sessions</span></span>

  - <span data-ttu-id="f424a-119">Sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f424a-119">IM sessions</span></span>

  - <span data-ttu-id="f424a-120">Sessions audio</span><span class="sxs-lookup"><span data-stu-id="f424a-120">Audio sessions</span></span>

  - <span data-ttu-id="f424a-121">Sessions vidéo</span><span class="sxs-lookup"><span data-stu-id="f424a-121">Video sessions</span></span>

  - <span data-ttu-id="f424a-122">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="f424a-122">Application sharing</span></span>

  - <span data-ttu-id="f424a-123">Nombre total de minutes de session audio</span><span class="sxs-lookup"><span data-stu-id="f424a-123">Total audio session minutes</span></span>

  - <span data-ttu-id="f424a-124">Nombre moyen de minutes par session audio</span><span class="sxs-lookup"><span data-stu-id="f424a-124">Avg. audio session minutes</span></span>

<span data-ttu-id="f424a-125">**Salle**</span><span class="sxs-lookup"><span data-stu-id="f424a-125">**Conference**</span></span>

  - <span data-ttu-id="f424a-126">Nombre total de conférences</span><span class="sxs-lookup"><span data-stu-id="f424a-126">Total conferences</span></span>

  - <span data-ttu-id="f424a-127">Conférences de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f424a-127">IM conferences</span></span>

  - <span data-ttu-id="f424a-128">Conférences A/V</span><span class="sxs-lookup"><span data-stu-id="f424a-128">A/V conferences</span></span>

  - <span data-ttu-id="f424a-129">Conférences de partage d’application</span><span class="sxs-lookup"><span data-stu-id="f424a-129">Application sharing conferences</span></span>

  - <span data-ttu-id="f424a-130">Conférences Web</span><span class="sxs-lookup"><span data-stu-id="f424a-130">Web conferences</span></span>

  - <span data-ttu-id="f424a-131">Nombre total de organisateurs</span><span class="sxs-lookup"><span data-stu-id="f424a-131">Total organizers</span></span>

  - <span data-ttu-id="f424a-132">Nombre total de minutes par conférence A/V</span><span class="sxs-lookup"><span data-stu-id="f424a-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="f424a-133">Nbre. Minutes de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="f424a-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="f424a-134">Nombre total de conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="f424a-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="f424a-135">Nombre total de participants PSTN</span><span class="sxs-lookup"><span data-stu-id="f424a-135">Total PSTN participants</span></span>

  - <span data-ttu-id="f424a-136">Nombre total de minutes par participant PSTN</span><span class="sxs-lookup"><span data-stu-id="f424a-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="f424a-137">Outre les mesures d’utilisation du système, les mesures suivantes affichent le total du jour actuel et des six jours précédents (si vous sélectionnez **affichage hebdomadaire**) ou pour la semaine en cours et les six dernières semaines si vous sélectionnez **affichage mensuel**.</span><span class="sxs-lookup"><span data-stu-id="f424a-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="f424a-138">Diagnostics des appels par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f424a-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="f424a-139">**Utilisateurs avec des échecs d’appel**</span><span class="sxs-lookup"><span data-stu-id="f424a-139">**Users with call failures**</span></span>

  - <span data-ttu-id="f424a-140">Nombre total d’utilisateurs avec des échecs d’appel</span><span class="sxs-lookup"><span data-stu-id="f424a-140">Total users with call failures</span></span>

  - <span data-ttu-id="f424a-141">Organisateurs de conférence avec des échecs d’appel</span><span class="sxs-lookup"><span data-stu-id="f424a-141">Conference organizers with call failures</span></span>

<span data-ttu-id="f424a-142">**Utilisateurs avec des appels de qualité médiocre**</span><span class="sxs-lookup"><span data-stu-id="f424a-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="f424a-143">Nombre total d’utilisateurs avec des appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="f424a-144">Diagnostics des appels</span><span class="sxs-lookup"><span data-stu-id="f424a-144">Call Diagnostics</span></span>

<span data-ttu-id="f424a-145">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="f424a-145">Peer-to-peer</span></span>

  - <span data-ttu-id="f424a-146">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="f424a-146">Total failures</span></span>

  - <span data-ttu-id="f424a-147">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="f424a-147">Overall failure rate</span></span>

  - <span data-ttu-id="f424a-148">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f424a-148">IM failure rate</span></span>

  - <span data-ttu-id="f424a-149">Taux d’échec audio</span><span class="sxs-lookup"><span data-stu-id="f424a-149">Audio failure rate</span></span>

  - <span data-ttu-id="f424a-150">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="f424a-150">Application sharing failure rate</span></span>

<span data-ttu-id="f424a-151">Salle</span><span class="sxs-lookup"><span data-stu-id="f424a-151">Conference</span></span>

  - <span data-ttu-id="f424a-152">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="f424a-152">Total failures</span></span>

  - <span data-ttu-id="f424a-153">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="f424a-153">Overall failure rate</span></span>

  - <span data-ttu-id="f424a-154">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="f424a-154">IM failure rate</span></span>

  - <span data-ttu-id="f424a-155">Taux d’échec A/V</span><span class="sxs-lookup"><span data-stu-id="f424a-155">A/V failure rate</span></span>

  - <span data-ttu-id="f424a-156">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="f424a-156">Application sharing failure rate</span></span>

<span data-ttu-id="f424a-157">Cinq principaux serveurs par sessions ayant échoué</span><span class="sxs-lookup"><span data-stu-id="f424a-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="f424a-158">Diagnostic de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="f424a-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="f424a-159">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="f424a-159">Peer-to-peer</span></span>

  - <span data-ttu-id="f424a-160">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-160">Total poor quality calls</span></span>

  - <span data-ttu-id="f424a-161">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="f424a-162">Appels RTC avec une qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="f424a-163">Salle</span><span class="sxs-lookup"><span data-stu-id="f424a-163">Conference</span></span>

  - <span data-ttu-id="f424a-164">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-164">Total poor quality calls</span></span>

  - <span data-ttu-id="f424a-165">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="f424a-166">Appels RTC avec une qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="f424a-167">Serveurs les plus défavorables par pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="f424a-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="f424a-168">Utilisation du tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="f424a-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="f424a-169">Comme indiqué plus haut, par défaut, les totaux sont affichés pour la semaine en cours et les valeurs de tendance sont affichées pour les six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="f424a-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="f424a-170">Si vous préférez afficher les totaux pour le mois en cours (ainsi que les valeurs de tendance pour les six derniers mois), cliquez sur le lien **affichage mensuel** dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="f424a-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="f424a-171">Si vous décidez d’afficher les totaux mensuels, le texte du lien prend la forme **affichage hebdomadaire**.</span><span class="sxs-lookup"><span data-stu-id="f424a-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="f424a-172">Vous pouvez revenir à la vue hebdomadaire en cliquant sur ce lien.</span><span class="sxs-lookup"><span data-stu-id="f424a-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f424a-173">Le tableau de bord de suivi vous limite à consulter les totaux de la semaine (ou du mois) en cours et les valeurs de tendance pour les six semaines (ou les mois précédents).</span><span class="sxs-lookup"><span data-stu-id="f424a-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="f424a-174">Vous ne pouvez pas modifier ces dates et heures.</span><span class="sxs-lookup"><span data-stu-id="f424a-174">You cannot change these dates and times.</span></span> <span data-ttu-id="f424a-175">Par exemple, vous ne pouvez pas utiliser le tableau de bord pour afficher les totaux du rapport pour la période commençant neuf mois plus tôt.</span><span class="sxs-lookup"><span data-stu-id="f424a-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="f424a-176">Les valeurs affichées dans les colonnes **cette semaine**, **ce mois**-ci ou **aujourd’hui** vous permettent d’accéder à des informations plus détaillées sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="f424a-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="f424a-177">N’oubliez pas que le nom de la colonne et les valeurs affichées dans cette colonne diffèrent souvent en fonction de la mesure choisie et selon que vous avez sélectionné la vue hebdomadaire ou mensuelle.</span><span class="sxs-lookup"><span data-stu-id="f424a-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="f424a-178">Par exemple, si vous cliquez sur les totaux affichés pour la mesure **ouvertures de session utilisateur uniques** , le **rapport d’enregistrement** de l’utilisateur s’affiche pour la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f424a-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="f424a-179">Vous pouvez revenir au tableau de bord de suivi à tout moment en cliquant sur **tableau de bord**.</span><span class="sxs-lookup"><span data-stu-id="f424a-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f424a-180">Vous pouvez également accéder à la page d’accueil des rapports du serveur de surveillance en cliquant sur le lien <STRONG>rapports</STRONG> dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="f424a-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="f424a-181">La colonne **tendance** affiche un graphique linéaire qui indique les totaux des six dernières semaines (ou, en fonction de la mesure et de l’intervalle de temps, des six derniers jours ou des six derniers mois).</span><span class="sxs-lookup"><span data-stu-id="f424a-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="f424a-182">Ces graphiques linéaires affichent un point de données sans nom pour chaque période (par exemple, un point de données sans nom pour chacune des six semaines précédentes).</span><span class="sxs-lookup"><span data-stu-id="f424a-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="f424a-183">Toutefois, vous pouvez récupérer les valeurs réelles de ces graphiques en maintenant le pointeur de la souris sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="f424a-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="f424a-184">Dans ce cas, une info-bulle vous indique les valeurs maximale et minimale dans le graphique.</span><span class="sxs-lookup"><span data-stu-id="f424a-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="f424a-185">Exportation de données à partir du tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="f424a-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="f424a-186">Le tableau de bord de suivi offre plusieurs méthodes pour exporter l’affichage actuel du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="f424a-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="f424a-187">Dans la barre d’outils Tableau de bord, une icône ressemblant à une disquette avec une flèche verte s’affiche.</span><span class="sxs-lookup"><span data-stu-id="f424a-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="f424a-188">Si vous cliquez sur cette icône, une liste déroulante s’affiche pour vous donner les formats d’exportation de données suivants :</span><span class="sxs-lookup"><span data-stu-id="f424a-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="f424a-189">fichier XML avec données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="f424a-189">XML file with report data</span></span>

  - <span data-ttu-id="f424a-190">fichier CSV (valeurs séparées par des virgules) ;</span><span class="sxs-lookup"><span data-stu-id="f424a-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="f424a-191">PDF</span><span class="sxs-lookup"><span data-stu-id="f424a-191">PDF</span></span>

  - <span data-ttu-id="f424a-192">fichier MHTML (archive web) ;</span><span class="sxs-lookup"><span data-stu-id="f424a-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="f424a-193">Excel</span><span class="sxs-lookup"><span data-stu-id="f424a-193">Excel</span></span>

  - <span data-ttu-id="f424a-194">fichier TIFF ;</span><span class="sxs-lookup"><span data-stu-id="f424a-194">TIFF file</span></span>

  - <span data-ttu-id="f424a-195">Word</span><span class="sxs-lookup"><span data-stu-id="f424a-195">Word</span></span>

<span data-ttu-id="f424a-196">Pour exporter l’affichage actuel du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée.</span><span class="sxs-lookup"><span data-stu-id="f424a-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="f424a-197">Lync Server 2013 génère un rapport au format spécifié, puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="f424a-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="f424a-198">Notez que, par défaut, Lync Server titres le **tableau de bord de suivi** des rapports et l’enregistre dans votre dossier téléchargements.</span><span class="sxs-lookup"><span data-stu-id="f424a-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="f424a-199">Pour donner un nom différent à l’État ou pour le stocker dans un autre dossier, cliquez sur la flèche en regard du bouton **Enregistrer** , puis cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="f424a-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="f424a-200">Si le tableau de bord de **suivi** des noms est correct et que le rapport est enregistré dans le dossier downloads, vous pouvez simplement cliquer sur le bouton **Enregistrer** .</span><span class="sxs-lookup"><span data-stu-id="f424a-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="f424a-201">Il est possible que, lorsque vous essayez d’exporter des données de tableau de bord, une boîte de dialogue **alerte de sécurité** s’affiche en même temps que le message « vos paramètres actuels n’autorisent pas le téléchargement de ce fichier. »</span><span class="sxs-lookup"><span data-stu-id="f424a-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="f424a-202">Dans ce cas, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="f424a-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="f424a-203">Dans Internet Explorer, sélectionnez **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="f424a-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="f424a-204">Dans la boîte de dialogue **Options Internet** , sous l’onglet **sécurité** , cliquez sur **sites de confiance** , puis sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="f424a-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="f424a-205">Dans la boîte de dialogue **sites de confiance** , cliquez sur **Ajouter** pour ajouter le serveur Lync Server 2013 exécutant Lync Server 2013 rapports aux collections de sites Web de confiance.</span><span class="sxs-lookup"><span data-stu-id="f424a-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="f424a-206">Cliquez sur **Fermer** , puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f424a-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="f424a-207">Vous devrez ensuite actualiser le tableau de bord de suivi pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="f424a-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="f424a-208">Pour ce faire, appuyez sur F5 ou cliquez sur l’icône **Actualiser** de la barre d’outils Tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="f424a-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="f424a-209">(L’icône d' **actualisation** est un cercle avec une paire de flèches vertes.)</span><span class="sxs-lookup"><span data-stu-id="f424a-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="f424a-210">Vous pouvez également créer une feuille de calcul Excel qui inclut des flux de données dynamiques, qui inclut des liens vers les dernières données du tableau de bord de surveillance.</span><span class="sxs-lookup"><span data-stu-id="f424a-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="f424a-211">Pour créer un fichier de flux de données actives, cliquez sur l’icône orange **Exporter vers un flux de données** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="f424a-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="f424a-212">Si vous préférez imprimer le tableau de bord actif, cliquez sur l’icône de l’imprimante dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="f424a-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

