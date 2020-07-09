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
description: Utilisez les rapports Power BI d’utilisation des équipes pour accéder aux données de tableau de bord de qualité des appels de Microsoft Teams (bord) pour suivre l’utilisation de Microsoft teams au sein de votre organisation.
ms.openlocfilehash: bd1a95a683da881a78acb5d4849bba0ac55f4898
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085580"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="6329f-103">Afficher l’utilisation de Microsoft teams dans Power BI à l’aide de données bord</span><span class="sxs-lookup"><span data-stu-id="6329f-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="6329f-104">Nouveauté du 2020 mars, nous avons ajouté un rapport sur l’utilisation des équipes aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="6329f-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="6329f-105">Les nouveaux rapports d’utilisation de teams vous permettent de voir (et combien) vos utilisateurs utilisent Microsoft teams en accédant à des données de tableau de bord de qualité des appels de Teams (bord).</span><span class="sxs-lookup"><span data-stu-id="6329f-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="6329f-106">Ces rapports sont destinés à être centralisés pour permettre à la fois aux administrateurs et aux leaders du marché d’avoir accès à ces données.</span><span class="sxs-lookup"><span data-stu-id="6329f-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="6329f-107">Le rapport taux d’utilisation de Microsoft Team BI comporte deux rapports principaux : **[Résumé des appels et synthèse](#call-count-summary-report)** des **[minutes audio](#audio-minutes-summary-report)**.</span><span class="sxs-lookup"><span data-stu-id="6329f-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="6329f-108">L' [utilisation quotidienne](#daily-usage), les détails de l' [audio régional](#regional-audio-details), les détails de la [Conférence](#conference-details) et les rapports de [liste d’utilisateurs](#user-list) sont lus quand un utilisateur tire parti des rapports d’exploration, indiqués dans les descriptions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6329f-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="6329f-109">Les données de bâtiment et de sous-réseau doivent être renseignées pour fournir des fonctionnalités de filtrage régionale et réseau.</span><span class="sxs-lookup"><span data-stu-id="6329f-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="6329f-110">Rapport de synthèse sur le nombre d’appels</span><span class="sxs-lookup"><span data-stu-id="6329f-110">Call Count Summary Report</span></span>

<span data-ttu-id="6329f-111">La page principale (Résumé du numéro d’appel) fournit immédiatement le nombre de sessions audio, vidéo et de partage d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de section.</span><span class="sxs-lookup"><span data-stu-id="6329f-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="6329f-112">Les données affichées initialement s’affichent pour l’ensemble de l’organisation et peuvent être filtrées à l’aide des options de la liste déroulante des segments sur le côté gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="6329f-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="6329f-114">Dans la partie droite de la liste déroulante du segment, le nombre d’appels par type de média est scindé en affichage interne/externe au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="6329f-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="6329f-115">Dans la capture d’écran ci-dessus, nous pouvons voir plus d’appels à partir d’emplacements d’organisation extérieurs, ce qui est pertinent pour l’environnement global actuel.</span><span class="sxs-lookup"><span data-stu-id="6329f-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="6329f-116">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="6329f-117">À droite de la zone nombre de types de média, nous avons le nombre d’appels mensuels par type de média pour les derniers 90 jours.</span><span class="sxs-lookup"><span data-stu-id="6329f-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="6329f-118">Chaque type de colonne et de média peut être pointé pour afficher le nombre d’un mois précédent ou du mois actuel jusqu’à ce jour, en fournissant des informations de tendance d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="6329f-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="6329f-119">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="6329f-120">Le graphique au milieu ne fonctionne pas comme le graphique de jour de 90, mais il fournit un affichage d’utilisation journalière pour les 30 derniers jours, et permet à un utilisateur de cliquer avec le bouton droit sur les détails d’un jour spécifique.</span><span class="sxs-lookup"><span data-stu-id="6329f-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="6329f-121">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="6329f-122">Dans la section en bas à gauche de la page se trouve un tableau qui fournit des valeurs totales pour chaque type de média au cours de l’année écoulée.</span><span class="sxs-lookup"><span data-stu-id="6329f-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="6329f-123">![Capture d’écran : rapports d’utilisation des équipes ](media/CQD-teams-utilization-report5.png) ![ : rapports d’utilisation des équipes](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="6329f-124">À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="6329f-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="6329f-125">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="6329f-126">Le dernier ensemble de graphiques pour cette page présente chaque type de média individuellement, avec une répartition indiquant une utilisation de conférences et de réseaux P2P.</span><span class="sxs-lookup"><span data-stu-id="6329f-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="6329f-127">Les graphiques ci-dessous montrent qu’il existe un nombre nettement supérieur d’utilisation de conférences par rapport au P2P.</span><span class="sxs-lookup"><span data-stu-id="6329f-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="6329f-128">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="6329f-129">Rapport de synthèse des minutes audio</span><span class="sxs-lookup"><span data-stu-id="6329f-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="6329f-130">Le rapport d’utilisation des minutes audio est fourni dans quelques affichages.</span><span class="sxs-lookup"><span data-stu-id="6329f-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="6329f-131">Le résumé de l’utilisation de l’espace de 30 jours est affiché en regard des segments comme facile à utiliser pour les zones de texte.</span><span class="sxs-lookup"><span data-stu-id="6329f-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="6329f-132">Le numéro supérieur correspond au total du trente jours, avec les répartitions internes et externes.</span><span class="sxs-lookup"><span data-stu-id="6329f-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="6329f-134">Le graphique barre supérieure droite fournit une vue yearlong de l’utilisation de la fonction audio de conférence.</span><span class="sxs-lookup"><span data-stu-id="6329f-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="6329f-135">Pointez sur le mois pour afficher les minutes audio de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6329f-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="6329f-136">Pour afficher la différence entre le son de votre interligne et celle de la conférence téléphonique, le graphique en bas à gauche tire tout le son de l’année dernière et le scinde entre les deux types.</span><span class="sxs-lookup"><span data-stu-id="6329f-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="6329f-138">Le dernier graphique de la page minutes audio montre l’utilisation des minutes audio sur une façade de carte globale.</span><span class="sxs-lookup"><span data-stu-id="6329f-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="6329f-139">Ce graphique ne fonctionnera que si les données de génération et de sous-réseau sont téléchargées vers le client.</span><span class="sxs-lookup"><span data-stu-id="6329f-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="6329f-140">La superposition de graphique en secteurs sur la carte peut être percée, ce qui vous permet de fournir une utilisation audio régionale.</span><span class="sxs-lookup"><span data-stu-id="6329f-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="6329f-142">Fonctionnalités d’analyse approfondie</span><span class="sxs-lookup"><span data-stu-id="6329f-142">Drill-through capabilities</span></span>

<span data-ttu-id="6329f-143">Comme indiqué précédemment, les utilisateurs peuvent explorer les rapports d’utilisation quotidienne et régionale.</span><span class="sxs-lookup"><span data-stu-id="6329f-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="6329f-144">Utilisation quotidienne</span><span class="sxs-lookup"><span data-stu-id="6329f-144">Daily Usage</span></span>

<span data-ttu-id="6329f-145">Le rapport d’utilisation quotidienne permet à un administrateur d’identifier les périodes de forte consommation au cours d’une journée.</span><span class="sxs-lookup"><span data-stu-id="6329f-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="6329f-146">En plus de l’utilisation, nous sommes en mesure de capturer les informations et les commentaires globaux de chaque jour.</span><span class="sxs-lookup"><span data-stu-id="6329f-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="6329f-148">Le rapport activité quotidienne affiche le nombre de partages audio, vidéo et d’écran du jour sélectionné, avec la possibilité de faire la différence entre les connexions internes et externes.</span><span class="sxs-lookup"><span data-stu-id="6329f-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="6329f-149">Une composition de conférence et d’égal à égal (P2P) est à droite de la zone de total modalité.</span><span class="sxs-lookup"><span data-stu-id="6329f-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="6329f-150">Le coin supérieur droit du rapport dresse la liste des conférences avec leur ID et leurs participants correspondants.</span><span class="sxs-lookup"><span data-stu-id="6329f-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="6329f-151">La liste de conférences fournit également une analyse supplémentaire au rapport sur les détails de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6329f-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="6329f-152">REMPLACER LE GRAPHIQUE</span><span class="sxs-lookup"><span data-stu-id="6329f-152">REPLACE GRAPHIC</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="6329f-154">Le graphique à barres dans la zone centrale permet à l’utilisateur d’identifier les périodes de consommation de pointe au cours d’une journée.</span><span class="sxs-lookup"><span data-stu-id="6329f-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="6329f-155">Les utilisateurs peuvent descendre dans l’heure représentée sur le graphique qui présente le rapport de liste d’utilisateurs pour l’heure.</span><span class="sxs-lookup"><span data-stu-id="6329f-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="6329f-156">À droite du graphique à barres, le retour utilisateur est présenté dans un format visuel.</span><span class="sxs-lookup"><span data-stu-id="6329f-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="6329f-157">Bien que l’utilisateur puisse être subjectif, il fournit une vision permettant d’identifier les problèmes potentiels.</span><span class="sxs-lookup"><span data-stu-id="6329f-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="6329f-158">Le tableau inférieur fournit une gamme de métriques pour le jour.</span><span class="sxs-lookup"><span data-stu-id="6329f-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="6329f-159">Des pourcentages insuffisants, ainsi que les taux d’échec, peuvent offrir à un administrateur des zones d’amélioration potentielles.</span><span class="sxs-lookup"><span data-stu-id="6329f-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="6329f-160">Chaque heure peut également être sélectionnée individuellement, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6329f-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="6329f-161">Ces données peuvent être utilisées pour identifier les régions rencontrant des problèmes en temps maximum de consommation.</span><span class="sxs-lookup"><span data-stu-id="6329f-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="6329f-162">Cliquez sur la colonne de ce jour pour afficher les métriques de cette heure.</span><span class="sxs-lookup"><span data-stu-id="6329f-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="6329f-163">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="6329f-164">Le tableau sous le graphique affiche les mesures pour cette heure.</span><span class="sxs-lookup"><span data-stu-id="6329f-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="6329f-165">Vous pouvez trier ce critère par n’importe quel en-tête de colonne. Néanmoins, nous aimerions pouvoir Rechercher les zones problématiques.</span><span class="sxs-lookup"><span data-stu-id="6329f-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="6329f-167">Nous voyons que la région de IND rencontre des performances vidéo médiocres pendant ce laps de temps.</span><span class="sxs-lookup"><span data-stu-id="6329f-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="6329f-168">Par la suite, les rapports Microsoft bord QER peuvent être utilisés pour affiner l’emplacement problématique, car le cadre de la région et de l’heure a été identifié.</span><span class="sxs-lookup"><span data-stu-id="6329f-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="6329f-169">Détails de la Conférence</span><span class="sxs-lookup"><span data-stu-id="6329f-169">Conference Details</span></span>

<span data-ttu-id="6329f-170">Le rapport Détails de la Conférence fournit des informations supplémentaires pour les réunions, de la liste des participants aux types de médias utilisés lors de la session.</span><span class="sxs-lookup"><span data-stu-id="6329f-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="6329f-171">Cliquez avec le bouton droit sur la barre du participant sur le graphique d’ID de conférence sur la page utilisation quotidienne pour explorer les détails de la Conférence.</span><span class="sxs-lookup"><span data-stu-id="6329f-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report24.png)

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="6329f-174">Nous pouvons voir les participants à la Conférence ainsi que les informations pertinentes en matière de perte de paquets et de gigue pour vous aider à résoudre les problèmes potentiels dans le tableau de base.</span><span class="sxs-lookup"><span data-stu-id="6329f-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="6329f-176">Détails audio régionaux</span><span class="sxs-lookup"><span data-stu-id="6329f-176">Regional Audio Details</span></span>

<span data-ttu-id="6329f-177">Les détails audio régionaux d’une analyse descendante montrent en particulier l’utilisation des minutes audio pour la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6329f-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="6329f-178">Les utilisateurs disposant d’un accès à bord peuvent voir les tendances d’utilisation pour les appels audio et vidéo P2P au sein de la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6329f-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="6329f-179">Dans la page Résumé du numéro d’appel, accédez à la zone de recherche en tant que région spécifique dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="6329f-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="6329f-180">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="6329f-181">Sélectionnez la ligne contenant les informations supplémentaires nécessaires pour la région.</span><span class="sxs-lookup"><span data-stu-id="6329f-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="6329f-182">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="6329f-183">Les tendances des données indiquent un nombre considérable de minutes d’utilisation sur le réseau interne, avec une conférence bien plus longue.</span><span class="sxs-lookup"><span data-stu-id="6329f-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="6329f-184">![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="6329f-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="6329f-185">La tendance régionale du son peut être utilisée pour illustrer la façon dont les utilisateurs sont affectés par des influences externes dans le monde.</span><span class="sxs-lookup"><span data-stu-id="6329f-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="6329f-186">Pour l’instant, nous vous attendons d’avoir accès à l’utilisation externe des régions EMEA et APAC qui peuvent être utilisées par les personnes invitées à travailler à distance.</span><span class="sxs-lookup"><span data-stu-id="6329f-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="6329f-187">Liste d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="6329f-187">User List</span></span>

<span data-ttu-id="6329f-188">La liste des utilisateurs permet d’explorer les informations spécifiques à l’utilisateur pour une heure spécifique sélectionnée par la personne qui affiche le rapport.</span><span class="sxs-lookup"><span data-stu-id="6329f-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="6329f-189">Le rapport sur la liste des utilisateurs est accessible par le biais d’une analyse approfondie du graphique tendances d’heures du rapport sur l’utilisation journalière.</span><span class="sxs-lookup"><span data-stu-id="6329f-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="6329f-190">Il suffit de cliquer avec le bouton droit de l’heure pour accéder à des informations supplémentaires et sélectionner extraire vers l’aide d’une liste d’utilisateurs, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6329f-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="6329f-192">Le rapport sur la liste des utilisateurs présente les connexions internes/externes par le biais du graphique en anneau dans le centre supérieur de la page.</span><span class="sxs-lookup"><span data-stu-id="6329f-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="6329f-193">Nous pouvons voir qu’il existe un grand nombre de participations à partir de l’extérieur du réseau d’entreprise dans l’image ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="6329f-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="6329f-194">Le coin supérieur droit du graphique indique le nombre d’appels passés par chaque utilisateur au cours de cette heure.</span><span class="sxs-lookup"><span data-stu-id="6329f-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Capture d’écran : rapports d’utilisation des équipes](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="6329f-196">Le tableau inférieur fournit des informations détaillées sur les sessions auxquelles un utilisateur a participé au cours de cette heure.</span><span class="sxs-lookup"><span data-stu-id="6329f-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="6329f-197">La colonne type d’échec permet de déterminer le résultat d’un appel.</span><span class="sxs-lookup"><span data-stu-id="6329f-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="6329f-198">Les colonnes d’appareil de capture et de rendu sont utiles dans l’identification de la raison pour laquelle un appel a été signalé d’une mauvaise qualité.</span><span class="sxs-lookup"><span data-stu-id="6329f-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="6329f-199">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6329f-199">Related topics</span></span>

[<span data-ttu-id="6329f-200">Dimensions et mesures disponibles dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="6329f-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="6329f-201">Classification de flux de données dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="6329f-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="6329f-202">Configurer l'analyse des appels Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="6329f-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="6329f-203">Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="6329f-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="6329f-204">Tableau de bord Analyse des appels et Qualité des appels</span><span class="sxs-lookup"><span data-stu-id="6329f-204">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

[<span data-ttu-id="6329f-205">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="6329f-205">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
 