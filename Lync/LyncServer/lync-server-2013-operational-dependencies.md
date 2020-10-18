---
title: 'Lync Server 2013 : dépendances opérationnelles'
description: 'Lync Server 2013 : dépendances opérationnelles.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e240981f5dfded7c27f123c8483794ea3ffedff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579190"
---
# <a name="operational-dependencies-in-lync-server-2013"></a><span data-ttu-id="4964c-103">Dépendances opérationnelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4964c-103">Operational dependencies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4964c-104">_**Dernière modification de la rubrique :** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="4964c-104">_**Topic Last Modified:** 2015-05-15_</span></span>

<span data-ttu-id="4964c-105">L’architecture de référence décrite dans ce document vous permettra de vous assurer que vous disposez d’un déploiement Lync Server 2013 non seulement adapté aux besoins de l’organisation, mais qu’il est conçu conformément aux meilleures pratiques de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4964c-105">The Reference Architecture discussed in this document will help ensure that you have a Lync Server 2013 deployment that not only scales to the organization’s requirements but is architected as per Microsoft best practices.</span></span> <span data-ttu-id="4964c-106">Il est possible que l’implémentation de Lync Server 2013 soit un service dynamique et que tous les autres services de l’entreprise nécessitent toujours une surveillance et une gestion proactive pour maintenir un niveau élevé de disponibilité de service et de qualité de service pour l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4964c-106">Be that as it may the Lync Server 2013 implementation is a dynamic service and like any other service in the enterprise still requires monitoring and proactive management to maintain high level of service availability and service quality to the business.</span></span>

<span data-ttu-id="4964c-107">Dans la mesure où Lync Server 2013 devient profondément ingranulaire dans le secteur quotidien de l’organisation, il est important que le service soit géré par une gestion des niveaux de service précise et tangible.</span><span class="sxs-lookup"><span data-stu-id="4964c-107">As Lync Server 2013 becomes deeply ingrained in the organization’s everyday business it is important that the service be managed by accurate and tangible service level management.</span></span> <span data-ttu-id="4964c-108">L’architecture système de Lync peut devenir complexe et très intégrée et, afin de maintenir une gestion efficace du niveau de service et établir des SLA pour Lync Server 2013, il est essentiel de comprendre les dépendances du système sur d’autres plateformes et serveurs.</span><span class="sxs-lookup"><span data-stu-id="4964c-108">The Lync system architecture can become complex and very integrated and in order to maintain effective service level management and establish SLAs for Lync Server 2013 it becomes critical to understand the system’s dependencies on other platforms and servers.</span></span> <span data-ttu-id="4964c-109">Tout aussi important est de noter quels services d’entreprise, tels que les applications vocales et de communications unifiées, dépendent de Lync.</span><span class="sxs-lookup"><span data-stu-id="4964c-109">Equally important is to note which business services, such as voice and UC integrated applications, become dependent on Lync.</span></span>

<span data-ttu-id="4964c-110">Lync Server 2013 doit être établi en notant toutes ces dépendances.</span><span class="sxs-lookup"><span data-stu-id="4964c-110">Lync Server 2013 must be established noting all the said dependencies.</span></span> <span data-ttu-id="4964c-111">Le plan de service vous permettra de formuler un accord SLA entre Lync et son service dépendant et de fournir un emplacement de départ pour la négociation SLA.</span><span class="sxs-lookup"><span data-stu-id="4964c-111">The service map will allow you to formulate a SLA between Lync and its dependent service and provide a starting place for SLA negotiation.</span></span>

<span data-ttu-id="4964c-112">Le tableau suivant répertorie les services de dépendance typiques d’une infrastructure Lync.</span><span class="sxs-lookup"><span data-stu-id="4964c-112">The following table lists the typical dependency services for a Lync infrastructure.</span></span> <span data-ttu-id="4964c-113">Chacune de ces technologies doit avoir sa propre surveillance proactive.</span><span class="sxs-lookup"><span data-stu-id="4964c-113">Each of these technologies should have its own proactive monitoring.</span></span>

