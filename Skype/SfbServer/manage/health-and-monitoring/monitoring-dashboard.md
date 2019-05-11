---
title: À l’aide du tableau de bord de surveillance dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 'Résumé : En savoir plus sur le tableau de bord de surveillance dans Skype pour Business Server.'
ms.openlocfilehash: 9e670ef971b6be9988167f82f21e855cbc8083a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902854"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="16ec3-103">À l’aide du tableau de bord de surveillance dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="16ec3-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="16ec3-104">**Résumé :** Obtenir des informations sur le tableau de bord de surveillance dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="16ec3-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="16ec3-105">Le tableau de bord de surveillance fournit aux administrateurs un aperçu rapide de leur Skype pour l’utilisation de système et d’intégrité du système Business Server.</span><span class="sxs-lookup"><span data-stu-id="16ec3-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="16ec3-106">Le tableau de bord est conçu pour afficher une vue agrégée des mesures système clés, et ce en affichant soit :</span><span class="sxs-lookup"><span data-stu-id="16ec3-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="16ec3-107">Les totaux du jour.</span><span class="sxs-lookup"><span data-stu-id="16ec3-107">Totals for the current day.</span></span> <span data-ttu-id="16ec3-108">Notez que les valeurs affichées pour le jour actuel représentent les données enregistrées de minuit à l’heure actuelle (sur la base de l’heure locale du serveur de rapports).</span><span class="sxs-lookup"><span data-stu-id="16ec3-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="16ec3-109">Par conséquent, vous ne verrez que les données d’un jour partiel et non d’une période de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="16ec3-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="16ec3-110">Par exemple, si l’heure locale du serveur est 8 h 00, vous voyez heures huit de données, car il existe huit heures entre minuit et l’heure actuelle de 8 h 00.</span><span class="sxs-lookup"><span data-stu-id="16ec3-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="16ec3-111">Les totaux de la semaine, et les totaux de la tendance des six semaines précédentes.</span><span class="sxs-lookup"><span data-stu-id="16ec3-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="16ec3-112">Les totaux du mois, et les totaux de la tendance des six mois précédents (pour l’utilisation du système uniquement).</span><span class="sxs-lookup"><span data-stu-id="16ec3-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="16ec3-113">Notez que vous pouvez utiliser l’applet de commande [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) pour renvoyer l’URL utilisée pour accéder à Skype pour les rapports de surveillance Business Server :</span><span class="sxs-lookup"><span data-stu-id="16ec3-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```
Get-CsReportingConfiguration
```

<span data-ttu-id="16ec3-114">Par défaut, le Tableau de bord de suivi affiche les données des mesures suivantes pour la semaine en cours (et les totaux de la tendance des six semaines précédentes) :</span><span class="sxs-lookup"><span data-stu-id="16ec3-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="16ec3-115">Mesures d’utilisation du système</span><span class="sxs-lookup"><span data-stu-id="16ec3-115">System Usage Metrics</span></span>

 <span data-ttu-id="16ec3-116">**Enregistrement**</span><span class="sxs-lookup"><span data-stu-id="16ec3-116">**Registration**</span></span>
  
- <span data-ttu-id="16ec3-117">Ouvertures de sessions à utilisateur unique</span><span class="sxs-lookup"><span data-stu-id="16ec3-117">Unique user logons</span></span>
    
  <span data-ttu-id="16ec3-118">**Égal à égal**</span><span class="sxs-lookup"><span data-stu-id="16ec3-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="16ec3-119">Nombre total de sessions</span><span class="sxs-lookup"><span data-stu-id="16ec3-119">Total sessions</span></span>
    
- <span data-ttu-id="16ec3-120">Sessions de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="16ec3-120">IM sessions</span></span>
    
- <span data-ttu-id="16ec3-121">Sessions audio</span><span class="sxs-lookup"><span data-stu-id="16ec3-121">Audio sessions</span></span>
    
- <span data-ttu-id="16ec3-122">Sessions vidéo</span><span class="sxs-lookup"><span data-stu-id="16ec3-122">Video sessions</span></span>
    
- <span data-ttu-id="16ec3-123">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="16ec3-123">Application sharing</span></span>
    
- <span data-ttu-id="16ec3-124">Nombre total de minutes de session audio</span><span class="sxs-lookup"><span data-stu-id="16ec3-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="16ec3-125">Nombre moyen de minutes de session audio</span><span class="sxs-lookup"><span data-stu-id="16ec3-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="16ec3-126">**Conférence**</span><span class="sxs-lookup"><span data-stu-id="16ec3-126">**Conference**</span></span>
  
- <span data-ttu-id="16ec3-127">Nombre total de conférences</span><span class="sxs-lookup"><span data-stu-id="16ec3-127">Total conferences</span></span>
    
- <span data-ttu-id="16ec3-128">Conférences par messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="16ec3-128">IM conferences</span></span>
    
- <span data-ttu-id="16ec3-129">Conférences A/V</span><span class="sxs-lookup"><span data-stu-id="16ec3-129">A/V conferences</span></span>
    
- <span data-ttu-id="16ec3-130">Conférences de partage d’application</span><span class="sxs-lookup"><span data-stu-id="16ec3-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="16ec3-131">Conférences web</span><span class="sxs-lookup"><span data-stu-id="16ec3-131">Web conferences</span></span>
    
- <span data-ttu-id="16ec3-132">Nombre total d’organisateurs</span><span class="sxs-lookup"><span data-stu-id="16ec3-132">Total organizers</span></span>
    
- <span data-ttu-id="16ec3-133">Nombre total de minutes par conférence A/V</span><span class="sxs-lookup"><span data-stu-id="16ec3-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="16ec3-134">Nombre moyen de minutes par conférence A/V</span><span class="sxs-lookup"><span data-stu-id="16ec3-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="16ec3-135">Nombre total de conférences RTC</span><span class="sxs-lookup"><span data-stu-id="16ec3-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="16ec3-136">Nombre total de participants RTC</span><span class="sxs-lookup"><span data-stu-id="16ec3-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="16ec3-137">Nombre total de minutes par participant RTC</span><span class="sxs-lookup"><span data-stu-id="16ec3-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="16ec3-138">Outre les mesures d’utilisation du système, les mesures suivantes indiquent le total pour le jour actuel et les six jours précédents (si vous sélectionnez **Vue hebdomadaire**), ou pour la semaine en cours et les six semaines précédentes si vous sélectionnez **Vue mensuelle**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="16ec3-139">Diagnostics des appels par utilisateur</span><span class="sxs-lookup"><span data-stu-id="16ec3-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="16ec3-140">**Utilisateurs ayant rencontré des problèmes d’appel**</span><span class="sxs-lookup"><span data-stu-id="16ec3-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="16ec3-141">Nombre total d’utilisateurs ayant rencontré des problèmes d’appel</span><span class="sxs-lookup"><span data-stu-id="16ec3-141">Total users with call failures</span></span>
    
- <span data-ttu-id="16ec3-142">Organisateurs de conférence ayant rencontré des problèmes d’appel</span><span class="sxs-lookup"><span data-stu-id="16ec3-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="16ec3-143">**Utilisateurs ayant eu des appels de qualité médiocre**</span><span class="sxs-lookup"><span data-stu-id="16ec3-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="16ec3-144">Nombre total d’utilisateurs ayant eu des appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="16ec3-145">Diagnostics des appels</span><span class="sxs-lookup"><span data-stu-id="16ec3-145">Call Diagnostics</span></span>

<span data-ttu-id="16ec3-146">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="16ec3-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="16ec3-147">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="16ec3-147">Total failures</span></span>
    
- <span data-ttu-id="16ec3-148">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="16ec3-148">Overall failure rate</span></span>
    
- <span data-ttu-id="16ec3-149">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="16ec3-149">IM failure rate</span></span>
    
- <span data-ttu-id="16ec3-150">Taux d’échec audio</span><span class="sxs-lookup"><span data-stu-id="16ec3-150">Audio failure rate</span></span>
    
- <span data-ttu-id="16ec3-151">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="16ec3-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="16ec3-152">Conférence</span><span class="sxs-lookup"><span data-stu-id="16ec3-152">Conference</span></span>
  
- <span data-ttu-id="16ec3-153">Nombre total d’échecs</span><span class="sxs-lookup"><span data-stu-id="16ec3-153">Total failures</span></span>
    
- <span data-ttu-id="16ec3-154">Taux d’échec global</span><span class="sxs-lookup"><span data-stu-id="16ec3-154">Overall failure rate</span></span>
    
- <span data-ttu-id="16ec3-155">Taux d’échec de la messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="16ec3-155">IM failure rate</span></span>
    
- <span data-ttu-id="16ec3-156">Taux d’échec A/V</span><span class="sxs-lookup"><span data-stu-id="16ec3-156">A/V failure rate</span></span>
    
- <span data-ttu-id="16ec3-157">Taux d’échec du partage d’application</span><span class="sxs-lookup"><span data-stu-id="16ec3-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="16ec3-158">Cinq principaux serveurs par session ayant échoué</span><span class="sxs-lookup"><span data-stu-id="16ec3-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="16ec3-159">Diagnostic de la qualité des médias</span><span class="sxs-lookup"><span data-stu-id="16ec3-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="16ec3-160">Égal à égal</span><span class="sxs-lookup"><span data-stu-id="16ec3-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="16ec3-161">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="16ec3-162">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="16ec3-163">Appels PSTN de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="16ec3-164">Conférence</span><span class="sxs-lookup"><span data-stu-id="16ec3-164">Conference</span></span>
  
- <span data-ttu-id="16ec3-165">Nombre total d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="16ec3-166">Pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="16ec3-167">Appels PSTN de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="16ec3-168">Cinq derniers serveurs par pourcentage d’appels de qualité médiocre</span><span class="sxs-lookup"><span data-stu-id="16ec3-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="16ec3-169">Travail avec le Tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="16ec3-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="16ec3-p103">Comme mentionné plus haut, les totaux par défaut sont affichés pour la semaine en cours et les valeurs de tendance pour les six semaines précédentes. Si vous préférez voir les totaux pour le mois en cours (ainsi que les valeurs de la tendance sur les six mois précédents), cliquez sur le lien **Vue mensuelle** dans le coin supérieur droit du tableau de bord. Si vous décidez d’afficher les totaux mensuels, le texte du lien devient **Vue hebdomadaire**. Vous pouvez revenir à la vue mensuelle en cliquant dessus.</span><span class="sxs-lookup"><span data-stu-id="16ec3-p103">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks. If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard. If you decide to view monthly totals, the link text will change to **Weekly View**. You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="16ec3-p104">Le Tableau de bord de suivi ne vous permet que de voir les totaux de la semaine (ou du mois) en cours et les valeurs de tendance des six semaines précédentes (ou mois précédents). Vous ne pouvez pas modifier ces dates et périodes. Par exemple, le tableau de bord ne vous permet pas de voir les totaux des rapports pour la période commençant neuf mois plus tôt.</span><span class="sxs-lookup"><span data-stu-id="16ec3-p104">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months). You cannot change these dates and times. For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="16ec3-p105">Les valeurs affichées dans les colonnes **Cette semaine**, **Ce mois-ci** ou **Aujourd’hui** vous mènent à des informations détaillées sur l’élément. Rappelez-vous que le nom de la colonne et les valeurs qui y sont affichées changent en fonction de la mesure choisie et de votre choix de la vue hebdomadaire ou mensuelle. Par exemple, si vous cliquez sur les totaux affichés pour la mesure **Ouvertures de sessions à utilisateur unique**, vous verrez le **Rapport d’enregistrement de l’utilisateur** pour la période spécifiée. Vous pouvez retourner au Tableau de bord de suivi à tout moment en cliquant sur **Tableau de bord**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-p105">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item. Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view. For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period. You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="16ec3-181">Vous pouvez également accéder à la page d’accueil de Monitoring Server Reports en cliquant sur le lien **rapports** dans le coin supérieur droit du tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="16ec3-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="16ec3-p106">La colonne **Tendance** montre un graphique en courbes indiquant les totaux des six semaines précédentes (ou, selon la mesure et l’intervalle de temps, les six derniers jours ou mois). Ces graphiques en courbes affichent un point de données sans nom pour chaque période (par exemple, un point de données sans nom pour chacune des six semaines précédentes). Cependant, vous pouvez récupérer les valeurs réelles pour ces graphiques en maintenant le pointeur de la souris sur le graphique. Une info-bulle vous indique alors les valeurs minimale et maximale du graphique.</span><span class="sxs-lookup"><span data-stu-id="16ec3-p106">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months). These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks). However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph. In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="16ec3-186">Exportation de données à partir du Tableau de bord de suivi</span><span class="sxs-lookup"><span data-stu-id="16ec3-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="16ec3-p107">Le Tableau de bord de suivi permet d’exporter la vue en cours de différentes manières. Dans la barre d’outils du tableau de bord se trouve une icône représentant une disquette avec une flèche verte attachée. Si vous cliquez dessus, une liste déroulante avec les formats d’exportation de données suivants apparaît :</span><span class="sxs-lookup"><span data-stu-id="16ec3-p107">The Monitoring Dashboard provides a number of ways to export the current dashboard view. On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it. If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="16ec3-190">fichier XML avec données de rapport ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-190">XML file with report data</span></span>
    
- <span data-ttu-id="16ec3-191">fichier CSV (valeurs séparées par des virgules) ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="16ec3-192">fichier PDF ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-192">PDF</span></span>
    
- <span data-ttu-id="16ec3-193">fichier MHTML (archive Web) ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="16ec3-194">fichier Excel ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-194">Excel</span></span>
    
- <span data-ttu-id="16ec3-195">fichier TIFF ;</span><span class="sxs-lookup"><span data-stu-id="16ec3-195">TIFF file</span></span>
    
- <span data-ttu-id="16ec3-196">fichier Word.</span><span class="sxs-lookup"><span data-stu-id="16ec3-196">Word</span></span>
    
<span data-ttu-id="16ec3-197">Pour exporter la vue active du tableau de bord (et ses valeurs), cliquez sur l’option d’exportation souhaitée.</span><span class="sxs-lookup"><span data-stu-id="16ec3-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="16ec3-198">Skype pour Business Server génère un rapport au format spécifié et puis vous offre la possibilité d’ouvrir ce rapport ou de l’enregistrer.</span><span class="sxs-lookup"><span data-stu-id="16ec3-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="16ec3-199">Notez que, par défaut, Skype pour Business Server titles le rapport de **Tableau de bord de surveillance** et l’enregistre dans votre dossier de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="16ec3-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="16ec3-200">Pour nommer le rapport différemment ou pour le stocker dans un autre dossier, cliquez sur la flèche située à côté du bouton **Enregistrer**, puis cliquez sur **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="16ec3-201">Si le nom **Tableau de bord de suivi** et le dossier d’enregistrement Téléchargements vous conviennent, vous pouvez simplement appuyer sur le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="16ec3-p109">Lorsque vous essayez d’exporter des données du tableau de bord, il est possible qu’une boîte de dialogue **Alerte de sécurité** apparaisse avec le message « Vos paramètres actuels ne permettent pas le téléchargement de ce fichier. » Dans ce cas, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="16ec3-p109">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded." If that occurs, do the following:</span></span>
  
- <span data-ttu-id="16ec3-204">Dans Internet Explorer, sélectionnez **Options Internet**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="16ec3-205">Dans la boîte de dialogue **Options Internet**, sous l’onglet **Sécurité**, cliquez sur **Sites approuvés**, puis sur **Sites**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="16ec3-206">Dans la boîte de dialogue **sites de confiance** , cliquez sur **Ajouter** pour ajouter le Skype pour Business Server qui exécute Skype pour les rapports de serveur Business pour les collections de sites de confiance.</span><span class="sxs-lookup"><span data-stu-id="16ec3-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="16ec3-207">Cliquez sur **Fermer**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="16ec3-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="16ec3-p110">Vous devez ensuite actualiser le Tableau de bord de suivi pour que les modifications prennent effet. Pour cela, appuyez sur F5 ou cliquez sur l’icône **Actualiser** de la barre d’outils du tableau de bord. (L’icône **Actualiser** représente un cercle contenant deux flèches vertes.)</span><span class="sxs-lookup"><span data-stu-id="16ec3-p110">You will then need to refresh the Monitoring Dashboard before the changes take effect. To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar. (The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="16ec3-p111">Vous pouvez également créer une feuille de calcul Excel avec les flux de données actives, comprenant des liens vers les dernières données du Tableau de bord de suivi. Pour créer un fichier de flux de données actives, cliquez sur l’icône orange **Exporter vers un flux de données** dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="16ec3-p111">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data. To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="16ec3-213">Si vous préférez imprimer le tableau de bord actif, cliquez sur l’icône d’imprimante située dans la barre d’outils.</span><span class="sxs-lookup"><span data-stu-id="16ec3-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

