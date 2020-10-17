---
title: 'Lync Server 2013 : tâches hebdomadaires'
description: 'Lync Server 2013 : tâches hebdomadaires.'
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
ms.openlocfilehash: d818e1140141a470bb57a1471bb04931f505a6bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546140"
---
# <a name="weekly-tasks-in-lync-server-2013"></a><span data-ttu-id="1a2bb-103">Tâches hebdomadaires dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a2bb-103">Weekly tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a2bb-104">_**Dernière modification de la rubrique :** 2015-08-17_</span><span class="sxs-lookup"><span data-stu-id="1a2bb-104">_**Topic Last Modified:** 2015-08-17_</span></span>

<span data-ttu-id="1a2bb-105">Les tâches hebdomadaires sont généralement liées à la collecte et à l’analyse des journaux et des rapports.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-105">Weekly tasks are generally related to collecting and analyzing logs and reports.</span></span>

<div>

## <a name="archive-event-logs"></a><span data-ttu-id="1a2bb-106">Archiver les journaux des événements</span><span class="sxs-lookup"><span data-stu-id="1a2bb-106">Archive event logs</span></span>

<span data-ttu-id="1a2bb-107">Si les journaux des événements ne sont pas configurés de manière à remplacer les événements au besoin, ils doivent être régulièrement archivés et supprimés.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-107">If event logs are not configured to overwrite events as required, they must be regularly archived and deleted.</span></span> <span data-ttu-id="1a2bb-108">Cette action est particulièrement importante pour les journaux de sécurité, qui peuvent être requis dans le cadre de recherches concernant des tentatives de violation de la sécurité.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-108">This action is especially important for security logs, which may be required when investigating attempted security breaches.</span></span>

<span data-ttu-id="1a2bb-109">Votre organisation devra définir des stratégies et des procédures pour l’archivage des journaux.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-109">Your organization will have to define policies and procedures for log archiving.</span></span>

</div>

<div>

## <a name="create-reports"></a><span data-ttu-id="1a2bb-110">Créer des rapports</span><span class="sxs-lookup"><span data-stu-id="1a2bb-110">Create reports</span></span>

<span data-ttu-id="1a2bb-111">Créer des rapports d’État pour faciliter la planification de la capacité, les révisions SLA et l’analyse des performances.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-111">Create status reports to help with capacity planning, SLA reviews, and performance analysis.</span></span> <span data-ttu-id="1a2bb-112">Utilisez les données quotidiennes du journal des événements et du moniteur système pour créer des rapports sur le disque, la mémoire et l’utilisation du processeur.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-112">Use daily data from event log and System Monitor to create reports on disk, memory, and CPU usage.</span></span> <span data-ttu-id="1a2bb-113">Utilisez System Center Operations Manager pour générer des rapports de disponibilité et de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-113">Use System Center Operations Manager to generate uptime and availability reports.</span></span>

<span data-ttu-id="1a2bb-114">Votre organisation devra définir des stratégies et des procédures pour les rapports d’État.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-114">Your organization will have to define policies and procedures for status reports.</span></span>

</div>

<div>

## <a name="incident-reports"></a><span data-ttu-id="1a2bb-115">Rapports d’incident</span><span class="sxs-lookup"><span data-stu-id="1a2bb-115">Incident reports</span></span>

<span data-ttu-id="1a2bb-116">Effectuez un audit hebdomadaire des rapports d’incident de votre organisation liés à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-116">Perform a weekly audit of your organization’s incident reports that relate to Lync Server.</span></span> <span data-ttu-id="1a2bb-117">Cet audit doit inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-117">This audit should include the following:</span></span>

  - <span data-ttu-id="1a2bb-118">Les incidents les plus fréquents générés, résolus et en attente.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-118">The top generated, resolved, and pending incidents.</span></span>

  - <span data-ttu-id="1a2bb-119">Solutions pour les incidents non résolus.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-119">Solutions for unresolved incidents.</span></span>

  - <span data-ttu-id="1a2bb-120">Mise à jour des rapports pour inclure de nouveaux tickets de problèmes.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-120">Updating reports to include new trouble tickets.</span></span>

  - <span data-ttu-id="1a2bb-121">Mise à jour d’un référentiel de documents pour des guides de dépannage et des post-mortem à propos des pannes.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-121">Updating a document repository for troubleshooting guides and post mortems about outages.</span></span>

