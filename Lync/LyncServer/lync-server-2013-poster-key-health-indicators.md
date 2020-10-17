---
title: 'Lync Server 2013 : affiche : indicateurs d’intégrité clés'
description: 'Lync Server 2013 : affiche : indicateurs d’intégrité clés.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566340"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="acb50-103">Indicateurs d’intégrité clés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="acb50-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="acb50-104">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="acb50-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="acb50-105">Cet article est un complément des [indicateurs d’intégrité clés : la base pour la maintenance de l’affiche des serveurs Lync sains](https://go.microsoft.com/fwlink/?linkid=391838) , que vous pouvez télécharger à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="acb50-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="acb50-106">![Affiche décrivant le dépannage à l’aide de données KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Affiche décrivant le dépannage à l’aide de données KHI")</span><span class="sxs-lookup"><span data-stu-id="acb50-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="acb50-107">Vous pouvez utiliser cette affiche pour en savoir plus sur les indicateurs d’intégrité clés (KHIs), les compteurs de performance avec des seuils visant à révéler des problèmes d’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="acb50-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="acb50-108">La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="acb50-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="acb50-109">Si vous avez des questions sur l’utilisation de CQM, vous pouvez soumettre vos questions à cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="acb50-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="acb50-110">L’affiche décrit les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="acb50-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="acb50-111">Qu’est-ce que les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="acb50-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="acb50-112">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="acb50-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="acb50-113">Flux de correction pour tous les rôles serveur</span><span class="sxs-lookup"><span data-stu-id="acb50-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="acb50-114">Glossaire</span><span class="sxs-lookup"><span data-stu-id="acb50-114">Glossary</span></span>

  - <span data-ttu-id="acb50-115">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="acb50-115">Front-end Servers</span></span>

  - <span data-ttu-id="acb50-116">Serveurs SQL principaux</span><span class="sxs-lookup"><span data-stu-id="acb50-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="acb50-117">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="acb50-117">Mediation Servers</span></span>

  - <span data-ttu-id="acb50-118">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="acb50-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="acb50-119">Qu’est-ce que les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="acb50-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="acb50-120">Les indicateurs d’intégrité clés sont des compteurs de performance dont les seuils visent à révéler des problèmes d’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="acb50-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="acb50-121">La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="acb50-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="acb50-122">Les KHIs sont utilisés en plus des solutions de surveillance Lync standard (par exemple, System Center Operations Manager, les transactions synthétiques, le serveur de surveillance) et non pas ces solutions.</span><span class="sxs-lookup"><span data-stu-id="acb50-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="acb50-123">Recueillez les compteurs de performance KHI et remplissez la feuille de calcul KHI accompagnant le Guide de mise en réseau pour produire une carte de performance qui vous permettra de déterminer l’intégrité du serveur d’un déploiement Lync.</span><span class="sxs-lookup"><span data-stu-id="acb50-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="acb50-124">Une fois renseigné, il vous guide lors de la réparation de l’environnement et apporte un aperçu supplémentaire aux autres parties prenantes.</span><span class="sxs-lookup"><span data-stu-id="acb50-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="acb50-125">Évaluez KHIs chaque mois et incorporez-les dans les processus opérationnels en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="acb50-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="acb50-126">Téléchargez le [Guide de mise en réseau Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) pour voir la liste complète des KHIs et obtenir les feuilles de calcul connexes.</span><span class="sxs-lookup"><span data-stu-id="acb50-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="acb50-127">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="acb50-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="acb50-128">Exécutez le script KHI inclus dans le Guide de mise en réseau Lync Server sur chaque serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="acb50-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="acb50-129">Cette opération crée un collecteur de données à l’intérieur de l’analyseur de performances et le nomme KHI.</span><span class="sxs-lookup"><span data-stu-id="acb50-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="acb50-130">Par défaut, les données sont interrogées toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="acb50-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="acb50-131">Avant le début de la journée de travail de votre entreprise, accédez à chaque serveur Lync Server et démarrez le collecteur de données KHI.</span><span class="sxs-lookup"><span data-stu-id="acb50-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="acb50-132">À la fin de ce jour, arrêtez le collecteur de données KHI et copiez les données vers un emplacement central.</span><span class="sxs-lookup"><span data-stu-id="acb50-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="acb50-133">Après avoir utilisé l’analyseur de performances pour remplir la feuille de calcul KHI incluse avec le téléchargement du Guide de mise en réseau Lync Server, comparez les résultats aux cibles recommandées.</span><span class="sxs-lookup"><span data-stu-id="acb50-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="acb50-134">Flux de correction pour tous les rôles serveur</span><span class="sxs-lookup"><span data-stu-id="acb50-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="acb50-135">Pour chaque serveur de votre implémentation Lync, commencez par vérifier que les performances du système et de l’intégrité des composants du serveur sont égales ou supérieures au niveau souhaité.</span><span class="sxs-lookup"><span data-stu-id="acb50-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="acb50-136">Uniquement après cela, vous devez examiner les indicateurs relatifs au rôle du serveur dans l’implémentation globale de Lync.</span><span class="sxs-lookup"><span data-stu-id="acb50-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="acb50-137">Commencez par collecter les données de performances KHI pour tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="acb50-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="acb50-138">Pour chaque rôle système (détails abordés plus loin dans ce document), déterminez si les composants système de base satisfont aux objectifs recommandés.</span><span class="sxs-lookup"><span data-stu-id="acb50-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="acb50-139">Si ce n’est pas le cas, corrigez les performances du système, puis rerecueillez les données KHI et assurez-vous que le système est en mesure d’examiner les mesures propres au rôle du serveur dans l’implémentation Lync.</span><span class="sxs-lookup"><span data-stu-id="acb50-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="acb50-140">L’intégrité des composants de tous les rôles est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="acb50-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="acb50-141">Utilisation de l’UC \< 80%</span><span class="sxs-lookup"><span data-stu-id="acb50-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="acb50-142">Moy. disque écriture \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="acb50-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="acb50-143">Moy. disk read \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="acb50-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="acb50-144">Mémoire disponible \> 20% système total Mo</span><span class="sxs-lookup"><span data-stu-id="acb50-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="acb50-145">Longueur de la file d’attente réseau \< 2</span><span class="sxs-lookup"><span data-stu-id="acb50-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="acb50-146">Paquets ignorés (entrée/sortie) = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="acb50-147">Glossaire</span><span class="sxs-lookup"><span data-stu-id="acb50-147">Glossary</span></span>

