---
title: 'Lync Server 2013 : affiche : indicateurs d’intégrité clés'
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
ms.openlocfilehash: aca31ca681c75438bbcbb67b1d2dc5c0b6305cb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="7fdf9-102">Indicateurs d’intégrité clés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7fdf9-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fdf9-103">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="7fdf9-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="7fdf9-104">Cet article est un complément des [indicateurs d’intégrité clés : la base pour la maintenance de l’affiche des serveurs Lync sains](https://go.microsoft.com/fwlink/?linkid=391838) , que vous pouvez télécharger à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="7fdf9-105">![Affiche décrivant le dépannage à l’aide de données KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Affiche décrivant le dépannage à l’aide de données KHI")</span><span class="sxs-lookup"><span data-stu-id="7fdf9-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="7fdf9-106">Vous pouvez utiliser cette affiche pour en savoir plus sur les indicateurs d’intégrité clés (KHIs), les compteurs de performance avec des seuils visant à révéler des problèmes d’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="7fdf9-107">La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="7fdf9-108">Si vous avez des questions sur l’utilisation de CQM, vous pouvez soumettre vos questions à cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="7fdf9-109">L’affiche décrit les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="7fdf9-110">Qu’est-ce que les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="7fdf9-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="7fdf9-111">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="7fdf9-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="7fdf9-112">Flux de correction pour tous les rôles serveur</span><span class="sxs-lookup"><span data-stu-id="7fdf9-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="7fdf9-113">Glossaire</span><span class="sxs-lookup"><span data-stu-id="7fdf9-113">Glossary</span></span>

  - <span data-ttu-id="7fdf9-114">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="7fdf9-114">Front-end Servers</span></span>

  - <span data-ttu-id="7fdf9-115">Serveurs SQL principaux</span><span class="sxs-lookup"><span data-stu-id="7fdf9-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="7fdf9-116">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="7fdf9-116">Mediation Servers</span></span>

  - <span data-ttu-id="7fdf9-117">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="7fdf9-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="7fdf9-118">Qu’est-ce que les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="7fdf9-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="7fdf9-119">Les indicateurs d’intégrité clés sont des compteurs de performance dont les seuils visent à révéler des problèmes d’expérience utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="7fdf9-120">La collecte de données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui est axée sur la qualité audio pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="7fdf9-121">Les KHIs sont utilisés en plus des solutions de surveillance Lync standard (par exemple, System Center Operations Manager, les transactions synthétiques, le serveur de surveillance) et non pas ces solutions.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="7fdf9-122">Recueillez les compteurs de performance KHI et remplissez la feuille de calcul KHI accompagnant le Guide de mise en réseau pour produire une carte de performance qui vous permettra de déterminer l’intégrité du serveur d’un déploiement Lync.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="7fdf9-123">Une fois renseigné, il vous guide lors de la réparation de l’environnement et apporte un aperçu supplémentaire aux autres parties prenantes.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="7fdf9-124">Évaluez KHIs chaque mois et incorporez-les dans les processus opérationnels en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="7fdf9-125">Téléchargez le [Guide de mise en réseau Lync Server](https://go.microsoft.com/fwlink/p/?linkid=390677) pour voir la liste complète des KHIs et obtenir les feuilles de calcul connexes.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="7fdf9-126">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="7fdf9-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="7fdf9-127">Exécutez le script KHI inclus dans le Guide de mise en réseau Lync Server sur chaque serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="7fdf9-128">Cette opération crée un collecteur de données à l’intérieur de l’analyseur de performances et le nomme KHI.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="7fdf9-129">Par défaut, les données sont interrogées toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="7fdf9-130">Avant le début de la journée de travail de votre entreprise, accédez à chaque serveur Lync Server et démarrez le collecteur de données KHI.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="7fdf9-131">À la fin de ce jour, arrêtez le collecteur de données KHI et copiez les données vers un emplacement central.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="7fdf9-132">Après avoir utilisé l’analyseur de performances pour remplir la feuille de calcul KHI incluse avec le téléchargement du Guide de mise en réseau Lync Server, comparez les résultats aux cibles recommandées.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="7fdf9-133">Flux de correction pour tous les rôles serveur</span><span class="sxs-lookup"><span data-stu-id="7fdf9-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="7fdf9-134">Pour chaque serveur de votre implémentation Lync, commencez par vérifier que les performances du système et de l’intégrité des composants du serveur sont égales ou supérieures au niveau souhaité.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="7fdf9-135">Uniquement après cela, vous devez examiner les indicateurs relatifs au rôle du serveur dans l’implémentation globale de Lync.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="7fdf9-136">Commencez par collecter les données de performances KHI pour tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="7fdf9-137">Pour chaque rôle système (détails abordés plus loin dans ce document), déterminez si les composants système de base satisfont aux objectifs recommandés.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="7fdf9-138">Si ce n’est pas le cas, corrigez les performances du système, puis rerecueillez les données KHI et assurez-vous que le système est en mesure d’examiner les mesures propres au rôle du serveur dans l’implémentation Lync.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="7fdf9-139">L’intégrité des composants de tous les rôles est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="7fdf9-140">Utilisation de \< l’UC 80%</span><span class="sxs-lookup"><span data-stu-id="7fdf9-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="7fdf9-141">Moy. disque écriture \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="7fdf9-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="7fdf9-142">Moy. disk read \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="7fdf9-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="7fdf9-143">Mémoire \>disponible 20% système total Mo</span><span class="sxs-lookup"><span data-stu-id="7fdf9-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="7fdf9-144">Longueur \< de la file d’attente réseau 2</span><span class="sxs-lookup"><span data-stu-id="7fdf9-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="7fdf9-145">Paquets ignorés (entrée/sortie) = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="7fdf9-146">Glossaire</span><span class="sxs-lookup"><span data-stu-id="7fdf9-146">Glossary</span></span>

<span data-ttu-id="7fdf9-147">Les termes et acronymes suivants sont utilisés dans cette affiche :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="7fdf9-148">AS MCU = unité de contrôle multipoint de partage d’application</span><span class="sxs-lookup"><span data-stu-id="7fdf9-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="7fdf9-149">MCU AV = audio/vidéo MCU</span><span class="sxs-lookup"><span data-stu-id="7fdf9-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="7fdf9-150">MCU de messagerie instantanée = MCU de messagerie instantanée</span><span class="sxs-lookup"><span data-stu-id="7fdf9-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="7fdf9-151">UCWA = API Web de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="7fdf9-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="7fdf9-152">Serveur Edge AV = parcours audio/vidéo via le serveur Edge</span><span class="sxs-lookup"><span data-stu-id="7fdf9-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="7fdf9-153">Authentification AV = authentification audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="7fdf9-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="7fdf9-154">Pile SIP = contient la mise en œuvre SIP principale de Lync</span><span class="sxs-lookup"><span data-stu-id="7fdf9-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="7fdf9-155">Proxy de données = utilisé pour la Conférence Edge</span><span class="sxs-lookup"><span data-stu-id="7fdf9-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="7fdf9-156">LySS = service de stockage Lync</span><span class="sxs-lookup"><span data-stu-id="7fdf9-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="7fdf9-157">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="7fdf9-157">Front-end Servers</span></span>

<span data-ttu-id="7fdf9-158">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs frontaux :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fdf9-159">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="7fdf9-159">Functional area</span></span></th>
<th><span data-ttu-id="7fdf9-160">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="7fdf9-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="7fdf9-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-162">État &lt;d’intégrité de la MCU 2</span><span class="sxs-lookup"><span data-stu-id="7fdf9-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fdf9-163">Composants Web</span><span class="sxs-lookup"><span data-stu-id="7fdf9-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-164">Délais d’attente de l’extension &lt;de liste de distribution 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="7fdf9-165">Échecs ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="7fdf9-166">Échecs LIS = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="7fdf9-167">Erreurs &lt; d’authentification 1/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="7fdf9-168">Demandes v4 ASP.NET rejetées = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-169">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="7fdf9-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-170">Traitement &lt; des messages entrants moy.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="7fdf9-171">Réponses entrantes &lt; supprimées 1/s requêtes &lt; entrantes abandonnées 1/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="7fdf9-172">Latence de file &lt; d’attente 100 ms</span><span class="sxs-lookup"><span data-stu-id="7fdf9-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="7fdf9-173">Latence de la &lt; sproc 100 ms</span><span class="sxs-lookup"><span data-stu-id="7fdf9-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="7fdf9-174">Demandes limitées = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="7fdf9-175">Erreurs &lt; d’authentification 1/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="7fdf9-176">Messages entrants expirés &lt; 2</span><span class="sxs-lookup"><span data-stu-id="7fdf9-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="7fdf9-177">Durée moyenne de blocage &lt; des messages entrants 1 seconde</span><span class="sxs-lookup"><span data-stu-id="7fdf9-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="7fdf9-178">Connexions &lt; avec contrôle de flux 2</span><span class="sxs-lookup"><span data-stu-id="7fdf9-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="7fdf9-179">Retard &lt; moy.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fdf9-180">LySS</span><span class="sxs-lookup"><span data-stu-id="7fdf9-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-181">% de l’espace utilisé par le service &lt; de stockage DB 80</span><span class="sxs-lookup"><span data-stu-id="7fdf9-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="7fdf9-182">#d’échecs de réplication de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="7fdf9-183">#des événements de perte de données = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-184">SQL</span><span class="sxs-lookup"><span data-stu-id="7fdf9-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-185">Durée de vie de &gt; la page 300 s.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="7fdf9-186">Demandes par lots/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="7fdf9-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="7fdf9-187">Serveurs SQL principaux</span><span class="sxs-lookup"><span data-stu-id="7fdf9-187">Backend SQL Servers</span></span>

<span data-ttu-id="7fdf9-188">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs SQL :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fdf9-189">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="7fdf9-189">Functional area</span></span></th>
<th><span data-ttu-id="7fdf9-190">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="7fdf9-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-191">SQL</span><span class="sxs-lookup"><span data-stu-id="7fdf9-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-192">Durée de vie de &gt; la page 300 s.</span><span class="sxs-lookup"><span data-stu-id="7fdf9-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="7fdf9-193">Demandes par lots/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="7fdf9-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="7fdf9-194">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="7fdf9-194">Mediation Servers</span></span>

<span data-ttu-id="7fdf9-195">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs de médiation :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fdf9-196">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="7fdf9-196">Functional area</span></span></th>
<th><span data-ttu-id="7fdf9-197">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="7fdf9-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-198">Service de médiation</span><span class="sxs-lookup"><span data-stu-id="7fdf9-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-199">Index d’échec de l’appel de chargement = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="7fdf9-200">Appels ayant échoué en raison &lt;du proxy 10</span><span class="sxs-lookup"><span data-stu-id="7fdf9-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="7fdf9-201">Appels ayant échoué en raison &lt;de la passerelle 10</span><span class="sxs-lookup"><span data-stu-id="7fdf9-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="7fdf9-202">Appels (entrants ou sortants) rejetés = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="7fdf9-203">Candidats multimédias manquants = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="7fdf9-204">Échecs de vérification de la connectivité des médias = 0</span><span class="sxs-lookup"><span data-stu-id="7fdf9-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="7fdf9-205">Serveurs de périphérie</span><span class="sxs-lookup"><span data-stu-id="7fdf9-205">Edge Servers</span></span>

<span data-ttu-id="7fdf9-206">Outre l’intégrité des composants de base, les cibles KHI recommandées sont spécifiques aux serveurs Edge :</span><span class="sxs-lookup"><span data-stu-id="7fdf9-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fdf9-207">Domaine fonctionnel</span><span class="sxs-lookup"><span data-stu-id="7fdf9-207">Functional area</span></span></th>
<th><span data-ttu-id="7fdf9-208">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="7fdf9-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-209">Authentification AV</span><span class="sxs-lookup"><span data-stu-id="7fdf9-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-210">Demandes &lt; incorrectes 20/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fdf9-211">Serveur Edge AV</span><span class="sxs-lookup"><span data-stu-id="7fdf9-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-212">Échecs &lt;d’authentification 20/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="7fdf9-213">Échecs &lt;de répartition 20/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="7fdf9-214">Paquets supprimés &lt;300/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fdf9-215">Proxy de données</span><span class="sxs-lookup"><span data-stu-id="7fdf9-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-216">Connexions &lt; serveur limitées 3</span><span class="sxs-lookup"><span data-stu-id="7fdf9-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="7fdf9-217">Le système est limité &lt;à 1</span><span class="sxs-lookup"><span data-stu-id="7fdf9-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fdf9-218">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="7fdf9-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="7fdf9-219">Connexions au-delà &lt; de la limite ignorée 1</span><span class="sxs-lookup"><span data-stu-id="7fdf9-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="7fdf9-220">Envoi expiré &lt;10</span><span class="sxs-lookup"><span data-stu-id="7fdf9-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="7fdf9-221">Connexions &lt;contrôlées par flux 100</span><span class="sxs-lookup"><span data-stu-id="7fdf9-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="7fdf9-222">Demandes entrantes &lt; abandonnées 1/s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="7fdf9-223">Traitement &lt; de message moy. 3 s</span><span class="sxs-lookup"><span data-stu-id="7fdf9-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fdf9-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7fdf9-224">See Also</span></span>


[<span data-ttu-id="7fdf9-225">Guide de mise en réseau Lync Server</span><span class="sxs-lookup"><span data-stu-id="7fdf9-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="7fdf9-226">Indicateurs d’intégrité clés : base pour la maintenance des serveurs Lync sains</span><span class="sxs-lookup"><span data-stu-id="7fdf9-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="7fdf9-227">Méthodologie de qualité des appels Lync</span><span class="sxs-lookup"><span data-stu-id="7fdf9-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

