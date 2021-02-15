---
title: Utilisation du tableau de bord de surveillance dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Résumé : Découvrez le tableau de bord de surveillance dans Skype Entreprise Server.'
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827784"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="ff004-103">Utilisation du tableau de bord de surveillance dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff004-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="ff004-104">**Résumé :** Découvrez le tableau de bord de surveillance dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ff004-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="ff004-105">Le Tableau de bord de surveillance offre aux administrateurs une vue d’ensemble rapide de l’état et de l’utilisation du système de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ff004-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="ff004-106">Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés et pour ce faire, en affichant :</span><span class="sxs-lookup"><span data-stu-id="ff004-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="ff004-107">Totaux du jour en cours.</span><span class="sxs-lookup"><span data-stu-id="ff004-107">Totals for the current day.</span></span> <span data-ttu-id="ff004-108">Notez que les valeurs affichées pour le jour actuel représentent des données enregistrées de minuit à l’heure actuelle (en fonction de l’heure locale du serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="ff004-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="ff004-109">Cela signifie que vous affichez généralement les données pour un jour partiel et non pour une période de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="ff004-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="ff004-110">Par exemple, si l’heure locale du serveur est 8:00 AM, vous voyez une valeur de huit heures de données, car il y a huit heures entre minuit et l’heure actuelle de 8:00.</span><span class="sxs-lookup"><span data-stu-id="ff004-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="ff004-111">Totaux de la semaine et totaux de tendance pour les six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="ff004-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="ff004-112">Totaux du mois et totaux de tendance pour les six derniers mois (pour l’utilisation du système uniquement).</span><span class="sxs-lookup"><span data-stu-id="ff004-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="ff004-113">Notez que vous pouvez utiliser l’cmdlet [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) pour renvoyer l’URL utilisée pour accéder aux rapports de surveillance de Skype Entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="ff004-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="ff004-114">Par défaut, le Tableau de bord de surveillance affiche les données pour les mesures suivantes pour la semaine en cours (et les totaux de tendance pour les six semaines précédentes) :</span><span class="sxs-lookup"><span data-stu-id="ff004-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="ff004-115">Mesures d’utilisation du système</span><span class="sxs-lookup"><span data-stu-id="ff004-115">System Usage Metrics</span></span>

 <span data-ttu-id="ff004-116">**Registration**</span><span class="sxs-lookup"><span data-stu-id="ff004-116">**Registration**</span></span>
  
- <span data-ttu-id="ff004-117">Connexions utilisateur uniques</span><span class="sxs-lookup"><span data-stu-id="ff004-117">Unique user logons</span></span>
    
  <span data-ttu-id="ff004-118">**Pair à pair**</span><span class="sxs-lookup"><span data-stu-id="ff004-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="ff004-119">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="ff004-119">Total sessions</span></span>
    
- <span data-ttu-id="ff004-120">Sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="ff004-120">IM sessions</span></span>
    
- <span data-ttu-id="ff004-121">Sessions audio</span><span class="sxs-lookup"><span data-stu-id="ff004-121">Audio sessions</span></span>
    
- <span data-ttu-id="ff004-122">Sessions vidéo</span><span class="sxs-lookup"><span data-stu-id="ff004-122">Video sessions</span></span>
    
- <span data-ttu-id="ff004-123">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="ff004-123">Application sharing</span></span>
    
- <span data-ttu-id="ff004-124">Nombre total de minutes par session audio</span><span class="sxs-lookup"><span data-stu-id="ff004-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="ff004-125">Avg. minutes de session audio</span><span class="sxs-lookup"><span data-stu-id="ff004-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="ff004-126">**Conférence**</span><span class="sxs-lookup"><span data-stu-id="ff004-126">**Conference**</span></span>
  
- <span data-ttu-id="ff004-127">Nombre total de conférences</span><span class="sxs-lookup"><span data-stu-id="ff004-127">Total conferences</span></span>
    
- <span data-ttu-id="ff004-128">Conférences par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="ff004-128">IM conferences</span></span>
    
- <span data-ttu-id="ff004-129">Conférences A/V</span><span class="sxs-lookup"><span data-stu-id="ff004-129">A/V conferences</span></span>
    
- <span data-ttu-id="ff004-130">Conférences de partage d’application</span><span class="sxs-lookup"><span data-stu-id="ff004-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="ff004-131">Conférences Web</span><span class="sxs-lookup"><span data-stu-id="ff004-131">Web conferences</span></span>
    
- <span data-ttu-id="ff004-132">Nombre total d’organisateurs</span><span class="sxs-lookup"><span data-stu-id="ff004-132">Total organizers</span></span>
    
- <span data-ttu-id="ff004-133">Nombre total de minutes par conférence A/V</span><span class="sxs-lookup"><span data-stu-id="ff004-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="ff004-134">Avg. Minutes de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="ff004-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="ff004-135">Nombre total de conférences PSTN</span><span class="sxs-lookup"><span data-stu-id="ff004-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="ff004-136">Nombre total de participants PSTN</span><span class="sxs-lookup"><span data-stu-id="ff004-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="ff004-137">Nombre total de minutes par participant PSTN</span><span class="sxs-lookup"><span data-stu-id="ff004-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="ff004-138">Outre les mesures d’utilisation du système, les mesures suivantes affichent le total pour le jour actuel et les six jours précédents (si vous sélectionnez Affichage **hebdomadaire)** ou pour la semaine en cours et les six semaines passées si vous sélectionnez Affichage **mensuel.**</span><span class="sxs-lookup"><span data-stu-id="ff004-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="ff004-139">Per-User diagnostics des appels</span><span class="sxs-lookup"><span data-stu-id="ff004-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="ff004-140">**Utilisateurs avec des échecs d’appel**</span><span class="sxs-lookup"><span data-stu-id="ff004-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="ff004-141">Nombre total d’utilisateurs ayant échoué aux appels</span><span class="sxs-lookup"><span data-stu-id="ff004-141">Total users with call failures</span></span>
    
- <span data-ttu-id="ff004-142">Organisateurs de conférence avec des échecs d’appel</span><span class="sxs-lookup"><span data-stu-id="ff004-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="ff004-143">**Utilisateurs ayant des appels de qualité médiocre**</span><span class="sxs-lookup"><span data-stu-id="ff004-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="ff004-144">Nombre total d’utilisateurs ayant des appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="ff004-145">Diagnostics des appels</span><span class="sxs-lookup"><span data-stu-id="ff004-145">Call Diagnostics</span></span>

<span data-ttu-id="ff004-146">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="ff004-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="ff004-147">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="ff004-147">Total failures</span></span>
    
- <span data-ttu-id="ff004-148">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="ff004-148">Overall failure rate</span></span>
    
- <span data-ttu-id="ff004-149">Taux d’échec de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="ff004-149">IM failure rate</span></span>
    
- <span data-ttu-id="ff004-150">Taux d’échec audio</span><span class="sxs-lookup"><span data-stu-id="ff004-150">Audio failure rate</span></span>
    
- <span data-ttu-id="ff004-151">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="ff004-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="ff004-152">Programme</span><span class="sxs-lookup"><span data-stu-id="ff004-152">Conference</span></span>
  
- <span data-ttu-id="ff004-153">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="ff004-153">Total failures</span></span>
    
- <span data-ttu-id="ff004-154">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="ff004-154">Overall failure rate</span></span>
    
- <span data-ttu-id="ff004-155">Taux d’échec de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="ff004-155">IM failure rate</span></span>
    
- <span data-ttu-id="ff004-156">Taux d’échec A/V</span><span class="sxs-lookup"><span data-stu-id="ff004-156">A/V failure rate</span></span>
    
- <span data-ttu-id="ff004-157">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="ff004-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="ff004-158">Cinq serveurs principaux en cas d’échec des sessions</span><span class="sxs-lookup"><span data-stu-id="ff004-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="ff004-159">Diagnostics de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="ff004-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="ff004-160">Pair à pair</span><span class="sxs-lookup"><span data-stu-id="ff004-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="ff004-161">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="ff004-162">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ff004-163">Appels PSTN de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ff004-164">Programme</span><span class="sxs-lookup"><span data-stu-id="ff004-164">Conference</span></span>
  
- <span data-ttu-id="ff004-165">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="ff004-166">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ff004-167">Appels PSTN de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ff004-168">Principaux serveurs par pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="ff004-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="ff004-169">Travailler avec le Tableau de bord de surveillance</span><span class="sxs-lookup"><span data-stu-id="ff004-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="ff004-170">Comme indiqué, les totaux par défaut sont affichés pour la semaine en cours et les valeurs de tendance sont affichées pour les six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="ff004-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="ff004-171">Si vous préférez afficher les totaux du mois en cours (ainsi que  les valeurs de tendance des six derniers mois), cliquez sur le lien Affichage mensuel dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="ff004-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="ff004-172">Si vous décidez d’afficher les totaux mensuels, le texte du lien sera changé en **Affichage hebdomadaire.**</span><span class="sxs-lookup"><span data-stu-id="ff004-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="ff004-173">Vous pouvez revenir à l’affichage hebdomadaire en cliquant sur ce lien.</span><span class="sxs-lookup"><span data-stu-id="ff004-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="ff004-174">Le Tableau de bord de surveillance vous limite à la recherche des totaux de la semaine (ou du mois) en cours et des valeurs de tendance des six semaines (ou mois précédents).</span><span class="sxs-lookup"><span data-stu-id="ff004-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="ff004-175">Vous ne pouvez pas modifier ces dates et heures.</span><span class="sxs-lookup"><span data-stu-id="ff004-175">You cannot change these dates and times.</span></span> <span data-ttu-id="ff004-176">Par exemple, vous ne pouvez pas utiliser le tableau de bord pour afficher les totaux des rapports pour la période commençant à neuf mois.</span><span class="sxs-lookup"><span data-stu-id="ff004-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="ff004-177">Les valeurs affichées dans les  colonnes **Cette semaine,** **Ce mois** ou Aujourd’hui vous relient à des informations plus détaillées sur l’élément.</span><span class="sxs-lookup"><span data-stu-id="ff004-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="ff004-178">N’oubliez pas que le nom de colonne et les valeurs affichées dans cette colonne varient souvent en fonction de la mesure choisie et selon que vous avez sélectionné un affichage hebdomadaire ou mensuel.</span><span class="sxs-lookup"><span data-stu-id="ff004-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="ff004-179">Par exemple, si vous cliquez sur les totaux affichés  pour la mesure Ouvertures de session utilisateur **uniques,** vous verrez le rapport d’enregistrement de l’utilisateur pour la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ff004-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="ff004-180">Vous pouvez revenir au Tableau de bord de surveillance à tout moment en cliquant sur **Tableau de bord.**</span><span class="sxs-lookup"><span data-stu-id="ff004-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="ff004-181">Vous pouvez également accéder à la page d’accueil Rapports du serveur de surveillance en cliquant sur le lien **Rapports** dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="ff004-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="ff004-182">La  colonne Tendance affiche un graphique en courbes simple qui affiche les totaux des six dernières semaines (ou, selon la mesure et l’intervalle de temps, les six derniers jours ou les six derniers mois).</span><span class="sxs-lookup"><span data-stu-id="ff004-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="ff004-183">Ces graphiques en courbes simples affichent un point de données non ajouté pour chaque période (par exemple, un point de données non ajouté pour chacune des six semaines précédentes).</span><span class="sxs-lookup"><span data-stu-id="ff004-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="ff004-184">Toutefois, vous pouvez récupérer les valeurs réelles de ces graphiques en maintenant le pointeur de la souris sur le graphique.</span><span class="sxs-lookup"><span data-stu-id="ff004-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="ff004-185">Dans ce cas, une info-conseil vous indique les valeurs maximale et minimale du graphique.</span><span class="sxs-lookup"><span data-stu-id="ff004-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="ff004-186">Exportation de données à partir du tableau de bord de surveillance</span><span class="sxs-lookup"><span data-stu-id="ff004-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="ff004-187">Le Tableau de bord de surveillance fournit plusieurs façons d’exporter l’affichage actuel du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="ff004-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="ff004-188">Dans la barre d’outils du tableau de bord, vous verrez une icône qui ressemble à une disquette avec une flèche verte attachée à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="ff004-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="ff004-189">Si vous cliquez sur cette icône, une liste dropdown s’affiche pour vous donner les formats d’exportation de données suivants :</span><span class="sxs-lookup"><span data-stu-id="ff004-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="ff004-190">fichier XML avec données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="ff004-190">XML file with report data</span></span>
    
- <span data-ttu-id="ff004-191">fichier CSV (valeurs séparées par des virgules) ;</span><span class="sxs-lookup"><span data-stu-id="ff004-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="ff004-192">PDF</span><span class="sxs-lookup"><span data-stu-id="ff004-192">PDF</span></span>
    
- <span data-ttu-id="ff004-193">fichier MHTML (archive web) ;</span><span class="sxs-lookup"><span data-stu-id="ff004-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="ff004-194">Excel</span><span class="sxs-lookup"><span data-stu-id="ff004-194">Excel</span></span>
    
- <span data-ttu-id="ff004-195">fichier TIFF ;</span><span class="sxs-lookup"><span data-stu-id="ff004-195">TIFF file</span></span>
    
- <span data-ttu-id="ff004-196">Word</span><span class="sxs-lookup"><span data-stu-id="ff004-196">Word</span></span>
    
<span data-ttu-id="ff004-197">Pour exporter l’affichage actuel du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée.</span><span class="sxs-lookup"><span data-stu-id="ff004-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="ff004-198">Skype Entreprise Server génère un rapport au format spécifié, puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ff004-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="ff004-199">Notez que, par défaut, Skype  Entreprise Server titre le tableau de bord de surveillance du rapport et l’enregistre dans votre dossier Téléchargements.</span><span class="sxs-lookup"><span data-stu-id="ff004-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="ff004-200">Pour donner un nom différent au rapport ou pour le stocker  dans un autre dossier, cliquez sur la flèche en face du bouton Enregistrer, puis cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="ff004-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="ff004-201">Si vous avez  bien le nom Tableau de bord de surveillance et que le rapport est enregistré dans le dossier Téléchargements, vous pouvez simplement cliquer sur **le bouton** Enregistrer.</span><span class="sxs-lookup"><span data-stu-id="ff004-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="ff004-202">Il est possible que, lorsque vous essayez  d’exporter des données de tableau de bord, une boîte de dialogue Alerte de sécurité s’affiche avec le message « Vos paramètres actuels n’autorisent pas le téléchargement de ce fichier ».</span><span class="sxs-lookup"><span data-stu-id="ff004-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="ff004-203">Si cela se produit, faites les choses suivantes :</span><span class="sxs-lookup"><span data-stu-id="ff004-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="ff004-204">Dans Internet Explorer, sélectionnez **Options Internet.**</span><span class="sxs-lookup"><span data-stu-id="ff004-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="ff004-205">Dans la boîte **de dialogue Options Internet,** sous l’onglet  Sécurité, cliquez sur **Sites** de confiance, puis sur **Sites**.</span><span class="sxs-lookup"><span data-stu-id="ff004-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="ff004-206">Dans la **boîte de**  dialogue Sites de confiance, cliquez sur Ajouter pour ajouter le serveur Skype Entreprise qui exécute les rapports Skype Entreprise Server aux collections de sites web de confiance.</span><span class="sxs-lookup"><span data-stu-id="ff004-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="ff004-207">Cliquez **sur Fermer,** puis sur **OK.**</span><span class="sxs-lookup"><span data-stu-id="ff004-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="ff004-208">Vous devrez ensuite actualiser le tableau de bord de surveillance avant que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="ff004-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="ff004-209">Pour ce faire, appuyez sur F5 ou cliquez sur l’icône **Actualiser** dans la barre d’outils du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="ff004-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="ff004-210">**(L’icône Actualiser** est un cercle avec une paire de flèches vertes.)</span><span class="sxs-lookup"><span data-stu-id="ff004-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="ff004-211">Vous pouvez également créer une feuille de calcul Excel qui inclut des flux de données en direct, qui inclut des liens vers les dernières données du Tableau de bord de surveillance.</span><span class="sxs-lookup"><span data-stu-id="ff004-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="ff004-212">Pour créer un fichier de flux  de données en direct, cliquez sur l’icône orange Exporter vers le flux de données dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="ff004-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="ff004-213">Si vous préférez imprimer le tableau de bord actuel, cliquez sur l’icône de l’imprimante dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="ff004-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