<span data-ttu-id="acb50-148">Les termes et acronymes suivants sont utilisés dans cette affiche :</span><span class="sxs-lookup"><span data-stu-id="acb50-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="acb50-149">AS MCU = unité de contrôle multipoint de partage d’application</span><span class="sxs-lookup"><span data-stu-id="acb50-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="acb50-150">MCU AV = audio/vidéo MCU</span><span class="sxs-lookup"><span data-stu-id="acb50-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="acb50-151">MCU de messagerie instantanée = MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="acb50-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="acb50-152">UCWA = API Web de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="acb50-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="acb50-153">Serveur Edge AV = parcours audio/vidéo via le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="acb50-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="acb50-154">Authentification AV = authentification audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="acb50-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="acb50-155">Pile SIP = contient la mise en œuvre SIP principale de Lync</span><span class="sxs-lookup"><span data-stu-id="acb50-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="acb50-156">Proxy de données = utilisé pour la Conférence Edge</span><span class="sxs-lookup"><span data-stu-id="acb50-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="acb50-157">LySS = service de stockage Lync</span><span class="sxs-lookup"><span data-stu-id="acb50-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="acb50-158">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="acb50-158">Front-end Servers</span></span>

<span data-ttu-id="acb50-159">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs frontaux :</span><span class="sxs-lookup"><span data-stu-id="acb50-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acb50-160">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="acb50-160">Functional area</span></span></th>
<th><span data-ttu-id="acb50-161">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="acb50-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acb50-162">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="acb50-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="acb50-163">État d’intégrité de la MCU &lt; 2</span><span class="sxs-lookup"><span data-stu-id="acb50-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb50-164">Composants Web</span><span class="sxs-lookup"><span data-stu-id="acb50-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="acb50-165">Délais d’attente de l’extension de liste de distribution &lt; 0</span><span class="sxs-lookup"><span data-stu-id="acb50-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="acb50-166">Échecs ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="acb50-167">Échecs LIS = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="acb50-168">Erreurs d’authentification &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="acb50-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="acb50-169">Demandes v4 ASP.NET rejetées = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acb50-170">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="acb50-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="acb50-171">Traitement des messages entrants moy. &lt;</span><span class="sxs-lookup"><span data-stu-id="acb50-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="acb50-172">Réponses entrantes supprimées &lt; 1/s requêtes entrantes abandonnées &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="acb50-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="acb50-173">Latence de file d’attente &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="acb50-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="acb50-174">Latence de la sproc &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="acb50-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="acb50-175">Demandes limitées = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="acb50-176">Erreurs d’authentification &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="acb50-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="acb50-177">Messages entrants expirés &lt; 2</span><span class="sxs-lookup"><span data-stu-id="acb50-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="acb50-178">Durée moyenne de blocage des messages entrants &lt; 1 seconde</span><span class="sxs-lookup"><span data-stu-id="acb50-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="acb50-179">Connexions avec contrôle de flux &lt; 2</span><span class="sxs-lookup"><span data-stu-id="acb50-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="acb50-180">&lt;Retard moy.</span><span class="sxs-lookup"><span data-stu-id="acb50-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb50-181">LySS</span><span class="sxs-lookup"><span data-stu-id="acb50-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="acb50-182">% de l’espace utilisé par le service de stockage DB &lt; 80</span><span class="sxs-lookup"><span data-stu-id="acb50-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="acb50-183"># d’échecs de réplication de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="acb50-184"># des événements de perte de données = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acb50-185">SQL</span><span class="sxs-lookup"><span data-stu-id="acb50-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="acb50-186">Durée de vie de la page &gt; 300 s.</span><span class="sxs-lookup"><span data-stu-id="acb50-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="acb50-187">Demandes par lots/s &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="acb50-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="acb50-188">Serveurs SQL principaux</span><span class="sxs-lookup"><span data-stu-id="acb50-188">Backend SQL Servers</span></span>

