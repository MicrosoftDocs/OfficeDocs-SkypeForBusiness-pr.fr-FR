---
title: Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Utilisez les rapports Power BI de Microsoft teams pour suivre l’utilisation de Microsoft teams au sein de votre organisation.
ms.openlocfilehash: 7eb39d043fafae0464ac52aa1e328c24b22d73f3
ms.sourcegitcommit: 86366b66b15870fe83cbb76e1ae7aa1ce9b3bfe1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42858759"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="e0d08-103">Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord</span><span class="sxs-lookup"><span data-stu-id="e0d08-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="e0d08-104">Nouveauté du 2020 mars, nous avons ajouté un rapport sur l’utilisation des équipes aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="e0d08-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="e0d08-105">Ce nouvel état d’utilisation de teams vous permet de déterminer la façon dont vos utilisateurs utilisent Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e0d08-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="e0d08-106">Ces rapports sont destinés à être centralisés pour permettre à la fois aux administrateurs et aux leaders du marché d’avoir accès à ces données.</span><span class="sxs-lookup"><span data-stu-id="e0d08-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="e0d08-107">Le rapport taux d’utilisation de Microsoft Team BI comporte deux rapports principaux : **[Résumé des appels et synthèse](#call-count-summary-report)** des **[minutes audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="e0d08-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="e0d08-108">Les rapports sur l' [utilisation quotidienne](#daily-usage) et les [Détails audio régionaux](#regional-audio-details) sont disponibles lorsqu’un utilisateur tire parti des rapports d’exploration, indiqués dans les descriptions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e0d08-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="e0d08-109">Les données de bâtiment et de sous-réseau doivent être renseignées pour fournir des fonctionnalités de filtrage régionale et réseau.</span><span class="sxs-lookup"><span data-stu-id="e0d08-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="e0d08-110">Rapport de synthèse sur le nombre d’appels</span><span class="sxs-lookup"><span data-stu-id="e0d08-110">Call Count Summary Report</span></span>

<span data-ttu-id="e0d08-111">La page principale (Résumé du numéro d’appel) fournit immédiatement le nombre de sessions audio, vidéo et de partage d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de section.</span><span class="sxs-lookup"><span data-stu-id="e0d08-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="e0d08-112">Les données affichées initialement s’affichent pour l’ensemble de l’organisation et peuvent être filtrées à l’aide des options de la liste déroulante des segments sur le côté gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="e0d08-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="e0d08-114">Dans la partie droite de la liste déroulante du segment, le nombre d’appels par type de média est scindé en affichage interne/externe au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="e0d08-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="e0d08-115">Dans la capture d’écran ci-dessus, nous pouvons voir plus d’appels à partir d’emplacements d’organisation extérieurs, ce qui est pertinent pour l’environnement global actuel.</span><span class="sxs-lookup"><span data-stu-id="e0d08-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="e0d08-116">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="e0d08-117">À droite de la zone nombre de types de média, nous avons le nombre d’appels mensuels par type de média pour les derniers 90 jours.</span><span class="sxs-lookup"><span data-stu-id="e0d08-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="e0d08-118">Chaque type de colonne et de média peut être pointé pour afficher le nombre d’un mois précédent ou du mois actuel jusqu’à ce jour, en fournissant des informations de tendance d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="e0d08-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="e0d08-119">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="e0d08-120">Le graphique au milieu ne fonctionne pas comme le graphique de jour de 90, mais il fournit un affichage d’utilisation journalière pour les 30 derniers jours, et permet à un utilisateur de cliquer avec le bouton droit sur les détails d’un jour spécifique.</span><span class="sxs-lookup"><span data-stu-id="e0d08-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="e0d08-121">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="e0d08-122">Dans la section en bas à gauche de la page se trouve un tableau qui fournit des valeurs totales pour chaque type de média au cours de l’année écoulée.</span><span class="sxs-lookup"><span data-stu-id="e0d08-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="e0d08-123">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="e0d08-124">Ce tableau inclut également une analyse approfondie pour vous permettre de voir une répartition des données régionale.</span><span class="sxs-lookup"><span data-stu-id="e0d08-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="e0d08-125">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="e0d08-126">À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="e0d08-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="e0d08-127">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="e0d08-128">Le dernier ensemble de graphiques pour cette page présente chaque type de média individuellement, avec une répartition indiquant une utilisation de conférences et de réseaux P2P.</span><span class="sxs-lookup"><span data-stu-id="e0d08-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="e0d08-129">Les graphiques ci-dessous montrent qu’il existe un nombre nettement supérieur d’utilisation de conférences par rapport au P2P.</span><span class="sxs-lookup"><span data-stu-id="e0d08-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="e0d08-130">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="e0d08-131">Rapport de synthèse des minutes audio</span><span class="sxs-lookup"><span data-stu-id="e0d08-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="e0d08-132">Le rapport d’utilisation des minutes audio est fourni dans quelques affichages.</span><span class="sxs-lookup"><span data-stu-id="e0d08-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="e0d08-133">Le résumé de l’utilisation de l’espace de 30 jours est affiché en regard des segments comme facile à utiliser pour les zones de texte.</span><span class="sxs-lookup"><span data-stu-id="e0d08-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="e0d08-134">Le numéro supérieur correspond au total du trente jours, avec les répartitions internes et externes.</span><span class="sxs-lookup"><span data-stu-id="e0d08-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="e0d08-136">Le graphique barre supérieure droite fournit une vue yearlong de l’utilisation de la fonction audio de conférence.</span><span class="sxs-lookup"><span data-stu-id="e0d08-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="e0d08-137">Pointez sur le mois pour afficher les minutes audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="e0d08-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="e0d08-138">Pour afficher la différence entre le son de votre interligne et celle de la conférence téléphonique, le graphique en bas à gauche tire tout le son de l’année dernière et le scinde entre les deux types.</span><span class="sxs-lookup"><span data-stu-id="e0d08-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="e0d08-139">![Capture d’écran : rapport](media/CQD-teams-utilization-report10.png) de synthèse sur le pays d’appel le dernier graphique pour la page minutes audio montre l’utilisation des minutes audio sur une façade de carte globale.</span><span class="sxs-lookup"><span data-stu-id="e0d08-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="e0d08-140">Ce graphique ne fonctionnera que si les données de génération et de sous-réseau sont téléchargées vers le client.</span><span class="sxs-lookup"><span data-stu-id="e0d08-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="e0d08-141">La superposition de graphique en secteurs sur la carte peut être percée, ce qui vous permet de fournir une utilisation audio régionale.</span><span class="sxs-lookup"><span data-stu-id="e0d08-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="e0d08-143">Fonctionnalités d’analyse approfondie</span><span class="sxs-lookup"><span data-stu-id="e0d08-143">Drill-through capabilities</span></span>

<span data-ttu-id="e0d08-144">Comme indiqué précédemment, les utilisateurs peuvent explorer les rapports d’utilisation quotidienne et régionale.</span><span class="sxs-lookup"><span data-stu-id="e0d08-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="e0d08-145">Utilisation quotidienne</span><span class="sxs-lookup"><span data-stu-id="e0d08-145">Daily Usage</span></span>

<span data-ttu-id="e0d08-146">Le rapport d’utilisation quotidienne permet à un administrateur d’identifier les périodes de forte consommation au cours d’une journée.</span><span class="sxs-lookup"><span data-stu-id="e0d08-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="e0d08-147">En plus de l’utilisation, nous sommes en mesure de capturer les informations et les commentaires globaux de chaque jour.</span><span class="sxs-lookup"><span data-stu-id="e0d08-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="e0d08-149">Ces données peuvent être utilisées pour identifier les régions rencontrant des problèmes en temps maximum de consommation.</span><span class="sxs-lookup"><span data-stu-id="e0d08-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="e0d08-150">Sur la page Résumé du numéro d’appel, accédez à une date spécifique.</span><span class="sxs-lookup"><span data-stu-id="e0d08-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="e0d08-151">Regardez la tendance horaire du jour pour trouver le taux d’utilisation maximal.</span><span class="sxs-lookup"><span data-stu-id="e0d08-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="e0d08-152">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="e0d08-153">Cliquez sur la colonne de ce jour pour afficher les métriques de cette heure.</span><span class="sxs-lookup"><span data-stu-id="e0d08-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="e0d08-154">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="e0d08-155">Le tableau sous le graphique affiche les mesures pour cette heure.</span><span class="sxs-lookup"><span data-stu-id="e0d08-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="e0d08-156">Vous pouvez trier ce critère par n’importe quel en-tête de colonne. Néanmoins, nous aimerions pouvoir Rechercher les zones problématiques.</span><span class="sxs-lookup"><span data-stu-id="e0d08-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="e0d08-158">Nous voyons que la région de IND rencontre des performances vidéo médiocres pendant ce laps de temps.</span><span class="sxs-lookup"><span data-stu-id="e0d08-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="e0d08-159">Par la suite, les rapports Microsoft bord QER peuvent être utilisés pour affiner l’emplacement problématique, car le cadre de la région et de l’heure a été identifié.</span><span class="sxs-lookup"><span data-stu-id="e0d08-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="e0d08-160">Détails audio régionaux</span><span class="sxs-lookup"><span data-stu-id="e0d08-160">Regional Audio Details</span></span>

<span data-ttu-id="e0d08-161">Les détails audio régionaux d’une analyse descendante montrent en particulier l’utilisation des minutes audio pour la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e0d08-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="e0d08-162">Les utilisateurs disposant d’un accès à bord peuvent voir les tendances d’utilisation pour les appels audio et vidéo P2P au sein de la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e0d08-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="e0d08-163">Dans la page Résumé du numéro d’appel, accédez à la zone de recherche en tant que région spécifique dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="e0d08-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="e0d08-164">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="e0d08-165">Sélectionnez la ligne contenant les informations supplémentaires nécessaires pour la région.</span><span class="sxs-lookup"><span data-stu-id="e0d08-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="e0d08-166">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="e0d08-167">Les tendances des données indiquent un nombre considérable de minutes d’utilisation sur le réseau interne, avec une conférence bien plus longue.</span><span class="sxs-lookup"><span data-stu-id="e0d08-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="e0d08-168">![Capture d’écran : rapport de synthèse sur le pays d’appel](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="e0d08-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="e0d08-169">La tendance régionale du son peut être utilisée pour illustrer la façon dont les utilisateurs sont affectés par des influences externes dans le monde.</span><span class="sxs-lookup"><span data-stu-id="e0d08-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="e0d08-170">Pour l’instant, nous vous attendons d’avoir accès à l’utilisation externe des régions EMEA et APAC qui peuvent être utilisées par les personnes invitées à travailler à distance.</span><span class="sxs-lookup"><span data-stu-id="e0d08-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="e0d08-171">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e0d08-171">Related topics</span></span>

[<span data-ttu-id="e0d08-172">Dimensions et mesures disponibles dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="e0d08-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="e0d08-173">Classification de flux de données dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="e0d08-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="e0d08-174">Configurer l'analyse des appels Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e0d08-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="e0d08-175">Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="e0d08-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="e0d08-176">Tableau de bord Analyse des appels et Qualité des appels</span><span class="sxs-lookup"><span data-stu-id="e0d08-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 