### <a name="typical-dependency-services"></a><span data-ttu-id="4964c-114">Services de dépendance typiques</span><span class="sxs-lookup"><span data-stu-id="4964c-114">Typical dependency services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4964c-115">Service de dépendance</span><span class="sxs-lookup"><span data-stu-id="4964c-115">Dependency Service</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4964c-116">Systèmes d’exploitation</span><span class="sxs-lookup"><span data-stu-id="4964c-116">Operating systems</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-117">Matériel de serveur</span><span class="sxs-lookup"><span data-stu-id="4964c-117">Server Hardware</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-118">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4964c-118">Active Directory</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-119">infrastructure à clé publique</span><span class="sxs-lookup"><span data-stu-id="4964c-119">Public Key Infrastructure</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-120">Service d’attribution de noms de domaine</span><span class="sxs-lookup"><span data-stu-id="4964c-120">Domain Naming Service</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-121">Services de base de données</span><span class="sxs-lookup"><span data-stu-id="4964c-121">Database Services</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-122">Services de stockage</span><span class="sxs-lookup"><span data-stu-id="4964c-122">Storage Services</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-123">Gestion du système – surveillance et distribution</span><span class="sxs-lookup"><span data-stu-id="4964c-123">System Management – Monitoring and distribution</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-124">Services de sécurité-antivirus</span><span class="sxs-lookup"><span data-stu-id="4964c-124">Security Services - Antivirus</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-125">Infrastructure réseau-Internet</span><span class="sxs-lookup"><span data-stu-id="4964c-125">Network Infrastructure - Internet</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-126">Infrastructure réseau : interne (LAN/WAN)</span><span class="sxs-lookup"><span data-stu-id="4964c-126">Network Infrastructure – Internal (LAN/WAN)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-127">Infrastructure de téléphonie – IP-PBX et passerelles</span><span class="sxs-lookup"><span data-stu-id="4964c-127">Telephony Infrastructure – IP-PBX and Gateways</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-128">Services Cloud</span><span class="sxs-lookup"><span data-stu-id="4964c-128">Cloud Services</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4964c-129">Il est supposé que l’organisation est très mature dans l’exercice des fonctions de base de gestion du niveau de service, telles que les modifications, la gestion des incidents et des versions, comme le préconise la structure MOF.</span><span class="sxs-lookup"><span data-stu-id="4964c-129">It is assumed that the organization is operationally mature in exercising basic service level management functions such as change, incident and release management as prescribed by the MOF.</span></span> <span data-ttu-id="4964c-130">La solution Lync doit être adoptée par ces fonctions et être soumise aux mêmes processus de gestion des opérations opérationnelles.</span><span class="sxs-lookup"><span data-stu-id="4964c-130">The Lync solution should be adopted by these functions and become subject to the same operational management processes.</span></span>

<span data-ttu-id="4964c-131">En s’appuyant sur les informations recueillies ci-dessus, nous avons désormais une meilleure compréhension de ce qui peut avoir un impact sur le service Lync dans l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="4964c-131">Building on the information obtained above we now have a greater understanding of what can impact the Lync service in the enterprise.</span></span> <span data-ttu-id="4964c-132">Pour garantir la qualité et la disponibilité du service Lync Server 2013, les outils de surveillance suivants doivent accompagner le déploiement de l’architecture de référence :</span><span class="sxs-lookup"><span data-stu-id="4964c-132">To help ensure Lync Server 2013 service availability and quality, the following monitoring tools must accompany the reference architecture deployment:</span></span>

