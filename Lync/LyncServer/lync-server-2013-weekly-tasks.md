---
title: 'Skype Entreprise Server 2015 : tâches hebdomadaires'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973d5d69e6e4609a1dff3029b0ad0b05ec3a936
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="3e95c-102">Tâches hebdomadaires dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="3e95c-102">Weekly tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e95c-103">_**Dernière modification de la rubrique :** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="3e95c-103">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="3e95c-104">Les tâches hebdomadaires sont généralement liées à la collecte et à l’analyse des journaux et des rapports.</span><span class="sxs-lookup"><span data-stu-id="3e95c-104">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="3e95c-105">Archiver les journaux des événements</span><span class="sxs-lookup"><span data-stu-id="3e95c-105">Archive event logs</span></span>

<span data-ttu-id="3e95c-106">Si les journaux d’événements ne sont pas configurés pour remplacer les événements selon les besoins, ils doivent être régulièrement archivés et supprimés.</span><span class="sxs-lookup"><span data-stu-id="3e95c-106">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="3e95c-107">Cette action est particulièrement importante pour les journaux de sécurité, qui sont peut-être requis lors de l’examen des violations de la sécurité.</span><span class="sxs-lookup"><span data-stu-id="3e95c-107">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="3e95c-108">Votre organisation doit définir des stratégies et des procédures pour l’archivage des journaux.</span><span class="sxs-lookup"><span data-stu-id="3e95c-108">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="3e95c-109">Créer des rapports</span><span class="sxs-lookup"><span data-stu-id="3e95c-109">Create reports</span></span>

<span data-ttu-id="3e95c-110">Créez des rapports d’État pour faciliter la planification de la capacité, les avis sur les SLA et l’analyse des performances.</span><span class="sxs-lookup"><span data-stu-id="3e95c-110">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="3e95c-111">Utilisez les données quotidiennes du journal des événements et du moniteur système pour créer des rapports sur le disque, la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="3e95c-111">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="3e95c-112">Utilisez System Center Operations Manager pour générer des rapports de disponibilité et de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="3e95c-112">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="3e95c-113">Votre organisation doit définir des stratégies et des procédures pour les rapports d’État.</span><span class="sxs-lookup"><span data-stu-id="3e95c-113">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="3e95c-114">Rapports d’incident</span><span class="sxs-lookup"><span data-stu-id="3e95c-114">Incident reports</span></span>

<span data-ttu-id="3e95c-115">Effectuez un audit hebdomadaire des rapports d’incident de votre organisation liés à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e95c-115">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="3e95c-116">Ce contrôle doit inclure ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="3e95c-116">This audit should include the following:</span></span>

  - <span data-ttu-id="3e95c-117">Les incidents les plus fréquents générés, résolus et en attente.</span><span class="sxs-lookup"><span data-stu-id="3e95c-117">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="3e95c-118">Solutions pour les incidents résolus.</span><span class="sxs-lookup"><span data-stu-id="3e95c-118">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="3e95c-119">Mise à jour des rapports pour inclure de nouveaux tickets d’incident.</span><span class="sxs-lookup"><span data-stu-id="3e95c-119">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="3e95c-120">Mise à jour d’un référentiel de documents pour les guides de dépannage et les publications à propos des pannes.</span><span class="sxs-lookup"><span data-stu-id="3e95c-120">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="3e95c-121">Dans la mesure où le système de suivi des incidents de votre organisation est un choix indépendant de Lync Server, les instructions ou les pointeurs spécifiques ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3e95c-121">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="3e95c-122">Consultez la documentation relative au système choisi par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3e95c-122">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="3e95c-123">Vérifier les journaux et performances d’IIS</span><span class="sxs-lookup"><span data-stu-id="3e95c-123">Check IIS logs and performance</span></span>

<span data-ttu-id="3e95c-124">Effectuez une analyse hebdomadaire des journaux et des performances de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3e95c-124">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="3e95c-125">Pour plus d’informations sur la façon de surveiller les journaux et performances d’IIS, voir [vue d’ensemble de la journalisation des événements Windows Server 2003 Internet Information Services (IIS)](http://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="3e95c-125">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](http://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="3e95c-126">L’avis doit inclure ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="3e95c-126">The review should include the following:</span></span>

  - <span data-ttu-id="3e95c-127">Les compteurs du cache de service Web pour surveiller le cache de service WWW.</span><span class="sxs-lookup"><span data-stu-id="3e95c-127">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="3e95c-128">Compteurs ASP (Active Server Pages) pour contrôler les applications qui s’exécutent en tant qu’ASP.</span><span class="sxs-lookup"><span data-stu-id="3e95c-128">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="3e95c-129">Générer des rapports de base de données</span><span class="sxs-lookup"><span data-stu-id="3e95c-129">Generate database reports</span></span>

