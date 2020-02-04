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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="c3e59-102">Principaux indicateurs d’intégrité dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3e59-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3e59-103">_**Dernière modification de la rubrique :** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="c3e59-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="c3e59-104">Cet article est un complément des [indicateurs d’intégrité clés : la base de la mise à jour des afficheurs Lync Servers sains](http://go.microsoft.com/fwlink/?linkid=391838) que vous pouvez télécharger à partir du centre de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="c3e59-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="c3e59-105">![Affiche décrivant le dépannage à l’aide de données KHI](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Affiche décrivant le dépannage à l’aide de données KHI")</span><span class="sxs-lookup"><span data-stu-id="c3e59-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="c3e59-106">Vous pouvez utiliser cette affiche pour en savoir plus sur les indicateurs de performance clés (KHIs), les compteurs de performance avec des seuils visant à révéler des problèmes d’utilisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3e59-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c3e59-107">La collecte des données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui vise à garantir une qualité audio optimale pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c3e59-108">Si vous avez des questions sur l’utilisation de CQM, vous pouvez transmettre vos questions à cqmfeedback@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c3e59-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="c3e59-109">L’affiche décrit les domaines suivants :</span><span class="sxs-lookup"><span data-stu-id="c3e59-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="c3e59-110">Que sont les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="c3e59-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="c3e59-111">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="c3e59-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="c3e59-112">Flux de correction pour tous les rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="c3e59-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="c3e59-113">Glossaire</span><span class="sxs-lookup"><span data-stu-id="c3e59-113">Glossary</span></span>

  - <span data-ttu-id="c3e59-114">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="c3e59-114">Front-end Servers</span></span>

  - <span data-ttu-id="c3e59-115">Serveur SQL principal</span><span class="sxs-lookup"><span data-stu-id="c3e59-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="c3e59-116">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="c3e59-116">Mediation Servers</span></span>

  - <span data-ttu-id="c3e59-117">serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="c3e59-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="c3e59-118">Que sont les indicateurs d’intégrité clés ?</span><span class="sxs-lookup"><span data-stu-id="c3e59-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="c3e59-119">Les indicateurs de performance clés sont des compteurs de performance avec des seuils visant à révéler des problèmes d’utilisation de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c3e59-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c3e59-120">La collecte des données KHI est généralement la première étape de l’implémentation de la méthodologie de qualité des appels (CQM), qui vise à garantir une qualité audio optimale pour les utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c3e59-121">Les KHIs sont utilisés en plus des solutions de surveillance Lync standard (par exemple, System Center Operations Manager, transactions synthétiques, serveur de surveillance) et non au lieu de ces solutions.</span><span class="sxs-lookup"><span data-stu-id="c3e59-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="c3e59-122">Recueillez les compteurs de performance KHI et remplissez la feuille de calcul KHI qui accompagne le Guide réseau pour créer une carte de performance qui vous aidera à déterminer l’état du serveur d’un déploiement Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="c3e59-123">Une fois rempli, il vous guide dans la réparation de l’environnement et fournit des renseignements supplémentaires aux autres parties prenantes.</span><span class="sxs-lookup"><span data-stu-id="c3e59-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="c3e59-124">Évaluez KHIs sur une base mensuelle et intégrez-le dans les processus opérationnels en cours de déploiement.</span><span class="sxs-lookup"><span data-stu-id="c3e59-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="c3e59-125">Téléchargez le [Guide du réseau Lync Server](http://go.microsoft.com/fwlink/p/?linkid=390677) pour afficher la liste complète des KHIs et obtenir les feuilles de calcul associées.</span><span class="sxs-lookup"><span data-stu-id="c3e59-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="c3e59-126">Pour collecter des données KHI</span><span class="sxs-lookup"><span data-stu-id="c3e59-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="c3e59-127">Exécutez le script KHI inclus dans le Guide du réseau Lync Server sur chaque serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="c3e59-128">Cela permet de créer un collecteur de données dans le moniteur de performance et de le nommer KHI.</span><span class="sxs-lookup"><span data-stu-id="c3e59-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="c3e59-129">Par défaut, les données sont interrogées toutes les 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="c3e59-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="c3e59-130">Avant le début de la journée de votre entreprise, accédez à chaque serveur Lync et démarrez le collecteur de données KHI.</span><span class="sxs-lookup"><span data-stu-id="c3e59-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="c3e59-131">À la fin de cette journée, arrêtez le collecteur de données KHI et copiez les données dans un emplacement central.</span><span class="sxs-lookup"><span data-stu-id="c3e59-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="c3e59-132">Après avoir utilisé le moniteur de performance pour remplir la feuille de calcul KHI incluse dans le téléchargement du Guide du réseau Lync Server, comparez les résultats aux cibles recommandées.</span><span class="sxs-lookup"><span data-stu-id="c3e59-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="c3e59-133">Flux de correction pour tous les rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="c3e59-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="c3e59-134">Pour chaque serveur dans votre implémentation Lync, commencez par vérifier que les performances du composant et celles du serveur du serveur sont au niveau le plus souhaité.</span><span class="sxs-lookup"><span data-stu-id="c3e59-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="c3e59-135">Après cela, vous devez examiner les indicateurs relatifs au rôle du serveur dans l’implémentation globale de Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="c3e59-136">Commencez par collecter les données de performances KHI pour tous les serveurs.</span><span class="sxs-lookup"><span data-stu-id="c3e59-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="c3e59-137">Pour chacun des rôles système (détails abordés plus loin dans ce document), déterminez si les composants système de base répondent aux cibles recommandées.</span><span class="sxs-lookup"><span data-stu-id="c3e59-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="c3e59-138">Si ce n’est pas le cas, assurez-vous d’apporter une correction aux performances du système, puis recollectez les données KHI et assurez-vous que l’état du système s’applique aux mesures spécifiques au rôle du serveur dans l’implémentation Lync.</span><span class="sxs-lookup"><span data-stu-id="c3e59-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="c3e59-139">L’intégrité des composants de tous les rôles est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="c3e59-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="c3e59-140">Taux d' \< utilisation UC 80%</span><span class="sxs-lookup"><span data-stu-id="c3e59-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="c3e59-141">Moyenne. écriture \< de 10 ms</span><span class="sxs-lookup"><span data-stu-id="c3e59-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="c3e59-142">Moyenne. Disk lu \< 10 ms</span><span class="sxs-lookup"><span data-stu-id="c3e59-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="c3e59-143">Mémoire \>disponible de 20% au total Mo</span><span class="sxs-lookup"><span data-stu-id="c3e59-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="c3e59-144">Longueur \< de la file d’attente réseau 2</span><span class="sxs-lookup"><span data-stu-id="c3e59-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="c3e59-145">Paquets ignorés (en entrée/sortie) = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="c3e59-146">Glossaire</span><span class="sxs-lookup"><span data-stu-id="c3e59-146">Glossary</span></span>

<span data-ttu-id="c3e59-147">Les termes et sigles suivants sont utilisés dans cet affiche :</span><span class="sxs-lookup"><span data-stu-id="c3e59-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="c3e59-148">AS MCU = unité de contrôle de partage d’application multipoint</span><span class="sxs-lookup"><span data-stu-id="c3e59-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="c3e59-149">AV MCU = audio/vidéo MCU</span><span class="sxs-lookup"><span data-stu-id="c3e59-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="c3e59-150">Messagerie instantanée MCU = MCU</span><span class="sxs-lookup"><span data-stu-id="c3e59-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="c3e59-151">UCWA = API Web de communications unifiées</span><span class="sxs-lookup"><span data-stu-id="c3e59-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="c3e59-152">Clavier AV = traversée de l’audio/vidéo via Edge</span><span class="sxs-lookup"><span data-stu-id="c3e59-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="c3e59-153">Authentification AV = authentification audio/vidéo</span><span class="sxs-lookup"><span data-stu-id="c3e59-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="c3e59-154">Pile SIP = application de base SIP de Lync</span><span class="sxs-lookup"><span data-stu-id="c3e59-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="c3e59-155">Proxy de données = utilisé pour les conférences de périphériques</span><span class="sxs-lookup"><span data-stu-id="c3e59-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="c3e59-156">LySS = service de stockage Lync</span><span class="sxs-lookup"><span data-stu-id="c3e59-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="c3e59-157">Serveurs frontaux</span><span class="sxs-lookup"><span data-stu-id="c3e59-157">Front-end Servers</span></span>

<span data-ttu-id="c3e59-158">Les cibles KHI suivantes sont spécifiques aux serveurs frontaux en plus de l’état d’intégrité des composants de base :</span><span class="sxs-lookup"><span data-stu-id="c3e59-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3e59-159">Zone fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c3e59-159">Functional area</span></span></th>
<th><span data-ttu-id="c3e59-160">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="c3e59-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="c3e59-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c3e59-162">État &lt;d’intégrité du MCU 2</span><span class="sxs-lookup"><span data-stu-id="c3e59-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3e59-163">Composants Web</span><span class="sxs-lookup"><span data-stu-id="c3e59-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="c3e59-164">Temporisation de l’extension de &lt;liste de distribution 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="c3e59-165">Échecs de ABWQ = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="c3e59-166">Échecs de LIS = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="c3e59-167">Erreurs &lt; d’authentification 1/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c3e59-168">Demandes d’ASP.NET V4 rejetées = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-169">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="c3e59-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c3e59-170">Moyenne. traitement &lt; de messages entrants 1 s</span><span class="sxs-lookup"><span data-stu-id="c3e59-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c3e59-171">Les réponses entrantes ont été supprimées &lt; &lt; .</span><span class="sxs-lookup"><span data-stu-id="c3e59-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c3e59-172">Latence de la &lt; file d’attente 100 ms</span><span class="sxs-lookup"><span data-stu-id="c3e59-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c3e59-173">Latence de sproc &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="c3e59-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c3e59-174">Demandes de limitation = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="c3e59-175">Erreurs &lt; d’authentification 1/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c3e59-176">Messages entrants expirés &lt; 2</span><span class="sxs-lookup"><span data-stu-id="c3e59-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="c3e59-177">Moyenne de messages entrants &lt; : 1 seconde</span><span class="sxs-lookup"><span data-stu-id="c3e59-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c3e59-178">Connexions &lt; à contrôle de flux 2</span><span class="sxs-lookup"><span data-stu-id="c3e59-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="c3e59-179">Moyenne. décalage &lt; de la file d’attente 2 s</span><span class="sxs-lookup"><span data-stu-id="c3e59-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3e59-180">LySS</span><span class="sxs-lookup"><span data-stu-id="c3e59-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="c3e59-181">% d’espace utilisé par la base &lt; de services de stockage 80</span><span class="sxs-lookup"><span data-stu-id="c3e59-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="c3e59-182">#échecs de réplication de réplica = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="c3e59-183">#des événements de perte de données = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-184">SQL</span><span class="sxs-lookup"><span data-stu-id="c3e59-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="c3e59-185">Durée de vie de &gt; la page 300 s.</span><span class="sxs-lookup"><span data-stu-id="c3e59-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c3e59-186">Demandes de lot/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="c3e59-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="c3e59-187">Serveur SQL principal</span><span class="sxs-lookup"><span data-stu-id="c3e59-187">Backend SQL Servers</span></span>

<span data-ttu-id="c3e59-188">Les cibles KHI suivantes sont spécifiques aux serveurs SQL Server en plus de l’intégrité des composants de base :</span><span class="sxs-lookup"><span data-stu-id="c3e59-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3e59-189">Zone fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c3e59-189">Functional area</span></span></th>
<th><span data-ttu-id="c3e59-190">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="c3e59-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-191">SQL</span><span class="sxs-lookup"><span data-stu-id="c3e59-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="c3e59-192">Durée de vie de &gt; la page 300 s.</span><span class="sxs-lookup"><span data-stu-id="c3e59-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c3e59-193">Demandes de lot/ &lt; s 2500</span><span class="sxs-lookup"><span data-stu-id="c3e59-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="c3e59-194">serveurs de médiation</span><span class="sxs-lookup"><span data-stu-id="c3e59-194">Mediation Servers</span></span>

<span data-ttu-id="c3e59-195">Les cibles KHI suivantes sont spécifiques aux serveurs de médiation en plus de l’intégrité des composants de base :</span><span class="sxs-lookup"><span data-stu-id="c3e59-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3e59-196">Zone fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c3e59-196">Functional area</span></span></th>
<th><span data-ttu-id="c3e59-197">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="c3e59-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-198">Service de médiation Server</span><span class="sxs-lookup"><span data-stu-id="c3e59-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="c3e59-199">Chargement de l’index d’échec de l’appel = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="c3e59-200">Appels en échec en raison &lt;de proxy 10</span><span class="sxs-lookup"><span data-stu-id="c3e59-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="c3e59-201">Appels en échec en raison &lt;de la passerelle 10</span><span class="sxs-lookup"><span data-stu-id="c3e59-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="c3e59-202">Appels (en sortie ou en sortie) rejetés = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="c3e59-203">Les candidats de médias ont manquant = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="c3e59-204">Échecs de vérification de la connectivité média = 0</span><span class="sxs-lookup"><span data-stu-id="c3e59-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="c3e59-205">serveurs Edge</span><span class="sxs-lookup"><span data-stu-id="c3e59-205">Edge Servers</span></span>

<span data-ttu-id="c3e59-206">Les cibles KHI suivantes sont spécifiques aux serveurs Edge, en plus de l’état d’intégrité des composants de base :</span><span class="sxs-lookup"><span data-stu-id="c3e59-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3e59-207">Zone fonctionnelle</span><span class="sxs-lookup"><span data-stu-id="c3e59-207">Functional area</span></span></th>
<th><span data-ttu-id="c3e59-208">Mesures cibles</span><span class="sxs-lookup"><span data-stu-id="c3e59-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-209">Authentification AV</span><span class="sxs-lookup"><span data-stu-id="c3e59-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="c3e59-210">Demandes &lt; incorrectes 20/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3e59-211">Bordure AV</span><span class="sxs-lookup"><span data-stu-id="c3e59-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="c3e59-212">Échecs &lt;d’authentification 20/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c3e59-213">Échecs &lt;d’attribution 20/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c3e59-214">Paquets déposés &lt;300/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3e59-215">Proxy de données</span><span class="sxs-lookup"><span data-stu-id="c3e59-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="c3e59-216">Connexions &lt; serveur limitées 3</span><span class="sxs-lookup"><span data-stu-id="c3e59-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="c3e59-217">Le système est en &lt;limitation 1</span><span class="sxs-lookup"><span data-stu-id="c3e59-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3e59-218">Pile SIP</span><span class="sxs-lookup"><span data-stu-id="c3e59-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c3e59-219">Connexions en dépassement de &lt; limite</span><span class="sxs-lookup"><span data-stu-id="c3e59-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="c3e59-220">Le délai d' &lt;envoi est écoulé 10</span><span class="sxs-lookup"><span data-stu-id="c3e59-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="c3e59-221">Connexion &lt;contrôlée par flux 100</span><span class="sxs-lookup"><span data-stu-id="c3e59-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="c3e59-222">Demandes entrantes &lt; rejetées 1/s</span><span class="sxs-lookup"><span data-stu-id="c3e59-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c3e59-223">Moyenne du traitement &lt; des messages 3 s</span><span class="sxs-lookup"><span data-stu-id="c3e59-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3e59-224">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3e59-224">See Also</span></span>


[<span data-ttu-id="c3e59-225">Guide du réseau Lync Server</span><span class="sxs-lookup"><span data-stu-id="c3e59-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="c3e59-226">Principaux indicateurs d’intégrité : notions de base pour la mise à jour des serveurs Lync sains</span><span class="sxs-lookup"><span data-stu-id="c3e59-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="c3e59-227">Méthodologie de qualité d’appel Lync</span><span class="sxs-lookup"><span data-stu-id="c3e59-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

