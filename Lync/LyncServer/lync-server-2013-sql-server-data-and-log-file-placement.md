---
title: 'Lync Server 2013 : Emplacement des fichiers journaux et des données SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SQL Server data and log file placement
ms:assetid: 67aa525b-8aa3-474f-827e-8e1d4697f30f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398479(v=OCS.15)
ms:contentKeyID: 48184395
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 197141ea62307631eab206fce5403d25b4d89583
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="180ee-102">Emplacement des fichiers journaux et des données SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180ee-102">SQL Server data and log file placement for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180ee-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="180ee-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="180ee-104">Lors de la planification et du déploiement de Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2 SP1 pour votre pool frontal Lync Server 2013, il est important de tenir compte du placement des données et des fichiers journaux sur les disques durs physiques pour des performances.</span><span class="sxs-lookup"><span data-stu-id="180ee-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="180ee-105">La configuration de disque recommandée consiste à implémenter un ensemble RAID de 1 + 0 avec 6 piles.</span><span class="sxs-lookup"><span data-stu-id="180ee-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="180ee-106">Placement de tous les fichiers de base de données et fichiers journaux utilisés par le pool frontal, et les rôles et services de serveur associés (c’est-à-dire, archivage et analyse du serveur, service de groupe de réponse de Lync Server, service de parc de serveurs Lync Server L’Assistant Déploiement génère une configuration qui a été testée pour des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="180ee-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="180ee-107">Les fichiers de base de données et leurs responsables sont décrits dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="180ee-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="180ee-108">Si vos stratégies et configurations SQL Server nécessitent une installation plus spécialisée, les fichiers de base de données et les fichiers journaux peuvent être installés vers tout emplacement prédéfini à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="180ee-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="180ee-109">Pour plus d’informations, voir <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="180ee-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="180ee-110">Données et fichiers journaux pour le centre de gestion central</span><span class="sxs-lookup"><span data-stu-id="180ee-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180ee-111">Fichiers de base de données du magasin de gestion centrale</span><span class="sxs-lookup"><span data-stu-id="180ee-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="180ee-112">Fichier de données ou objet du journal</span><span class="sxs-lookup"><span data-stu-id="180ee-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180ee-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-114">Fichier journal des transactions du magasin de gestion central</span><span class="sxs-lookup"><span data-stu-id="180ee-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-116">Conserve la configuration de la topologie Lync Server 2013 actuelle, telle que définie et publiée par le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="180ee-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-117">Lis. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-118">Fichier de données de service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="180ee-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-119">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-120">Journal des transactions pour le fichier de données du service d’information d’emplacement</span><span class="sxs-lookup"><span data-stu-id="180ee-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="180ee-121">Données et fichiers journaux pour l’utilisateur, les conférences et le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="180ee-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180ee-122">Fichiers de base de données principaux de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="180ee-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="180ee-123">Fichier de données ou objet du journal</span><span class="sxs-lookup"><span data-stu-id="180ee-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180ee-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-125">Données utilisateur persistantes (telles que les listes de contrôle d’accès (ACL), les contacts, les conférences planifiées)</span><span class="sxs-lookup"><span data-stu-id="180ee-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-127">Journal des transactions pour les données RTC</span><span class="sxs-lookup"><span data-stu-id="180ee-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-128">RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-129">Gère les données utilisateur temporaires (données d’exécution de la présence)</span><span class="sxs-lookup"><span data-stu-id="180ee-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-131">Journal des transactions pour les données RTCDyn</span><span class="sxs-lookup"><span data-stu-id="180ee-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-132">RTCAb. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-133">La base de données du carnet d’adresses RTC (Real-Time communications) est le référentiel SQL Server où sont stockés les informations de service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="180ee-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-134">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-135">Journal des transactions pour le service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="180ee-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="180ee-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="180ee-137">Héberge l’annuaire de conférences</span><span class="sxs-lookup"><span data-stu-id="180ee-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-138">Rtcxds. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-139">Conserve la sauvegarde des données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="180ee-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-141">Journal des transactions pour les données Rtcxds</span><span class="sxs-lookup"><span data-stu-id="180ee-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="180ee-142">Données et fichiers journaux pour le parc d’appels et le groupe Response</span><span class="sxs-lookup"><span data-stu-id="180ee-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180ee-143">base de données d’applications</span><span class="sxs-lookup"><span data-stu-id="180ee-143">Application database</span></span></th>
<th><span data-ttu-id="180ee-144">Fichier de données ou objet du journal</span><span class="sxs-lookup"><span data-stu-id="180ee-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180ee-145">Cpsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-146">Base de données d’information dynamique pour l’application de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="180ee-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-148">Journal des transactions pour le fichier de données d’application de parc d’appels</span><span class="sxs-lookup"><span data-stu-id="180ee-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-149">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-150">Fichier de données du service de groupe de réponse Lync Server pour la configuration des services</span><span class="sxs-lookup"><span data-stu-id="180ee-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-152">Fichier journal des transactions pour la configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="180ee-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-153">Rgsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-154">Fichier de données du service Response Group pour les opérations d’exécution</span><span class="sxs-lookup"><span data-stu-id="180ee-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-156">Journal des transactions pour le fichier de données Runtime du service de Response Group</span><span class="sxs-lookup"><span data-stu-id="180ee-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="180ee-157">Données et fichiers journaux pour le serveur d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="180ee-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180ee-158">Archivage et contrôle des fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="180ee-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="180ee-159">Fichier de données ou objet du journal</span><span class="sxs-lookup"><span data-stu-id="180ee-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180ee-160">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-161">Magasin de données pour le processus d’enregistrement des détails des appels (CDR) du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="180ee-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-163">Journal des transactions pour les données d’enregistrement des détails des appels (CDR)</span><span class="sxs-lookup"><span data-stu-id="180ee-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-164">QoEMetrics. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-165">Fichier de données de qualité de l’utilisateur stocké à partir du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="180ee-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-167">Journal des transactions d’analyse des données</span><span class="sxs-lookup"><span data-stu-id="180ee-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180ee-168">LcsLog. mdf</span><span class="sxs-lookup"><span data-stu-id="180ee-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="180ee-169">Fichier de données pour la conservation des données de messagerie instantanée et de conférence sur un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="180ee-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180ee-170">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="180ee-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="180ee-171">Journal des transactions d’archivage des données</span><span class="sxs-lookup"><span data-stu-id="180ee-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="180ee-172">Dans cette rubrique, les références sont prises sur le disque et sur le jeu RAID.</span><span class="sxs-lookup"><span data-stu-id="180ee-172">In this topic, references are made to disk and to RAID set.</span></span> <span data-ttu-id="180ee-173">Notez que dans la configuration des ressources SQL Server, le fait de faire référence à un disque correspond à un seul appareil matériel.</span><span class="sxs-lookup"><span data-stu-id="180ee-173">Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device.</span></span> <span data-ttu-id="180ee-174">Un disque dur doté de deux partitions, l’un contenant les fichiers journaux et l’autre partition contenant les fichiers de données, n’est pas le même que sur deux disques.</span><span class="sxs-lookup"><span data-stu-id="180ee-174">A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="180ee-175">En ce qui concerne les jeux RAID, il existe plusieurs technologies RAID différentes de celles de différents fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="180ee-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="180ee-176">Par le biais de la prolifération des réseaux de zone de stockage, les jeux RAID dédiés à un seul système sont plus rares.</span><span class="sxs-lookup"><span data-stu-id="180ee-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="180ee-177">Vous devez consulter votre fabricant de réseau ou de réseau pour déterminer la configuration qui correspond le mieux à votre disposition de disque lorsque vous configurez des performances SQL Server avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="180ee-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="180ee-178">Notez également que tous les lecteurs de disque ne sont pas créés de la même manière ; d’autres sont plus performantes que d’autres.</span><span class="sxs-lookup"><span data-stu-id="180ee-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="180ee-179">Même les lecteurs du même fabricant peuvent varier en fonction de la vitesse de rotation, de la taille du cache matériel et d’autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="180ee-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