<span data-ttu-id="3e95c-130">**Pour générer des rapports sur la base de données SQL**</span><span class="sxs-lookup"><span data-stu-id="3e95c-130">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="3e95c-131">Ouvrez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e95c-131">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3e95c-132">Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous voulez générer un rapport de base de données.</span><span class="sxs-lookup"><span data-stu-id="3e95c-132">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3e95c-133">Dans le volet Détails, cliquez sur l’onglet **base de données** .</span><span class="sxs-lookup"><span data-stu-id="3e95c-133">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3e95c-134">Sous l’onglet **base de données** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e95c-134">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3e95c-135">Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e95c-135">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3e95c-136">Pour récupérer les statistiques de synthèse des utilisateurs actuels pour le pool, développez **rapports récapitulatifs des utilisateurs**, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-136">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3e95c-137">Pour récupérer les données par utilisateur actuelles d’un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-137">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3e95c-138">Pour récupérer les statistiques actuelles de synthèse de conférence pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-138">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="3e95c-139">Vérifier la sécurité et les mises à jour de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e95c-139">Check for security and Lync Server updates</span></span>

<span data-ttu-id="3e95c-140">Identifiez de nouveaux service packs, Hotfix ou mises à jour.</span><span class="sxs-lookup"><span data-stu-id="3e95c-140">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="3e95c-141">Le cas échéant, testez ces éléments dans un laboratoire de test et utilisez les procédures de contrôle des modifications pour organiser le déploiement sur les serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="3e95c-141">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="3e95c-142">De plus, les mises à jour de composant Lync Server sont désormais disponibles dans le cadre de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="3e95c-142">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="3e95c-143">Toutes les mises à jour de composant Lync Server doivent être mises à jour en même temps sur tous les serveurs exécutant Lync Server pour lesquels les mises à jour sont applicables.</span><span class="sxs-lookup"><span data-stu-id="3e95c-143">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="3e95c-144">Exécuter l’analyseur de meilleures pratiques Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e95c-144">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="3e95c-145">L’outil Analyseur de meilleures pratiques de Lync Server 2013 est un outil de diagnostic qui collecte des informations de configuration et détermine si la configuration est définie conformément aux meilleures pratiques Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3e95c-145">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="3e95c-146">La documentation relative à cet outil se trouve dans l' [Analyseur de meilleures pratiques de Lync Server 2013](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="3e95c-146">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="3e95c-147">L’outil compare les données de configuration de votre déploiement à un ensemble de règles prédéfinies pour Lync Server et signale les problèmes potentiels.</span><span class="sxs-lookup"><span data-stu-id="3e95c-147">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="3e95c-148">Pour chaque problème signalé, l’outil fournit la configuration actuelle dans l’environnement Lync Server et la configuration recommandée.</span><span class="sxs-lookup"><span data-stu-id="3e95c-148">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="3e95c-149">Avec l’accès au réseau approprié, l’outil peut examiner votre annuaire publicitaire et les serveurs qui exécutent Lync Server 2013 pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e95c-149">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="3e95c-150">Procéder de manière proactive pour vérifier que la configuration est définie conformément aux meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="3e95c-150">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="3e95c-151">Générer une liste des problèmes, tels que les paramètres de configuration de qualité optimale ou les options non prises en charge</span><span class="sxs-lookup"><span data-stu-id="3e95c-151">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="3e95c-152">Évaluer la santé générale d’un système</span><span class="sxs-lookup"><span data-stu-id="3e95c-152">Judge the general health of a system</span></span>

  - <span data-ttu-id="3e95c-153">Aide pour résoudre des problèmes spécifiques</span><span class="sxs-lookup"><span data-stu-id="3e95c-153">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="3e95c-154">Vous invite à télécharger les mises à jour, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="3e95c-154">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="3e95c-155">Fournir une documentation en ligne et locale sur les problèmes signalés et inclure des conseils de dépannage</span><span class="sxs-lookup"><span data-stu-id="3e95c-155">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="3e95c-156">Générer des informations de configuration qui peuvent être capturées lors de la révision ultérieure</span><span class="sxs-lookup"><span data-stu-id="3e95c-156">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="3e95c-157">Vérifiez que le fichier RTCBPA. msi est installé sur tous les serveurs Lync Server 2013 et génère un rapport de vérification d’état hebdomadaire.</span><span class="sxs-lookup"><span data-stu-id="3e95c-157">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="3e95c-158">Notez les résultats et l’exactitude, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="3e95c-158">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="3e95c-159">Examiner les chiffres de performance du SLA</span><span class="sxs-lookup"><span data-stu-id="3e95c-159">Review SLA performance figures</span></span>