### <a name="monitoring-tools"></a><span data-ttu-id="4964c-133">Outils de surveillance</span><span class="sxs-lookup"><span data-stu-id="4964c-133">Monitoring tools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4964c-134">Composant</span><span class="sxs-lookup"><span data-stu-id="4964c-134">Component</span></span></th>
<th><span data-ttu-id="4964c-135">Description</span><span class="sxs-lookup"><span data-stu-id="4964c-135">Description</span></span></th>
<th><span data-ttu-id="4964c-136">Site applicable</span><span class="sxs-lookup"><span data-stu-id="4964c-136">Applicable Site</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4964c-137">Serveur de surveillance Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4964c-137">Lync Server 2013 Monitoring Server</span></span></p></td>
<td><p><span data-ttu-id="4964c-138">Déployez au moins un rôle serveur de surveillance Lync Server 2013 par site central et configurez le Pack de rapports qualité de l’expérience (QoE).</span><span class="sxs-lookup"><span data-stu-id="4964c-138">Deploy at least one Lync Server 2013 Monitoring Server role per Central site and configure Quality of Experience (QoE) Reporting Pack.</span></span></p>
<p><span data-ttu-id="4964c-139">Pour plus d’informations, reportez-vous à la documentation de déploiement de Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="4964c-139">Refer to the Lync Server 2013 Deployment documentation for further details:</span></span></p>
<p><span data-ttu-id="4964c-140"><a href="lync-server-2013-deploying-monitoring.md">Déploiement de la surveillance dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4964c-140"><a href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="4964c-141">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="4964c-141">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-142">Attachez chaque pool à l’instance la plus proche du rôle serveur de surveillance.</span><span class="sxs-lookup"><span data-stu-id="4964c-142">Tether each pool to its nearest instance of the Monitoring Server role.</span></span></p></td>
<td><p><span data-ttu-id="4964c-143">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="4964c-143">Central sites</span></span></p>
<p><span data-ttu-id="4964c-144">Sites de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-144">Branch sites</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-145">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="4964c-145">System Center Operations Manager 2012</span></span></p></td>
<td><p><span data-ttu-id="4964c-146">System Center Operations Manager 2012 avec le pack d’administration Microsoft Lync Server 2013 (MP) importé.</span><span class="sxs-lookup"><span data-stu-id="4964c-146">System Center Operations Manager 2012 with the Microsoft Lync Server 2013 Management Pack (MP) imported.</span></span></p>
<p><span data-ttu-id="4964c-147">Le pack d’administration met en œuvre le journal des événements traditionnels et l’instrumentation basée sur les compteurs de performances, ainsi que l’activation de l’instrumentation nouvellement disponible dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4964c-147">The Management Pack implements traditional Event Log and Performance counter based instrumentation is utilized as well as enabling newly available instrumentation in Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="4964c-148">Sites centraux</span><span class="sxs-lookup"><span data-stu-id="4964c-148">Central sites</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-149">Assurez-vous que la découverte centrale pour la découverte de rôles et de composants qui doivent être surveillés est automatiquement effectuée en fonction d’un script de découverte central qui lit le document de topologie publié dans la base de données de gestion centrale.</span><span class="sxs-lookup"><span data-stu-id="4964c-149">Make sure that Central Discovery to discovery of roles and components that need to be monitored are automatically completed based on a central discovery script that reads the topology document published in Central Management Database.</span></span></p></td>
<td><p><span data-ttu-id="4964c-150">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-150">Central Site</span></span></p>
<p><span data-ttu-id="4964c-151">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-151">Branch Site</span></span></p>
<p><span data-ttu-id="4964c-152">Site Edge</span><span class="sxs-lookup"><span data-stu-id="4964c-152">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="4964c-153">Déployez les agents System Center Operations Manager 2007 sur tous les serveurs déployés exécutant Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4964c-153">Deploy System Centre Operations Manager 2007 agents to all deployed servers running Lync Server.</span></span></p></td>
<td><p><span data-ttu-id="4964c-154">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-154">Central Site</span></span></p>
<p><span data-ttu-id="4964c-155">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-155">Branch Site</span></span></p>
<p><span data-ttu-id="4964c-156">Site Edge</span><span class="sxs-lookup"><span data-stu-id="4964c-156">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-157">Assurez-vous que les alertes classées par ordre de priorité sont configurées pour la notification :</span><span class="sxs-lookup"><span data-stu-id="4964c-157">Make sure Prioritized Alerts are configured for notification:</span></span></p>
<p><span data-ttu-id="4964c-158">Alertes à priorité élevée</span><span class="sxs-lookup"><span data-stu-id="4964c-158">High Priority Alerts</span></span></p>
<p><span data-ttu-id="4964c-159">Alertes de priorité moyenne</span><span class="sxs-lookup"><span data-stu-id="4964c-159">Medium Priority Alerts</span></span></p>
<p><span data-ttu-id="4964c-160">Autres alertes.</span><span class="sxs-lookup"><span data-stu-id="4964c-160">Other Alerts.</span></span></p></td>
<td><p><span data-ttu-id="4964c-161">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-161">Central Site</span></span></p>
<p><span data-ttu-id="4964c-162">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-162">Branch Site</span></span></p>
<p><span data-ttu-id="4964c-163">Site Edge</span><span class="sxs-lookup"><span data-stu-id="4964c-163">Edge Site</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="4964c-164">Configurez la surveillance des ports pour votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="4964c-164">Configure Port monitoring for your deployment.</span></span></p></td>
<td><p><span data-ttu-id="4964c-165">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-165">Central Site</span></span></p>
<p><span data-ttu-id="4964c-166">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-166">Branch Site</span></span></p>
<p><span data-ttu-id="4964c-167">Site Edge</span><span class="sxs-lookup"><span data-stu-id="4964c-167">Edge Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-168">Configurer la surveillance d’URL pour votre déploiement</span><span class="sxs-lookup"><span data-stu-id="4964c-168">Configure URL monitoring for your deployment</span></span></p></td>
<td><p><span data-ttu-id="4964c-169">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-169">Central Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-170">Intégration de Lync et de System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="4964c-170">Lync and System Center Operations Manager integration</span></span></p></td>
<td><p><span data-ttu-id="4964c-171">Déploiement de la fiabilité des appels et de la qualité des médias MonitoringCall fiabilité et surveillance de la qualité des médias utilisez le serveur de surveillance comme nœud observateur pour surveiller la fiabilité des appels et la qualité des médias de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4964c-171">Deploy Call Reliability and Media Quality MonitoringCall reliability and media quality monitoring use the Monitoring Server computer as their watcher node to monitor call reliability and media quality of Lync Server.</span></span> <span data-ttu-id="4964c-172">Ces deux fonctionnalités interrogent les bases de données du serveur de surveillance pour effectuer une analyse.</span><span class="sxs-lookup"><span data-stu-id="4964c-172">Both of these features query the Monitoring Server databases to do analysis.</span></span></p></td>
<td><p><span data-ttu-id="4964c-173">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-173">Central Site</span></span></p>
<p><span data-ttu-id="4964c-174">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-174">Branch Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-175">Vérifier que les seuils d’avertissement de qualité des médias sont correctement configurés.</span><span class="sxs-lookup"><span data-stu-id="4964c-175">Ensure Media Quality warning thresholds are accurately configured.</span></span> <span data-ttu-id="4964c-176">Le tableau suivant indique les notes moyennes d’opinion réseau maximales par codec.</span><span class="sxs-lookup"><span data-stu-id="4964c-176">The following table indicates the maximum Network Mean Opinion Scores by Codec.</span></span> <span data-ttu-id="4964c-177">En production, ces scores doivent être surveillés pendant une période déterminée et des seuils acceptables doivent être établis en fonction des scores NMOS spécifiques de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4964c-177">In production these scores should be monitored for a set period and acceptable thresholds must be established based on the organization specific NMOS scores.</span></span></p></td>
<td><p><span data-ttu-id="4964c-178">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-178">Central Site</span></span></p>
<p><span data-ttu-id="4964c-179">Site de succursale</span><span class="sxs-lookup"><span data-stu-id="4964c-179">Branch Site</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-180">Observateur de transactions synthétiques Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4964c-180">Lync Server 2013 Synthetic Transaction Watcher</span></span></p></td>
<td><p><span data-ttu-id="4964c-181">Déployez un serveur Lync dédié pour qu’il soit un observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="4964c-181">Deploy a dedicated Lync Server to be a synthetic transaction watcher.</span></span></p>
<p><span data-ttu-id="4964c-182">Les transactions synthétiques sont des applets de commande Lync Server 2013 Windows PowerShell qui sont automatiquement déclenchées par le pack d’administration sur un intervalle prédéfini.</span><span class="sxs-lookup"><span data-stu-id="4964c-182">Synthetic transactions are Lync Server 2013 Windows PowerShell cmdlets that are automatically triggered by the management pack on a predefined interval.</span></span> <span data-ttu-id="4964c-183">Ceux-ci sont exécutés sur un nœud observateur de transactions synthétiques qui est un serveur désigné par l’administrateur responsable de la découverte et de l’exécution du service STs pour chaque pool.</span><span class="sxs-lookup"><span data-stu-id="4964c-183">These are executed on a synthetic transaction watcher node which is an administrator designated server responsible for discovery and execution of STs for each pool.</span></span></p>
<p><span data-ttu-id="4964c-184">Nous vous déconseillons d’utiliser un serveur Microsoft Lync Server 2013 existant comme nœud observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="4964c-184">We do not recommend that you use an existing Microsoft Lync Server 2013 server as a synthetic transaction watcher node.</span></span> <span data-ttu-id="4964c-185">Cela est dû à l’utilisation élevée de la mémoire et de l’UC pour l’exécution de STs.</span><span class="sxs-lookup"><span data-stu-id="4964c-185">This is due to the high CPU/memory usage requirements for running STs.</span></span> <span data-ttu-id="4964c-186">Utilisez un nouvel ordinateur serveur (ou un serveur virtuel) pour le nœud observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="4964c-186">Use a new server computer (or a virtual server) for the synthetic transaction watcher node.</span></span></p></td>
<td><p><span data-ttu-id="4964c-187">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-187">Central Site</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="4964c-188">Déploiement du nœud observateur de transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="4964c-188">Deploying synthetic transactions watcher node.</span></span></p>
<p><span data-ttu-id="4964c-189">Reportez-vous au document MonitoringCS_withSCOM.docx de la documentation UCTAP Connect.</span><span class="sxs-lookup"><span data-stu-id="4964c-189">Refer to the MonitoringCS_withSCOM.docx document from UCTAP connect documentation.</span></span></p></td>
<td><p><span data-ttu-id="4964c-190">Site central</span><span class="sxs-lookup"><span data-stu-id="4964c-190">Central Site</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a><span data-ttu-id="4964c-191">Nombre maximal de scores MOS réseau par codec</span><span class="sxs-lookup"><span data-stu-id="4964c-191">Maximum Network MOS scores per codec</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4964c-192">Scénario</span><span class="sxs-lookup"><span data-stu-id="4964c-192">Scenario</span></span></th>
<th><span data-ttu-id="4964c-193">Codec</span><span class="sxs-lookup"><span data-stu-id="4964c-193">Codec</span></span></th>
<th><span data-ttu-id="4964c-194">Nombre maximal de NMOS</span><span class="sxs-lookup"><span data-stu-id="4964c-194">Max NMOS</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4964c-195">Appels UC-UC</span><span class="sxs-lookup"><span data-stu-id="4964c-195">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="4964c-196">RTAudio WB</span><span class="sxs-lookup"><span data-stu-id="4964c-196">RTAudio WB</span></span></p></td>
<td><p><span data-ttu-id="4964c-197">4.10</span><span class="sxs-lookup"><span data-stu-id="4964c-197">4.10</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-198">Appels UC-UC</span><span class="sxs-lookup"><span data-stu-id="4964c-198">UC-UC call</span></span></p></td>
<td><p><span data-ttu-id="4964c-199">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="4964c-199">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="4964c-200">2,95</span><span class="sxs-lookup"><span data-stu-id="4964c-200">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-201">Téléconférence</span><span class="sxs-lookup"><span data-stu-id="4964c-201">Conference call</span></span></p></td>
<td><p><span data-ttu-id="4964c-202">Siren</span><span class="sxs-lookup"><span data-stu-id="4964c-202">Siren</span></span></p></td>
<td><p><span data-ttu-id="4964c-203">3,72</span><span class="sxs-lookup"><span data-stu-id="4964c-203">3.72</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4964c-204">Appels UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="4964c-204">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="4964c-205">RTAudio NB</span><span class="sxs-lookup"><span data-stu-id="4964c-205">RTAudio NB</span></span></p></td>
<td><p><span data-ttu-id="4964c-206">2,95</span><span class="sxs-lookup"><span data-stu-id="4964c-206">2.95</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4964c-207">Appels UC-PSTN</span><span class="sxs-lookup"><span data-stu-id="4964c-207">UC-PSTN call</span></span></p></td>
<td><p><span data-ttu-id="4964c-208">G-711</span><span class="sxs-lookup"><span data-stu-id="4964c-208">G-711</span></span></p></td>
<td><p><span data-ttu-id="4964c-209">3,61</span><span class="sxs-lookup"><span data-stu-id="4964c-209">3.61</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4964c-210">Au-delà et au-delà des activités de surveillance plus anciennes, les tâches de maintenance doivent être exécutées pour les sites centraux, Edge et de succursale sur une base périodique quotidienne, hebdomadaire et mensuelle, comme défini dans le guide des opérations de l’autorité de session Lync.</span><span class="sxs-lookup"><span data-stu-id="4964c-210">Over and above the previous pro-active monitoring activities, maintenance tasks should be executed for Central, Edge and Branch sites on a recurring daily, weekly and monthly basis as defined in the Lync RA Operations Guide.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

