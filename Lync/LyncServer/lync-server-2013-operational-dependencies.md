---
title: 'Lync Server 2013: dépendances opérationnelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ef9959f48c085ad4f5f28f182b86442ebec8c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="a26be-102">Dépendances opérationnelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26be-102">Operational dependencies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a26be-103">_**Dernière modification de la rubrique:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="a26be-103">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="a26be-104">L’architecture de référence décrite dans ce document permet de vérifier que vous disposez d’un déploiement 2013 Server Lync qui n’est pas uniquement destiné aux besoins de l’organisation, mais qu’il est structuré conformément aux meilleures pratiques Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a26be-104">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="a26be-105">Soyez qu’il est possible que l’implémentation de Lync Server 2013 soit un service dynamique et que tous les autres services de l’entreprise requièrent une analyse et une gestion proactive pour maintenir un niveau élevé de disponibilité et de qualité de service pour l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a26be-105">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="a26be-106">Dans la mesure où Lync Server 2013 devient profondément en grain dans l’entreprise, il est important que le service soit géré par une gestion précise et tangible du niveau de service.</span><span class="sxs-lookup"><span data-stu-id="a26be-106">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="a26be-107">L’architecture système de Lync peut devenir complexe et très intégrée et permettre de maintenir une gestion de niveau de service effective et de définir les SLA pour Lync Server 2013 il est essentiel de comprendre les dépendances du système sur d’autres plateformes et serveurs.</span><span class="sxs-lookup"><span data-stu-id="a26be-107">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="a26be-108">Il est également important de noter quels services d’entreprise, tels que les applications vocales et les applications intégrées de Cu, dépendent de Lync.</span><span class="sxs-lookup"><span data-stu-id="a26be-108">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="a26be-109">Lync Server 2013 doit être établi en indiquant toutes les dépendances.</span><span class="sxs-lookup"><span data-stu-id="a26be-109">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="a26be-110">Le plan de service vous permet d’élaborer un SLA entre Lync et son service dépendant et de fournir un emplacement de départ pour la négociation SLA.</span><span class="sxs-lookup"><span data-stu-id="a26be-110">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="a26be-111">Le tableau suivant répertorie les services de dépendance typiques pour une infrastructure Lync.</span><span class="sxs-lookup"><span data-stu-id="a26be-111">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="a26be-112">Chacune de ces technologies doit avoir son propre contrôle proactif.</span><span class="sxs-lookup"><span data-stu-id="a26be-112">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="a26be-113">Services de dépendance typiques</span><span class="sxs-lookup"><span data-stu-id="a26be-113">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a26be-114">Service de dépendance</span><span class="sxs-lookup"><span data-stu-id="a26be-114">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a26be-115">Systèmes d’exploitation</span><span class="sxs-lookup"><span data-stu-id="a26be-115">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-116">Matériel du serveur</span><span class="sxs-lookup"><span data-stu-id="a26be-116">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-117">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a26be-117">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-118">Infrastructure à clé publique</span><span class="sxs-lookup"><span data-stu-id="a26be-118">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-119">Service d’attribution de noms de domaine</span><span class="sxs-lookup"><span data-stu-id="a26be-119">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-120">Services de base de données</span><span class="sxs-lookup"><span data-stu-id="a26be-120">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-121">Storage Services</span><span class="sxs-lookup"><span data-stu-id="a26be-121">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-122">Gestion du système – surveillance et distribution</span><span class="sxs-lookup"><span data-stu-id="a26be-122">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-123">Services de sécurité-antivirus</span><span class="sxs-lookup"><span data-stu-id="a26be-123">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-124">Infrastructure réseau-Internet</span><span class="sxs-lookup"><span data-stu-id="a26be-124">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-125">Infrastructure réseau-interne (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="a26be-125">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-126">Infrastructure de téléphonie – PBX IP et passerelles</span><span class="sxs-lookup"><span data-stu-id="a26be-126">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-127">Services Cloud</span><span class="sxs-lookup"><span data-stu-id="a26be-127">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a26be-128">Il est supposé que l’organisation s’est imposée par le biais des fonctions de gestion de niveau de service de base, telles que la modification, l’incident et la gestion des versions, conformément au programme MOF.</span><span class="sxs-lookup"><span data-stu-id="a26be-128">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="a26be-129">La solution Lync doit être adoptée par ces fonctions et être soumise aux mêmes processus de gestion opérationnels.</span><span class="sxs-lookup"><span data-stu-id="a26be-129">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="a26be-130">Outre les informations fournies ci-dessus, nous avons à présent une connaissance plus approfondie des éléments qui peuvent avoir un impact sur le service Lync au sein de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a26be-130">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="a26be-131">Pour garantir la disponibilité et la qualité du service Lync Server 2013, les outils d’analyse suivants doivent accompagner le déploiement de l’architecture de référence:</span><span class="sxs-lookup"><span data-stu-id="a26be-131">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="a26be-132">Outils d’analyse</span><span class="sxs-lookup"><span data-stu-id="a26be-132">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a26be-133">Composant</span><span class="sxs-lookup"><span data-stu-id="a26be-133">Component</span></span></th>
<th><span data-ttu-id="a26be-134">Description</span><span class="sxs-lookup"><span data-stu-id="a26be-134">Description</span></span></th>
<th><span data-ttu-id="a26be-135">Site applicable</span><span class="sxs-lookup"><span data-stu-id="a26be-135">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a26be-136">Serveur de surveillance Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26be-136">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="a26be-137">Déploiement d’au moins un rôle de serveur Lync Server 2013 de surveillance par site central et de configuration du Pack de rapport qualité de l’interface (QoE).</span><span class="sxs-lookup"><span data-stu-id="a26be-137">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="a26be-138">Pour plus d’informations, reportez-vous à la documentation sur le déploiement de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a26be-138">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="a26be-139"><a href="lync-server-2013-deploying-monitoring.md">Déploiement de la surveillance dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a26be-139"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="a26be-140">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="a26be-140">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-141">Attachez chaque liste à l’instance la plus proche du rôle serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="a26be-141">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="a26be-142">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="a26be-142">Central sites</span></span></p>
<p><span data-ttu-id="a26be-143">Sites de succursales</span><span class="sxs-lookup"><span data-stu-id="a26be-143">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-144">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="a26be-144">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="a26be-145">L’importation de System Center Operations Manager 2012 avec le pack d’administration Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a26be-145">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="a26be-146">Le pack d’administration implémente le journal des événements traditionnel et l’instrumentation basée sur le compteur de performance, ainsi que l’activation de l’instrumentation nouvellement disponible dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a26be-146">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="a26be-147">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="a26be-147">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-148">Assurez-vous que la recherche centralisée de rôles et de composants à surveiller est effectuée automatiquement en fonction d’un script de découverte centralisé qui lit le document de topologie publié dans la base de données de gestion centrale.</span><span class="sxs-lookup"><span data-stu-id="a26be-148">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="a26be-149">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-149">Central Site</span></span></p>
<p><span data-ttu-id="a26be-150">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-150">Branch Site</span></span></p>
<p><span data-ttu-id="a26be-151">Site Edge</span><span class="sxs-lookup"><span data-stu-id="a26be-151">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a26be-152">Déployez les agents 2007 de System Center Operations Manager sur tous les serveurs déployés exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a26be-152">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="a26be-153">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-153">Central Site</span></span></p>
<p><span data-ttu-id="a26be-154">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-154">Branch Site</span></span></p>
<p><span data-ttu-id="a26be-155">Site Edge</span><span class="sxs-lookup"><span data-stu-id="a26be-155">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-156">Vérifiez que les alertes classées sont configurées pour la notification:</span><span class="sxs-lookup"><span data-stu-id="a26be-156">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="a26be-157">Alertes de priorité élevée</span><span class="sxs-lookup"><span data-stu-id="a26be-157">High Priority Alerts</span></span></p>
<p><span data-ttu-id="a26be-158">Alertes de priorité moyenne</span><span class="sxs-lookup"><span data-stu-id="a26be-158">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="a26be-159">Autres alertes.</span><span class="sxs-lookup"><span data-stu-id="a26be-159">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="a26be-160">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-160">Central Site</span></span></p>
<p><span data-ttu-id="a26be-161">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-161">Branch Site</span></span></p>
<p><span data-ttu-id="a26be-162">Site Edge</span><span class="sxs-lookup"><span data-stu-id="a26be-162">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="a26be-163">Configurer le contrôle de port pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a26be-163">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="a26be-164">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-164">Central Site</span></span></p>
<p><span data-ttu-id="a26be-165">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-165">Branch Site</span></span></p>
<p><span data-ttu-id="a26be-166">Site Edge</span><span class="sxs-lookup"><span data-stu-id="a26be-166">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-167">Configurer le contrôle d’URL pour votre déploiement</span><span class="sxs-lookup"><span data-stu-id="a26be-167">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="a26be-168">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-168">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-169">Intégration de Lync et System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="a26be-169">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="a26be-170">Déploiement de la fiabilité des appels et de la qualité multimédia MonitoringCall de la fiabilité et de la qualité multimédia utilisez l’ordinateur de surveillance serveur comme nœud d’observation pour contrôler la fiabilité des appels et la qualité multimédia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a26be-170">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="a26be-171">Ces deux fonctionnalités interrogeront les bases de données du serveur de surveillance pour analyse.</span><span class="sxs-lookup"><span data-stu-id="a26be-171">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="a26be-172">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-172">Central Site</span></span></p>
<p><span data-ttu-id="a26be-173">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-173">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-174">Vérifiez que les seuils d’avertissement de qualité multimédia sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="a26be-174">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="a26be-175">Le tableau suivant indique le nombre maximal d’avis de moyenne réseau par codec.</span><span class="sxs-lookup"><span data-stu-id="a26be-175">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="a26be-176">En production, ces scores doivent être surveillés pour une période donnée et le seuil acceptable doit être établi en fonction des scores de NMOS spécifiques de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="a26be-176">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="a26be-177">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-177">Central Site</span></span></p>
<p><span data-ttu-id="a26be-178">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="a26be-178">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-179">Observateur de transactions synthétiques de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a26be-179">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="a26be-180">Déploiement d’un serveur Lync dédié en tant qu’observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="a26be-180">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="a26be-181">Les transactions synthétiques sont des cmdlets Windows PowerShell Lync Server 2013 qui sont automatiquement déclenchées par le pack d’administration sur un intervalle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="a26be-181">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="a26be-182">Celles-ci sont exécutées sur un nœud d’observateur de transactions synthétique qui est un serveur désigné par un administrateur responsable de la découverte et de l’exécution de STs pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="a26be-182">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="a26be-183">Nous vous déconseillons d’utiliser un serveur Microsoft Lync Server 2013 existant en tant que nœud de l’observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="a26be-183">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="a26be-184">En raison de la configuration requise pour l’utilisation du service STs.</span><span class="sxs-lookup"><span data-stu-id="a26be-184">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="a26be-185">Utilisez un nouvel ordinateur serveur (ou un serveur virtuel) pour le nœud de l’observateur de transactions synthétique.</span><span class="sxs-lookup"><span data-stu-id="a26be-185">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="a26be-186">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-186">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="a26be-187">Déploiement du nœud d’observation de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="a26be-187">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="a26be-188">Reportez-vous au document MonitoringCS_withSCOM. docx à partir de la documentation UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="a26be-188">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="a26be-189">Site central</span><span class="sxs-lookup"><span data-stu-id="a26be-189">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="a26be-190">Scores de réseau maximal par codec</span><span class="sxs-lookup"><span data-stu-id="a26be-190">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a26be-191">Scénario</span><span class="sxs-lookup"><span data-stu-id="a26be-191">Scenario</span></span></th>
<th><span data-ttu-id="a26be-192">Codec</span><span class="sxs-lookup"><span data-stu-id="a26be-192">Codec</span></span></th>
<th><span data-ttu-id="a26be-193">NMOS Max</span><span class="sxs-lookup"><span data-stu-id="a26be-193">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a26be-194">UC UC-appel d’UC</span><span class="sxs-lookup"><span data-stu-id="a26be-194">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a26be-195">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="a26be-195">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="a26be-196">4,10</span><span class="sxs-lookup"><span data-stu-id="a26be-196">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-197">UC UC-appel d’UC</span><span class="sxs-lookup"><span data-stu-id="a26be-197">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="a26be-198">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a26be-198">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a26be-199">2,95</span><span class="sxs-lookup"><span data-stu-id="a26be-199">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-200">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="a26be-200">Conference call</span></span></p></td>
<td><p><span data-ttu-id="a26be-201">Siren</span><span class="sxs-lookup"><span data-stu-id="a26be-201">Siren</span></span></p></td>
<td><p><span data-ttu-id="a26be-202">3,72</span><span class="sxs-lookup"><span data-stu-id="a26be-202">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a26be-203">UC-appel RTC</span><span class="sxs-lookup"><span data-stu-id="a26be-203">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a26be-204">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="a26be-204">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="a26be-205">2,95</span><span class="sxs-lookup"><span data-stu-id="a26be-205">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a26be-206">UC-appel RTC</span><span class="sxs-lookup"><span data-stu-id="a26be-206">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="a26be-207">G-711</span><span class="sxs-lookup"><span data-stu-id="a26be-207">G-711</span></span></p></td>
<td><p><span data-ttu-id="a26be-208">3,61</span><span class="sxs-lookup"><span data-stu-id="a26be-208">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a26be-209">Au-dessus ou au-dessus des activités d’analyse plus courantes, les tâches de maintenance doivent être exécutées pour les sites centraux, latéraux et succursales sur une base quotidienne, hebdomadaire et mensuelle, telle qu’elle est définie dans le Guide de fonctionnement de Lync RA.</span><span class="sxs-lookup"><span data-stu-id="a26be-209">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