<span data-ttu-id="1a2bb-122">Étant donné que le système de suivi des incidents de votre organisation est un choix indépendant de Lync Server, des instructions ou des pointeurs spécifiques ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-122">Since your organization’s incident tracking system is a choice independent of Lync Server, specific instructions or pointers are not available.</span></span> <span data-ttu-id="1a2bb-123">Consultez la documentation relative au système choisi par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-123">Consult the documentation for the system your organization chose.</span></span>

</div>

<div>

## <a name="check-iis-logs-and-performance"></a><span data-ttu-id="1a2bb-124">Vérifier les journaux et les performances IIS</span><span class="sxs-lookup"><span data-stu-id="1a2bb-124">Check IIS logs and performance</span></span>

<span data-ttu-id="1a2bb-125">Effectuer une révision hebdomadaire des journaux et des performances des services IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="1a2bb-125">Perform a weekly review of Internet Information Services (IIS) logs and performance.</span></span> <span data-ttu-id="1a2bb-126">Pour plus d’informations sur la surveillance des performances et des journaux IIS, voir [Windows Server 2003 Internet Information Services (IIS) Logging Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span><span class="sxs-lookup"><span data-stu-id="1a2bb-126">For more information about how to monitor IIS logs and performance, see [Windows Server 2003 Internet Information Services (IIS) Event Logging Overview](https://go.microsoft.com/fwlink/?linkid=36077).</span></span> <span data-ttu-id="1a2bb-127">La révision doit inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-127">The review should include the following:</span></span>

  - <span data-ttu-id="1a2bb-128">Compteurs de cache de service Web permettant de surveiller le cache du service WWW.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-128">Web Service Cache counters to monitor the WWW service cache.</span></span>

  - <span data-ttu-id="1a2bb-129">Compteurs ASP (Active Server Pages) pour surveiller les applications qui s’exécutent en tant qu’ASP.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-129">Active Server Pages (ASPs) counters to monitor applications that run as ASPs.</span></span>

</div>

<div>

## <a name="generate-database-reports"></a><span data-ttu-id="1a2bb-130">Générer des rapports de base de données</span><span class="sxs-lookup"><span data-stu-id="1a2bb-130">Generate database reports</span></span>

<span data-ttu-id="1a2bb-131">**Pour générer des rapports sur la base de données SQL**</span><span class="sxs-lookup"><span data-stu-id="1a2bb-131">**To generate reports on the SQL Database**</span></span>

1.  <span data-ttu-id="1a2bb-132">Ouvrez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-132">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="1a2bb-133">Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-133">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="1a2bb-134">Dans le volet d’informations, cliquez sur l’onglet **base de données** .</span><span class="sxs-lookup"><span data-stu-id="1a2bb-134">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="1a2bb-135">Sous l’onglet **base de données** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-135">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="1a2bb-136">Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-136">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="1a2bb-137">Pour récupérer les statistiques de résumé de l’utilisateur actuel pour le pool, développez **rapports de résumé**de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-137">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="1a2bb-138">Pour récupérer les données par utilisateur actuelles pour un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-138">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="1a2bb-139">Pour récupérer les statistiques de synthèse de conférence actuelles pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-139">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a><span data-ttu-id="1a2bb-140">Vérifier les mises à jour de sécurité et de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a2bb-140">Check for security and Lync Server updates</span></span>

<span data-ttu-id="1a2bb-141">Identifiez les nouveaux Service Packs, correctifs ou mises à jour.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-141">Identify any new service packs, hotfixes, or updates.</span></span> <span data-ttu-id="1a2bb-142">Si nécessaire, testez-les dans un laboratoire de test et utilisez les procédures de contrôle des modifications pour organiser le déploiement vers les serveurs de production.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-142">If appropriate, test these in a test lab, and use the change control procedures to arrange for deployment to the production servers.</span></span> <span data-ttu-id="1a2bb-143">De plus, les mises à jour de composants Lync Server sont désormais disponibles dans le cadre de Windows Update.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-143">Also, Lync Server component updates are now available as part of Windows update.</span></span> <span data-ttu-id="1a2bb-144">Toutes les mises à jour de composants Lync Server doivent être mises à jour en même temps sur tous les serveurs qui exécutent Lync Server et pour lesquels les mises à jour sont applicables.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-144">All Lync Server component updates must be updated at the same time on all of the servers that are running Lync Server for which the updates are applicable.</span></span>

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a><span data-ttu-id="1a2bb-145">Exécuter l’outil Best Practices Analyzer Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a2bb-145">Run the Lync Server 2013 Best Practice Analyzer</span></span>

<span data-ttu-id="1a2bb-146">L’outil de diagnostic Lync Server 2013 Best Practices Analyzer est un outil de diagnostic qui collecte des informations de configuration et détermine si la configuration est définie conformément aux meilleures pratiques de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-146">The Lync Server 2013 Best Practices Analyzer Tool is a diagnostic tool that collects configuration information and determines whether the configuration is set according to Microsoft best practices.</span></span> <span data-ttu-id="1a2bb-147">La documentation relative à cet outil se trouve sur [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="1a2bb-147">Documentation for this tool is at [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).</span></span>

<span data-ttu-id="1a2bb-148">L’outil compare les données de configuration de votre déploiement par rapport à un ensemble de règles prédéfinies pour Lync Server et signale les problèmes potentiels.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-148">The tool compares your deployment’s configuration data against a set of pre-defined rules for Lync Server, and reports potential issues.</span></span> <span data-ttu-id="1a2bb-149">Pour chaque problème signalé, l’outil fournit la configuration actuelle dans l’environnement Lync Server et la configuration recommandée.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-149">For every issue reported, the tool provides the current configuration in the Lync Server environment, and the recommended configuration.</span></span>

<span data-ttu-id="1a2bb-150">Avec l’accès réseau approprié, l’outil peut examiner vos services de domaine Active Directory et vos serveurs exécutant Lync Server 2013 pour effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-150">With the correct network access, the tool can examine your AD DS and servers that are running Lync Server 2013 to do the following:</span></span>

  - <span data-ttu-id="1a2bb-151">Effectuer des vérifications d’intégrité de manière proactive, en vérifiant que la configuration est définie conformément aux meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="1a2bb-151">Proactively perform health checks, verifying that the configuration is set according to recommended best practices</span></span>

  - <span data-ttu-id="1a2bb-152">Générer une liste de problèmes, tels que des paramètres de configuration sous-optimaux ou des options non prises en charge ou non prises en charge</span><span class="sxs-lookup"><span data-stu-id="1a2bb-152">Generate a list of issues, such as suboptimal configuration settings or unsupported or not recommended options</span></span>

  - <span data-ttu-id="1a2bb-153">Évaluer l’état général d’un système</span><span class="sxs-lookup"><span data-stu-id="1a2bb-153">Judge the general health of a system</span></span>

  - <span data-ttu-id="1a2bb-154">Aider à résoudre des problèmes spécifiques</span><span class="sxs-lookup"><span data-stu-id="1a2bb-154">Help troubleshoot specific issues</span></span>

  - <span data-ttu-id="1a2bb-155">Vous demander de télécharger les mises à jour si elles sont disponibles</span><span class="sxs-lookup"><span data-stu-id="1a2bb-155">Prompt you to download updates if they are available</span></span>

  - <span data-ttu-id="1a2bb-156">Fournir une documentation en ligne et locale sur les problèmes signalés et inclure des conseils de dépannage</span><span class="sxs-lookup"><span data-stu-id="1a2bb-156">Provide online and local documentation about reported issues, and include troubleshooting tips</span></span>

  - <span data-ttu-id="1a2bb-157">Générer des informations de configuration pouvant être capturées à des fins de révision ultérieure</span><span class="sxs-lookup"><span data-stu-id="1a2bb-157">Generate configuration information that can be captured for later review</span></span>

<span data-ttu-id="1a2bb-158">Assurez-vous que le RTCBPA.msi est installé sur tous les serveurs Lync Server 2013 et générez un rapport de vérification de l’intégrité hebdomadaire.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-158">Ensure that the RTCBPA.msi is installed on all Lync Server 2013 servers, and generate a weekly Health Check Report.</span></span> <span data-ttu-id="1a2bb-159">Notez les résultats et corrigez, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-159">Note the results and correct, if necessary.</span></span>

</div>

<div>

## <a name="review-sla-performance-figures"></a><span data-ttu-id="1a2bb-160">Passer en revue les chiffres de performances SLA</span><span class="sxs-lookup"><span data-stu-id="1a2bb-160">Review SLA performance figures</span></span>

<span data-ttu-id="1a2bb-161">Vérifiez les données de performances clés pour la semaine précédente.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-161">Check the key performance data for the previous week.</span></span> <span data-ttu-id="1a2bb-162">Passez en revue les performances par rapport aux exigences du contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-162">Review performance against the requirements of the SLA.</span></span> <span data-ttu-id="1a2bb-163">Identifiez les tendances et les éléments pour lesquels les objectifs n'ont pas été satisfaits.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-163">Identify trends and items that have not met their targets.</span></span>

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a><span data-ttu-id="1a2bb-164">Examen du pack d’administration et des rapports de qualité de l’expérience System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="1a2bb-164">Review System Center Operations Manager Management Pack and quality of experience reports</span></span>

<span data-ttu-id="1a2bb-165">Procurez-vous et passez en revue le pack d’administration Lync Server 2013 et les rapports de qualité de l’expérience.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-165">Obtain and review Lync Server 2013 Management Pack and Quality of Experience reports.</span></span>

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a><span data-ttu-id="1a2bb-166">Génération et affichage de rapports de base de données pour les pools d’entreprise</span><span class="sxs-lookup"><span data-stu-id="1a2bb-166">Generating and viewing database reports for enterprise pools</span></span>

<span data-ttu-id="1a2bb-167">**Pour générer des rapports de pool**</span><span class="sxs-lookup"><span data-stu-id="1a2bb-167">**To generate pool reports**</span></span>

1.  <span data-ttu-id="1a2bb-168">Ouvrez Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-168">Open Lync Server 2013.</span></span>

2.  <span data-ttu-id="1a2bb-169">Dans l’arborescence de la console, développez le nœud de la forêt, développez **pools d’entreprise**, puis cliquez sur le pool pour lequel vous souhaitez générer un rapport de base de données.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-169">In the console tree, expand the forest node, expand **Enterprise pools**, and then click the pool for which you want to generate a database report.</span></span>

3.  <span data-ttu-id="1a2bb-170">Dans le volet d’informations, cliquez sur l’onglet **base de données** .</span><span class="sxs-lookup"><span data-stu-id="1a2bb-170">In the details pane, click the **Database** tab.</span></span>

4.  <span data-ttu-id="1a2bb-171">Sous l’onglet **base de données** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-171">On the **Database** tab, do the following:</span></span>
    
    1.  <span data-ttu-id="1a2bb-172">Pour afficher le nom de la base de données, développez **paramètres généraux**, puis affichez le nom de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-172">To view the name of the database, expand **General Settings**, and view the database name.</span></span>
    
    2.  <span data-ttu-id="1a2bb-173">Pour récupérer les statistiques de résumé de l’utilisateur actuel pour le pool, développez **rapports de résumé**de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-173">To retrieve current user summary statistics for the pool, expand **User Summary Reports**, click **Go**, and view the results.</span></span>
    
    3.  <span data-ttu-id="1a2bb-174">Pour récupérer les données par utilisateur actuelles pour un seul utilisateur du pool, développez **rapports par utilisateur**, tapez l’URI SIP de l’utilisateur, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-174">To retrieve current per-user data for a single user of the pool, expand **Per-User Reports**, type the user’s SIP URI, click **Go**, and view the results.</span></span>

<span data-ttu-id="1a2bb-175">Pour récupérer les statistiques de synthèse de conférence actuelles pour le pool, développez **rapports de synthèse de conférence**, cliquez sur **atteindre**et affichez les résultats.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-175">To retrieve current conference summary statistics for the pool, expand **Conference Summary Reports**, click **Go**, and view the results.</span></span>

<span data-ttu-id="1a2bb-176">Pour chaque pool d’entreprise, les administrateurs peuvent utiliser l’onglet **base de données** pour afficher le nom de la base de données et en extraire et afficher les rapports à partir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-176">For each Enterprise Pool, administrators can use the **Database** tab to view the database name and retrieve and view reports from the database.</span></span>

### <a name="database-reports-and-descriptions"></a><span data-ttu-id="1a2bb-177">Rapports et descriptions de la base de données</span><span class="sxs-lookup"><span data-stu-id="1a2bb-177">Database Reports and Descriptions</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1a2bb-178">Section</span><span class="sxs-lookup"><span data-stu-id="1a2bb-178">Section</span></span></th>
<th><span data-ttu-id="1a2bb-179">Description</span><span class="sxs-lookup"><span data-stu-id="1a2bb-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1a2bb-180">Rapports de résumé des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="1a2bb-180">User Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="1a2bb-181">DbAnalyze/v/Report : diag [/SqlServer : valeur]</span><span class="sxs-lookup"><span data-stu-id="1a2bb-181">Dbanalyze /v /report:diag [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="1a2bb-182">Cette section affiche des informations agrégées sur les utilisateurs d’un pool, telles que le nombre d’utilisateurs activés, le nombre moyen de contacts par utilisateur et le nombre d’utilisateurs pour des fonctionnalités spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-182">This section displays aggregate information about users in a pool, such as the number of enabled users, the average number of contacts per user, and the number of users for specific features.</span></span></p>
<p><span data-ttu-id="1a2bb-183">Lors de l’utilisation de ces rapports, les informations suivantes peuvent être utiles :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-183">When using these reports, the following information may be helpful:</span></span></p>
<ul>
<li><p><span data-ttu-id="1a2bb-184">Un utilisateur activé est un utilisateur qui est activé pour Lync Server 2013 à l’aide du composant logiciel enfichable utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-184">An enabled user is a user who is enabled for Lync Server 2013 by using the Active Directory Users and Computers Snap-in.</span></span></p></li>
<li><p><span data-ttu-id="1a2bb-185">Un utilisateur actif est un utilisateur qui a ouvert une session ou a enregistré.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-185">An active user is a user who has logged on or registered.</span></span></p></li>
<li><p><span data-ttu-id="1a2bb-186">Les rapports de synthèse fournissent également un ensemble d’informations statistiques sur les contacts.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-186">The summary reports also offer a set of statistical information about contacts.</span></span> <span data-ttu-id="1a2bb-187">Ces statistiques ne sont valides que pour la population des utilisateurs qui ont ouvert une session au moins une fois et qui disposent au moins d’un contact.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-187">These statistics are only valid for the population of users who have logged on at least one time, and who have at least one contact.</span></span> <span data-ttu-id="1a2bb-188">Par conséquent, vous ne verrez généralement pas de nombre minimal de contacts de 0.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-188">Consequently, you'll typically not see a minimum number of contacts of 0.</span></span> <span data-ttu-id="1a2bb-189">En raison de ce comportement, si un utilisateur ne dispose d’aucun contact (mais est actif, et que l’utilisateur s’est inscrit), vous pouvez voir : &lt; vide &gt; pour certains champs de statistiques.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-189">Because of this behavior, if a user has no contacts (but is active, in that the user has registered), you may see: &lt;empty&gt; for some statistics fields.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1a2bb-190">Rapports Per-User</span><span class="sxs-lookup"><span data-stu-id="1a2bb-190">Per-User Reports</span></span></p></td>
<td><p><span data-ttu-id="1a2bb-191">DbAnalyze/v/Report : disque [/SqlServer : valeur]</span><span class="sxs-lookup"><span data-stu-id="1a2bb-191">Dbanalyze /v /report:disk [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="1a2bb-192">Contrairement aux rapports de synthèse, qui sont calculés sur une population d’utilisateurs, il s’agit de rapports sur un utilisateur spécifique.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-192">Unlike the summary reports, which are calculated over a user population, these are reports about a specific user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1a2bb-193">Rapports de synthèse de conférence</span><span class="sxs-lookup"><span data-stu-id="1a2bb-193">Conference Summary Reports</span></span></p></td>
<td><p><span data-ttu-id="1a2bb-194">DbAnalyze/v/Report : conf [/SqlServer : valeur]</span><span class="sxs-lookup"><span data-stu-id="1a2bb-194">Dbanalyze /v /report:conf [/sqlserver:value]</span></span></p>
<p><span data-ttu-id="1a2bb-195">Cette section affiche des informations agrégées sur les statistiques de résumé de conférence pour le pool, telles que le nombre de conférences actives et le nombre total de participants.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-195">This section displays aggregate information about conference summary statistics for the pool, such as the number of active conferences and total number of participants.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a><span data-ttu-id="1a2bb-196">Exécution de l’analyseur d’utilisation de la bande passante</span><span class="sxs-lookup"><span data-stu-id="1a2bb-196">Running Bandwidth Utilization Analyzer</span></span>

<span data-ttu-id="1a2bb-197">L’analyseur d’utilisation de la bande passante est un outil qui crée des rapports sur les différentes vues de la consommation de bande passante par les points de terminaison UC sur les liaisons de réseau étendu dans le réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-197">Bandwidth Utilization Analyzer is a tool that creates reports about various views of bandwidth consumption by the UC endpoints across WAN links in the enterprise network.</span></span> <span data-ttu-id="1a2bb-198">Ces rapports peuvent être utilisés pour comprendre le modèle de consommation de bande passante actuel et contribuer à la planification de la capacité de bande passante.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-198">These reports can be used to understand the current bandwidth consumption pattern and to help with bandwidth capacity planning.</span></span> <span data-ttu-id="1a2bb-199">Elle effectue également une itération sur la capacité de bande passante affectée à différents liens.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-199">It also iterates on the bandwidth capacity that is assigned to various links.</span></span>

<span data-ttu-id="1a2bb-200">Cet outil effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-200">This tool does the following:</span></span>

  - <span data-ttu-id="1a2bb-201">Génère des rapports spécifiques pour l’utilisation audio sur le réseau</span><span class="sxs-lookup"><span data-stu-id="1a2bb-201">Generates specific reports for audio usage over the network</span></span>

  - <span data-ttu-id="1a2bb-202">Permet une planification et une itération de capacité plus efficaces sur la capacité de bande passante affectée à différents liens</span><span class="sxs-lookup"><span data-stu-id="1a2bb-202">Helps with more effective capacity planning and iteration on the bandwidth capacity that is assigned to various links</span></span>

<span data-ttu-id="1a2bb-203">Bandwidth utilization Analyzer peut générer des tracés graphiques de la capacité de bande passante et des rapports d’utilisation.</span><span class="sxs-lookup"><span data-stu-id="1a2bb-203">Bandwidth Utilization Analyzer can generate graphical plots of bandwidth capacity and usage reports.</span></span> <span data-ttu-id="1a2bb-204">Ils sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="1a2bb-204">They are as follows:</span></span>

  - <span data-ttu-id="1a2bb-205">Toutes les liaisons de réseau étendu dans le réseau d’entreprise</span><span class="sxs-lookup"><span data-stu-id="1a2bb-205">All the WAN links in the enterprise network</span></span>

  - <span data-ttu-id="1a2bb-206">Filtré par les liaisons de réseau étendu sélectionnées</span><span class="sxs-lookup"><span data-stu-id="1a2bb-206">Filtered by selected WAN links that were chosen</span></span>

  - <span data-ttu-id="1a2bb-207">Filtrés par des liaisons de réseau étendu ayant dépassé la capacité de liaison</span><span class="sxs-lookup"><span data-stu-id="1a2bb-207">Filtered by WAN links that have exceeded link capacity</span></span>

  - <span data-ttu-id="1a2bb-208">Filtré par les liaisons de réseau étendu qui étaient sous-utilisant la bande passante approvisionnée</span><span class="sxs-lookup"><span data-stu-id="1a2bb-208">Filtered by WAN links that were under-using the provisioned bandwidth</span></span>

  - <span data-ttu-id="1a2bb-209">Filtrer par les liaisons de réseau étendu qui atteignent des niveaux critiques (une utilisation de bande passante supérieure à 90% de la capacité de bande passante de la liaison de réseau étendu)</span><span class="sxs-lookup"><span data-stu-id="1a2bb-209">Filter by WAN links that were reaching critical levels (a bandwidth usage that is greater than 90 percent of bandwidth capacity of the WAN link)</span></span>

  - <span data-ttu-id="1a2bb-210">Filtré par type de lien WAN — liaisons de sites réseau, liens interrégionaux et liens à l’intérieur d’un site</span><span class="sxs-lookup"><span data-stu-id="1a2bb-210">Filtered by WAN link type—network-site links, interregional links, and links inside a site</span></span>

  - <span data-ttu-id="1a2bb-211">Filtré par région réseau</span><span class="sxs-lookup"><span data-stu-id="1a2bb-211">Filtered by network region</span></span>

<span data-ttu-id="1a2bb-212">La documentation relative à cet outil est disponible dans [la documentation sur les outils du kit de ressources Lync Server 2013](https://go.microsoft.com/fwlink/?linkid=623245).</span><span class="sxs-lookup"><span data-stu-id="1a2bb-212">Documentation for this tool is available at [Lync Server 2013 Resource Kit Tools Documentation](https://go.microsoft.com/fwlink/?linkid=623245).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a2bb-213">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a2bb-213">See Also</span></span>


[<span data-ttu-id="1a2bb-214">Liste de vérification des tâches hebdomadaires</span><span class="sxs-lookup"><span data-stu-id="1a2bb-214">Weekly task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