<span data-ttu-id="acb50-189">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs SQL :</span><span class="sxs-lookup"><span data-stu-id="acb50-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acb50-190">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="acb50-190">Functional area</span></span></th>
<th><span data-ttu-id="acb50-191">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="acb50-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acb50-192">SQL</span><span class="sxs-lookup"><span data-stu-id="acb50-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="acb50-193">Durée de vie de la page &gt; 300 s.</span><span class="sxs-lookup"><span data-stu-id="acb50-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="acb50-194">Demandes par lots/s &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="acb50-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="acb50-195">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="acb50-195">Mediation Servers</span></span>

<span data-ttu-id="acb50-196">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs de médiation :</span><span class="sxs-lookup"><span data-stu-id="acb50-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acb50-197">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="acb50-197">Functional area</span></span></th>
<th><span data-ttu-id="acb50-198">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="acb50-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acb50-199">Service de médiation</span><span class="sxs-lookup"><span data-stu-id="acb50-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="acb50-200">Index d’échec de l’appel de chargement = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="acb50-201">Appels ayant échoué en raison du proxy &lt; 10</span><span class="sxs-lookup"><span data-stu-id="acb50-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="acb50-202">Appels ayant échoué en raison de la passerelle &lt; 10</span><span class="sxs-lookup"><span data-stu-id="acb50-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="acb50-203">Appels (entrants ou sortants) rejetés = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="acb50-204">Candidats multimédias manquants = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="acb50-205">Échecs de vérification de la connectivité des médias = 0</span><span class="sxs-lookup"><span data-stu-id="acb50-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="acb50-206">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="acb50-206">Edge Servers</span></span>

<span data-ttu-id="acb50-207">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs Edge :</span><span class="sxs-lookup"><span data-stu-id="acb50-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="acb50-208">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="acb50-208">Functional area</span></span></th>
<th><span data-ttu-id="acb50-209">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="acb50-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="acb50-210">Authentification AV</span><span class="sxs-lookup"><span data-stu-id="acb50-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="acb50-211">Demandes incorrectes &lt; 20/s</span><span class="sxs-lookup"><span data-stu-id="acb50-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb50-212">Serveur Edge AV</span><span class="sxs-lookup"><span data-stu-id="acb50-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="acb50-213">Échecs d’authentification &lt; 20/s</span><span class="sxs-lookup"><span data-stu-id="acb50-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="acb50-214">Échecs de répartition &lt; 20/s</span><span class="sxs-lookup"><span data-stu-id="acb50-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="acb50-215">Paquets supprimés &lt; 300/s</span><span class="sxs-lookup"><span data-stu-id="acb50-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="acb50-216">Proxy de données</span><span class="sxs-lookup"><span data-stu-id="acb50-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="acb50-217">Connexions serveur limitées &lt; 3</span><span class="sxs-lookup"><span data-stu-id="acb50-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="acb50-218">Le système est limité à &lt; 1</span><span class="sxs-lookup"><span data-stu-id="acb50-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="acb50-219">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="acb50-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="acb50-220">Connexions au-delà de la limite ignorée &lt; 1</span><span class="sxs-lookup"><span data-stu-id="acb50-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="acb50-221">Envoi expiré &lt; 10</span><span class="sxs-lookup"><span data-stu-id="acb50-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="acb50-222">Connexions contrôlées par flux &lt; 100</span><span class="sxs-lookup"><span data-stu-id="acb50-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="acb50-223">Demandes entrantes abandonnées &lt; 1/s</span><span class="sxs-lookup"><span data-stu-id="acb50-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="acb50-224">Traitement de message moy. &lt; 3 s</span><span class="sxs-lookup"><span data-stu-id="acb50-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="acb50-225">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="acb50-225">See Also</span></span>


[<span data-ttu-id="acb50-226">Guide de mise en réseau Lync Server</span><span class="sxs-lookup"><span data-stu-id="acb50-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="acb50-227">Indicateurs d’intégrité clés : base pour la maintenance des serveurs Lync sains</span><span class="sxs-lookup"><span data-stu-id="acb50-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="acb50-228">Méthodologie de qualité des appels Lync</span><span class="sxs-lookup"><span data-stu-id="acb50-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