<span data-ttu-id="3e95c-160">Vérifier les données de performance clés de la semaine précédente</span><span class="sxs-lookup"><span data-stu-id="3e95c-160">Check the key performance data for the previous week.</span></span> <span data-ttu-id="3e95c-161">Révisez les performances par rapport aux exigences du contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="3e95c-161">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="3e95c-162">Identifiez les tendances et éléments qui n’ont pas satisfait à leurs cibles.</span><span class="sxs-lookup"><span data-stu-id="3e95c-162">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="3e95c-163">Passez en revue le pack d’administration Operations Manager System Center Operations Manager et les rapports de qualité d’utilisation</span><span class="sxs-lookup"><span data-stu-id="3e95c-163">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="3e95c-164">Obtenez et passez en revue les rapports du Pack de gestion et de la qualité de l’interface Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e95c-164">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="3e95c-165">Génération et affichage des rapports de base de données pour les pools d’entreprise</span><span class="sxs-lookup"><span data-stu-id="3e95c-165">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="3e95c-166">**Pour générer des rapports de pool**</span><span class="sxs-lookup"><span data-stu-id="3e95c-166">**To generate pool reports**</span></span>

1.  <span data-ttu-id="3e95c-167">Ouvrez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e95c-167">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="3e95c-168">Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous voulez générer un rapport de base de données.</span><span class="sxs-lookup"><span data-stu-id="3e95c-168">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="3e95c-169">Dans le volet Détails, cliquez sur l’onglet **base de données** .</span><span class="sxs-lookup"><span data-stu-id="3e95c-169">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="3e95c-170">Sous l’onglet **base de données** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3e95c-170">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="3e95c-171">Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e95c-171">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="3e95c-172">Pour récupérer les statistiques de synthèse des utilisateurs actuels pour le pool, développez **rapports récapitulatifs des utilisateurs**, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-172">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="3e95c-173">Pour récupérer les données par utilisateur actuelles d’un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-173">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="3e95c-174">Pour récupérer les statistiques actuelles de synthèse de conférence pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**, puis affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="3e95c-174">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="3e95c-175">Pour chaque pool d’entreprise, les administrateurs peuvent utiliser l’onglet **base de données** pour afficher le nom de la base de données et récupérer et afficher les rapports de la base de données.</span><span class="sxs-lookup"><span data-stu-id="3e95c-175">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="3e95c-176">Rapports et descriptions de base de données</span><span class="sxs-lookup"><span data-stu-id="3e95c-176">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e95c-177">Section</span><span class="sxs-lookup"><span data-stu-id="3e95c-177">Section</span></span></th>
<th><span data-ttu-id="3e95c-178">Description</span><span class="sxs-lookup"><span data-stu-id="3e95c-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e95c-179">Rapports récapitulatifs des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="3e95c-179">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3e95c-180">DbAnalyze/v/Report : diag [/SqlServer : value]</span><span class="sxs-lookup"><span data-stu-id="3e95c-180">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3e95c-181">Cette section contient des informations agrégées sur les utilisateurs d’un pool, comme le nombre d’utilisateurs activés, le nombre moyen de contacts par utilisateur et le nombre d’utilisateurs pour des fonctionnalités spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3e95c-181">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="3e95c-182">Lors de l’utilisation de ces rapports, les informations suivantes pourront vous être utiles :</span><span class="sxs-lookup"><span data-stu-id="3e95c-182">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e95c-183">Un utilisateur activé est un utilisateur qui est activé pour Lync Server 2013 à l’aide du composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3e95c-183">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="3e95c-184">Un utilisateur actif est un utilisateur qui est connecté ou inscrit.</span><span class="sxs-lookup"><span data-stu-id="3e95c-184">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="3e95c-185">Les rapports de synthèse fournissent également un ensemble d’informations statistiques sur les contacts.</span><span class="sxs-lookup"><span data-stu-id="3e95c-185">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="3e95c-186">Ces statistiques sont valides uniquement pour la population d’utilisateurs qui se sont connectés au moins une fois et qui ont au moins un contact.</span><span class="sxs-lookup"><span data-stu-id="3e95c-186">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="3e95c-187">Par conséquent, vous ne verrez généralement pas un nombre minimum de contacts de 0.</span><span class="sxs-lookup"><span data-stu-id="3e95c-187">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="3e95c-188">En raison de ce comportement, si un utilisateur n’a pas de contacts (mais est actif, en ce qu’il est inscrit), il &lt;est&gt; possible que vous voyiez : vide pour certains champs de statistiques.</span><span class="sxs-lookup"><span data-stu-id="3e95c-188">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e95c-189">Rapports par utilisateur</span><span class="sxs-lookup"><span data-stu-id="3e95c-189">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="3e95c-190">DbAnalyze/v/Report : Disk [/SqlServer : value]</span><span class="sxs-lookup"><span data-stu-id="3e95c-190">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3e95c-191">Contrairement aux rapports de synthèse qui sont calculés sur une population d’utilisateurs, il s’agit de rapports relatifs à un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="3e95c-191">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e95c-192">Rapports récapitulatifs de la Conférence</span><span class="sxs-lookup"><span data-stu-id="3e95c-192">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="3e95c-193">DbAnalyze/v/Report : conf [/SqlServer : value]</span><span class="sxs-lookup"><span data-stu-id="3e95c-193">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="3e95c-194">Cette section contient des informations agrégées sur les statistiques de synthèse de conférences du pool, comme le nombre de conférences actives et le nombre total de participants.</span><span class="sxs-lookup"><span data-stu-id="3e95c-194">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="3e95c-195">Exécution de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="3e95c-195">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="3e95c-196">L’outil Bandwidth Utilization Analyzer crée des rapports sur divers affichages de la consommation de bande passante par les points de terminaison d’UC entre les liaisons de réseau étendu dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3e95c-196">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="3e95c-197">Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et faciliter la planification de la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="3e95c-197">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="3e95c-198">Il traite également la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="3e95c-198">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="3e95c-199">L’outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3e95c-199">This tool does the following:</span></span>

  - <span data-ttu-id="3e95c-200">Génère des rapports spécifiques pour l’utilisation de l’audio sur le réseau</span><span class="sxs-lookup"><span data-stu-id="3e95c-200">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="3e95c-201">permet de planifier la capacité plus efficacement et de traiter la capacité de bande passante affectée aux diverses liaisons par itération.</span><span class="sxs-lookup"><span data-stu-id="3e95c-201">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="3e95c-202">L’analyseur d’utilisation de la bande passante peut générer des trace graphiques de capacités de bande passante et de rapports d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="3e95c-202">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="3e95c-203">Ils sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="3e95c-203">They are as follows:</span></span>

  - <span data-ttu-id="3e95c-204">liaisons de réseau étendu au sein du réseau d’entreprise ;</span><span class="sxs-lookup"><span data-stu-id="3e95c-204">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="3e95c-205">Filtré sur la base des liens réseau étendu sélectionnés</span><span class="sxs-lookup"><span data-stu-id="3e95c-205">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="3e95c-206">filtrage des liaisons de réseau étendu ayant dépassé leur capacité ;</span><span class="sxs-lookup"><span data-stu-id="3e95c-206">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="3e95c-207">Filtrés par liaisons WAN qui étaient sous-utilisant la bande passante approvisionnée</span><span class="sxs-lookup"><span data-stu-id="3e95c-207">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="3e95c-208">Filtrer sur des liens WAN ayant atteint des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison WAN);</span><span class="sxs-lookup"><span data-stu-id="3e95c-208">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="3e95c-209">Filtré par type de liaison WAN : liens de site réseau, liens interrégionés et liens à l’intérieur d’un site</span><span class="sxs-lookup"><span data-stu-id="3e95c-209">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="3e95c-210">filtrage par région réseau.</span><span class="sxs-lookup"><span data-stu-id="3e95c-210">Filtered by network region</span></span>

<span data-ttu-id="3e95c-211">La documentation relative à cet outil est disponible dans [la documentation des outils du kit de ressources de Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="3e95c-211">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e95c-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3e95c-212">See Also</span></span>


[<span data-ttu-id="3e95c-213">Liste hebdomadaire des tâches</span><span class="sxs-lookup"><span data-stu-id="3e95c-213">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

