---
title: Utilisation de Microsoft Teams dans Power BI à l’aide de données du CQD
ms.author: serdars
author: SerdarSoysal
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
description: Utilisez les rapports Power BI Utilisation des équipes pour accéder aux données du tableau de bord de qualité des appels de Microsoft Teams afin de suivre l’utilisation de Microsoft Teams dans votre organisation.
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095038"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="83aeb-103">Utilisation de Microsoft Teams dans Power BI à l’aide de données du CQD</span><span class="sxs-lookup"><span data-stu-id="83aeb-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="83aeb-104">Nouveautés de mars 2020, nous avons ajouté un rapport Utilisation de Teams à nos modèles de requête Power BI téléchargeables pour le bon de [recherche de contenu.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="83aeb-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="83aeb-105">Ce nouveau rapport Utilisation des équipes vous permet de voir comment (et combien) vos utilisateurs utilisent Microsoft Teams en accédant aux données du tableau de bord de qualité des appels de Teams.</span><span class="sxs-lookup"><span data-stu-id="83aeb-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="83aeb-106">Ces rapports sont destinés à être un emplacement centralisé que les administrateurs et les chefs d’entreprise peuvent rapidement utiliser pour ces données.</span><span class="sxs-lookup"><span data-stu-id="83aeb-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="83aeb-107">Le rapport Utilisation de Power BI sur Teams se compose de deux rapports principaux : **[Le récapitulatif](#call-count-summary-report)** des appels et le résumé **[des minutes audio.](#audio-minutes-summary-report)**</span><span class="sxs-lookup"><span data-stu-id="83aeb-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="83aeb-108">[L’utilisation quotidienne,](#daily-usage)les [détails](#regional-audio-details)audio [](#user-list) régionaux, les détails des conférences et les rapports de la liste d’utilisateurs sont pris en compte lorsqu’un utilisateur tire parti des rapports d’analyse détaillée, comme indiqué dans les descriptions ci-dessous. [](#conference-details)</span><span class="sxs-lookup"><span data-stu-id="83aeb-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="83aeb-109">Les données de bâtiment et de sous-réseau doivent être remplies pour fournir des fonctionnalités de filtrage réseau et régionales.</span><span class="sxs-lookup"><span data-stu-id="83aeb-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="83aeb-110">Rapport de synthèse du nombre d’appels</span><span class="sxs-lookup"><span data-stu-id="83aeb-110">Call Count Summary Report</span></span>

<span data-ttu-id="83aeb-111">La page principale (call Count Summary) fournit immédiatement le nombre de sessions audio, vidéo et de partage d’écran au cours des 30 et 90 derniers jours, comme indiqué dans le titre de la section.</span><span class="sxs-lookup"><span data-stu-id="83aeb-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="83aeb-112">Les données initialement affichées s’affichent pour l’organisation dans son ensemble et peuvent être filtrées à l’aide des options de filtrage de la partie gauche de la page.</span><span class="sxs-lookup"><span data-stu-id="83aeb-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="83aeb-114">À droite des dropdowns de slicer, le nombre d’appels par type de média est décomposé en vue interne/externe au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="83aeb-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="83aeb-115">Nous pouvons voir via la capture d’écran ci-dessus qu’il y a davantage d’appels en provenance d’emplacements organisationnels extérieurs, ce qui est logique dans l’environnement global actuel.</span><span class="sxs-lookup"><span data-stu-id="83aeb-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="83aeb-116">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="83aeb-117">À droite de la zone du nombre de types de médias, nous avons le nombre d’appels mensuels par type de média au cours des 90 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="83aeb-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="83aeb-118">Vous pouvez pointer sur chaque colonne et chaque type de média pour afficher le nombre de mois précédent ou de mois en cours à ce jour, afin de fournir des informations sur la tendance d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="83aeb-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="83aeb-119">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="83aeb-120">Le graphique du milieu fonctionne comme le graphique de 90 jours. Toutefois, il fournit un affichage de l’utilisation quotidienne pour les 30 derniers jours et permet à un utilisateur de cliquer avec le bouton droit et d’descendre dans les détails pour un jour spécifique.</span><span class="sxs-lookup"><span data-stu-id="83aeb-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="83aeb-121">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="83aeb-122">Dans la section inférieure gauche de la page, vous trouverez un tableau fournissant les valeurs totales de chaque type de média au cours de l’année précédente.</span><span class="sxs-lookup"><span data-stu-id="83aeb-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="83aeb-123">![Capture d’écran : Capture d’écran des rapports d’utilisation des équipes ](media/CQD-teams-utilization-report5.png) ![ : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="83aeb-124">À droite du tableau, un graphique à barres affiche les clients les plus utilisés (appels/flux) au cours des 30 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="83aeb-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="83aeb-125">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="83aeb-126">Le dernier ensemble de graphiques pour cette page affiche chaque type de média individuellement, avec une répartition montrant l’utilisation des conférences et P2P.</span><span class="sxs-lookup"><span data-stu-id="83aeb-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="83aeb-127">Les graphiques ci-dessous indiquent qu’il y a un nombre d’utilisation des conférences considérablement plus élevé que P2P.</span><span class="sxs-lookup"><span data-stu-id="83aeb-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="83aeb-128">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="83aeb-129">Rapport de synthèse des minutes audio</span><span class="sxs-lookup"><span data-stu-id="83aeb-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="83aeb-130">Dans le rapport d’utilisation des minutes audio, le total des minutes d’utilisation est indiqué sur plusieurs affichages.</span><span class="sxs-lookup"><span data-stu-id="83aeb-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="83aeb-131">Le résumé de l’utilisation sur 30 jours est présenté à côté des slicers pour vous aider à consommer des zones de texte.</span><span class="sxs-lookup"><span data-stu-id="83aeb-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="83aeb-132">Le nombre supérieur affiche le total de trente jours, avec des répartitions internes et externes en dessous.</span><span class="sxs-lookup"><span data-stu-id="83aeb-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="83aeb-134">Le graphique à barres supérieure droite offre un affichage annuel de l’utilisation de l’audio dans les conférences.</span><span class="sxs-lookup"><span data-stu-id="83aeb-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="83aeb-135">Placez le pointez sur le mois pour afficher les minutes audio de la conférence.</span><span class="sxs-lookup"><span data-stu-id="83aeb-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="83aeb-136">Pour afficher la différence en audio P2P et en conférence, le graphique en bas à gauche prend tout l’audio de l’année passée et le décompose entre les deux types.</span><span class="sxs-lookup"><span data-stu-id="83aeb-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="83aeb-138">Le dernier graphique de la page Minutes audio affiche l’utilisation des minutes audio sur une carte globale superposée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="83aeb-139">Ce graphique ne fonctionne que si des données bâtiment et sous-réseau sont téléchargées sur le client.</span><span class="sxs-lookup"><span data-stu-id="83aeb-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="83aeb-140">Il est possible d’utiliser le graphique en secteurs superposé sur la carte pour fournir par la suite une utilisation audio régionale.</span><span class="sxs-lookup"><span data-stu-id="83aeb-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="83aeb-142">Fonctionnalités d’analyse</span><span class="sxs-lookup"><span data-stu-id="83aeb-142">Drill-through capabilities</span></span>

<span data-ttu-id="83aeb-143">Comme indiqué précédemment, les utilisateurs peuvent utiliser les rapports d’utilisation quotidiennes et régionaux.</span><span class="sxs-lookup"><span data-stu-id="83aeb-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="83aeb-144">Utilisation quotidienne</span><span class="sxs-lookup"><span data-stu-id="83aeb-144">Daily Usage</span></span>

<span data-ttu-id="83aeb-145">Le rapport Utilisation quotidienne permet à un administrateur d’identifier les pics de consommation tout au long d’une journée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="83aeb-146">En plus de l’utilisation, nous sommes également en mesure de capturer les opinions globales des utilisateurs et les commentaires pour ce jour.</span><span class="sxs-lookup"><span data-stu-id="83aeb-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="83aeb-148">Le rapport Utilisation quotidienne affiche le nombre de partages d’écran, audio et vidéo pour le jour sélectionné, avec une possibilité supplémentaire de différencier les connectivité interne et externe.</span><span class="sxs-lookup"><span data-stu-id="83aeb-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="83aeb-149">Une répartition de conférence et d’égal à égal est à la droite immédiate de la zone de total de la modalité.</span><span class="sxs-lookup"><span data-stu-id="83aeb-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="83aeb-150">La partie supérieure droite du rapport fournit la liste des conférences qui se sont tenues à l’aide de leur ID et des participants de la journée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="83aeb-151">La liste des conférences fournit également une analyse supplémentaire du rapport des détails de la conférence.</span><span class="sxs-lookup"><span data-stu-id="83aeb-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="83aeb-152">REPLACE GRAPHIC</span><span class="sxs-lookup"><span data-stu-id="83aeb-152">REPLACE GRAPHIC</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="83aeb-154">Le graphique à barres dans la zone centrale permet à l’utilisateur d’identifier les pics de consommation tout au long d’une journée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="83aeb-155">Les utilisateurs peuvent descendre dans l’heure représentée sur le graphique qui présente le rapport Liste utilisateur pour l’heure.</span><span class="sxs-lookup"><span data-stu-id="83aeb-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="83aeb-156">À droite du graphique à barres, les commentaires des utilisateurs sont présentés dans un format visuel.</span><span class="sxs-lookup"><span data-stu-id="83aeb-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="83aeb-157">Bien que les opinions des utilisateurs soient subjectifs, elles fournissent des informations permettant d’identifier les problèmes potentiels.</span><span class="sxs-lookup"><span data-stu-id="83aeb-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="83aeb-158">Le tableau inférieur fournit une plage d’indicateurs pour la journée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="83aeb-159">Des pourcentages médiocres et des taux d’échec peuvent fournir à un administrateur les domaines d’amélioration potentiels.</span><span class="sxs-lookup"><span data-stu-id="83aeb-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="83aeb-160">Chaque heure peut également être sélectionnée individuellement, comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="83aeb-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="83aeb-161">Ces données peuvent être utilisées pour identifier les régions qui ont des problèmes pendant les pics de consommation.</span><span class="sxs-lookup"><span data-stu-id="83aeb-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="83aeb-162">Cliquez sur la colonne de ce jour pour afficher des mesures pour cette heure.</span><span class="sxs-lookup"><span data-stu-id="83aeb-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="83aeb-163">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="83aeb-164">Le tableau sous le graphique affiche les mesures pour cette heure.</span><span class="sxs-lookup"><span data-stu-id="83aeb-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="83aeb-165">Celui-ci peut être trié sur n’importe quel en-tête de colonne . toutefois, nous nous intéressent à la recherche de domaines problématiques.</span><span class="sxs-lookup"><span data-stu-id="83aeb-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="83aeb-167">Nous voyons que la région IND connaît des performances vidéo médiocres lors des conférences pendant cette période.</span><span class="sxs-lookup"><span data-stu-id="83aeb-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="83aeb-168">Par la suite, les rapports Microsoft QER du CQD peuvent être utilisés pour restreindre l’emplacement problématique à mesure que la région et la période ont été identifiées.</span><span class="sxs-lookup"><span data-stu-id="83aeb-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="83aeb-169">Détails de la conférence</span><span class="sxs-lookup"><span data-stu-id="83aeb-169">Conference Details</span></span>

<span data-ttu-id="83aeb-170">Le rapport des détails de la conférence fournit des informations supplémentaires sur les réunions (liste des participants, types de médias utilisés pendant la session).</span><span class="sxs-lookup"><span data-stu-id="83aeb-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="83aeb-171">Cliquez avec le bouton droit sur une conférence dans la barre d’ID de conférence sur la page Utilisation quotidienne pour consulter les détails de la conférence.</span><span class="sxs-lookup"><span data-stu-id="83aeb-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report24.png)

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="83aeb-174">Nous pouvons voir les participants à la conférence ainsi que toutes les informations pertinentes sur la perte de paquets et la gigue pour aider à résoudre les problèmes potentiels dans le tableau inférieur.</span><span class="sxs-lookup"><span data-stu-id="83aeb-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="83aeb-176">Détails de l’audio régional</span><span class="sxs-lookup"><span data-stu-id="83aeb-176">Regional Audio Details</span></span>

<span data-ttu-id="83aeb-177">L’analyse Regional Audio Details présente particulièrement l’utilisation des minutes audio pour la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="83aeb-178">Les utilisateurs ayant accès au DQD peuvent voir les tendances d’utilisation du P2P et de l’audio de conférence dans la région sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="83aeb-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="83aeb-179">Dans la page Récapitulatif du nombre d’appels, recherchez une région spécifique dans la table.</span><span class="sxs-lookup"><span data-stu-id="83aeb-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="83aeb-180">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="83aeb-181">Sélectionnez la ligne pour qui vous avez besoin d’informations supplémentaires sur la région.</span><span class="sxs-lookup"><span data-stu-id="83aeb-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="83aeb-182">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="83aeb-183">Les tendances de données montrent un nombre important de minutes utilisées sur le réseau interne, avec une utilisation P2P beaucoup plus importante.</span><span class="sxs-lookup"><span data-stu-id="83aeb-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="83aeb-184">![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="83aeb-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="83aeb-185">La tendance audio régionale peut être utilisée pour montrer l’impact des utilisateurs sur les influences externes dans le monde.</span><span class="sxs-lookup"><span data-stu-id="83aeb-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="83aeb-186">Plus précisément, à l’heure actuelle, nous nous attendions à ce que l’utilisation externe des régions EMEA et APAC augmente avec le travail à distance des personnes invitées à travailler à distance.</span><span class="sxs-lookup"><span data-stu-id="83aeb-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="83aeb-187">Liste d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="83aeb-187">User List</span></span>

<span data-ttu-id="83aeb-188">La liste des utilisateurs descend dans la liste fournit, comme on peut s’y attendre, des informations spécifiques à l’utilisateur pour une heure spécifique sélectionnée par la personne qui affiche le rapport.</span><span class="sxs-lookup"><span data-stu-id="83aeb-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="83aeb-189">Le rapport Liste d’utilisateurs est accessible via une recherche dans le graphique Tendances horaires du rapport Utilisation quotidienne.</span><span class="sxs-lookup"><span data-stu-id="83aeb-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="83aeb-190">Cliquez avec le bouton droit sur l’heure pour obtenir les informations supplémentaires nécessaires, puis sélectionnez Drill through and User List (Liste d’utilisateurs), comme illustré ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="83aeb-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="83aeb-192">Le rapport Liste d’utilisateurs affiche la connectivité interne/externe via le graphique en doughnuts en haut au centre de la page.</span><span class="sxs-lookup"><span data-stu-id="83aeb-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="83aeb-193">L’image ci-dessous montre qu’un large nombre de participants se trouve en dehors du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="83aeb-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="83aeb-194">La partie supérieure droite du graphique indique le nombre d’appels effectués par chaque utilisateur dans l’heure.</span><span class="sxs-lookup"><span data-stu-id="83aeb-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![Capture d’écran : Rapports d’utilisation des équipes](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="83aeb-196">Le tableau inférieur fournit des informations détaillées sur les sessions à qui chaque utilisateur a participé au cours de cette heure.</span><span class="sxs-lookup"><span data-stu-id="83aeb-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="83aeb-197">La colonne Type d’échec est utile pour déterminer ce qui a provoqué la chute d’un appel.</span><span class="sxs-lookup"><span data-stu-id="83aeb-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="83aeb-198">Les colonnes Du périphérique de capture et de rendu sont utiles pour identifier la raison pour laquelle un appel a été signalé pour une qualité médiocre.</span><span class="sxs-lookup"><span data-stu-id="83aeb-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="83aeb-199">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="83aeb-199">Related topics</span></span>

[<span data-ttu-id="83aeb-200">Dimensions et mesures disponibles dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="83aeb-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="83aeb-201">Classification de flux de données dans le tableau de bord de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="83aeb-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="83aeb-202">Configurer l'analyse des appels Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="83aeb-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="83aeb-203">Utiliser l’analyse des appels pour résoudre les problèmes de qualité des appels</span><span class="sxs-lookup"><span data-stu-id="83aeb-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="83aeb-204">Tableau de bord Analyse des appels et Qualité des appels</span><span class="sxs-lookup"><span data-stu-id="83aeb-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="83aeb-205">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="83aeb-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
