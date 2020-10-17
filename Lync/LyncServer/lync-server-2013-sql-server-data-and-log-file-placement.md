---
title: 'Lync Server 2013 : emplacement des fichiers journaux et de données SQL Server'
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
ms.openlocfilehash: 3f536f2d67010856259abf6b98936cd9e096fc93
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509621"
---
# <a name="sql-server-data-and-log-file-placement-for-lync-server-2013"></a><span data-ttu-id="ca06a-102">Emplacement des fichiers journaux et de données SQL Server pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca06a-102">SQL Server data and log file placement for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca06a-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ca06a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ca06a-104">Lors de la planification et du déploiement de Microsoft SQL Server 2012 ou Microsoft SQL Server 2008 R2 SP1 pour votre pool frontal Lync Server 2013, il est important de prendre en compte le placement des données et des fichiers journaux sur des disques durs physiques pour des performances optimales.</span><span class="sxs-lookup"><span data-stu-id="ca06a-104">During the planning and deployment of Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2 SP1 for your Lync Server 2013 Front End pool, an important consideration is the placement of data and log files onto physical hard disks for performance.</span></span> <span data-ttu-id="ca06a-105">La configuration de disque recommandée consiste à implémenter un ensemble RAID 1 + 0 à l’aide de 6 piles de disques.</span><span class="sxs-lookup"><span data-stu-id="ca06a-105">The recommended disk configuration is to implement a 1+0 RAID set using 6 spindles.</span></span> <span data-ttu-id="ca06a-106">En plaçant tous les fichiers de base de données et journaux utilisés par le pool frontal et les rôles serveur et services associés (c’est-à-dire, le serveur d’archivage et de surveillance, le service Response Group Lync Server, le service de parcage d’appel Lync Server) sur le jeu de disques RAID à l’aide de l’Assistant Déploiement de Lync</span><span class="sxs-lookup"><span data-stu-id="ca06a-106">Placing all database and log files that are used by the Front End pool and associated server roles and services (that is, Archiving and Monitoring Server, Lync Server Response Group service, Lync Server Call Park service) onto the RAID drive set using the Lync Server Deployment Wizard will result in a configuration that has been tested for good performance.</span></span> <span data-ttu-id="ca06a-107">Le tableau suivant présente les différents fichiers de base de données ainsi que leur rôle.</span><span class="sxs-lookup"><span data-stu-id="ca06a-107">The database files and what they are responsible for is detailed in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca06a-108">Si vos stratégies et configurations SQL Server nécessitent une installation plus spécialisée, la base de données et les fichiers journaux peuvent être installés sur un emplacement prédéfini à l’aide de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca06a-108">If your policies and SQL Server configurations require a more specialized installation, the database and log files can be installed to any pre-defined location using the Lync Server Management Shell.</span></span> <span data-ttu-id="ca06a-109">Pour plus d’informations, voir <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">installation de la base de données à l’aide de Lync Server Management Shell dans Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ca06a-109">See <A href="lync-server-2013-database-installation-using-lync-server-management-shell.md">Database installation using Lync Server Management Shell in Lync Server 2013</A> for more details.</span></span>



</div>

### <a name="data-and-log-files-for-central-management-store"></a><span data-ttu-id="ca06a-110">Fichiers de données et fichiers journaux pour le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="ca06a-110">Data and Log Files for Central Management Store</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca06a-111">Fichiers de base de données du magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="ca06a-111">Central Management store database files</span></span></th>
<th><span data-ttu-id="ca06a-112">Objectif du fichier de données ou du fichier journal</span><span class="sxs-lookup"><span data-stu-id="ca06a-112">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-113">XDS. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-113">Xds.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-114">Fichier journal des transactions pour le magasin central de gestion</span><span class="sxs-lookup"><span data-stu-id="ca06a-114">Transaction log file for the Central Management store</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-115">XDS. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-115">Xds.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-116">Gère la configuration de la topologie Lync Server 2013 actuelle, telle que définie et publiée par le générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="ca06a-116">Maintains the configuration of the current Lync Server 2013 topology, as defined and published by Topology Builder</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-117">Lis. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-117">Lis.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-118">Fichier de données du service informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ca06a-118">Location Information service data file</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-119">Lis. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-119">Lis.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-120">Journal des transactions pour le fichier de données du service informations d’emplacement</span><span class="sxs-lookup"><span data-stu-id="ca06a-120">Transaction log for the Location Information service data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-user-conferencing-and-address-book"></a><span data-ttu-id="ca06a-121">Fichiers de données et fichiers journaux pour l’utilisateur, la conférence et le carne d’adresses</span><span class="sxs-lookup"><span data-stu-id="ca06a-121">Data and Log files for User, Conferencing, and Address Book</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca06a-122">Principaux fichiers de base de données Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca06a-122">Core Lync Server 2013 database files</span></span></th>
<th><span data-ttu-id="ca06a-123">Objectif du fichier de données ou du fichier journal</span><span class="sxs-lookup"><span data-stu-id="ca06a-123">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-124">RTC. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-124">Rtc.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-125">Données utilisateur persistantes (par exemple, listes de contrôle d’accès (ACL), contacts, conférences planifiées)</span><span class="sxs-lookup"><span data-stu-id="ca06a-125">Persistent user data (for example, access control lists (ACLs), contacts, scheduled conferences)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-126">RTC. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-126">Rtc.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-127">Journal des transactions pour les données RTC</span><span class="sxs-lookup"><span data-stu-id="ca06a-127">Transaction log for Rtc data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-128">RTCDyn. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-128">Rtcdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-129">Gère les données utilisateur temporaires (données d’exécution de présence)</span><span class="sxs-lookup"><span data-stu-id="ca06a-129">Maintains transient user data (presence runtime data)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-130">RTCDyn. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-130">Rtcdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-131">Journal des transactions pour les données RTCDyn</span><span class="sxs-lookup"><span data-stu-id="ca06a-131">Transaction log for Rtcdyn data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-132">RTCAb. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-132">Rtcab.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-133">La base de données de carnet d’adresses RTC est le référentiel SQL Server où les informations de service de carnet d’adresses sont stockées</span><span class="sxs-lookup"><span data-stu-id="ca06a-133">Real-time communications (RTC) address book database is the SQL Server repository where Address Book service information is stored</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-134">RTCAb. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-134">Rtcab.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-135">Fichier journal des transactions pour le service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="ca06a-135">Transaction log for Address Book Service</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-136">Rtclocal. mdb</span><span class="sxs-lookup"><span data-stu-id="ca06a-136">Rtclocal.mdb</span></span></p></td>
<td><p><span data-ttu-id="ca06a-137">Héberge l’annuaire des conférences</span><span class="sxs-lookup"><span data-stu-id="ca06a-137">Hosts the conference directory</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-138">Rtcxds. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-138">Rtcxds.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-139">Conserve la sauvegarde des données utilisateur</span><span class="sxs-lookup"><span data-stu-id="ca06a-139">Maintains the backup for user data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-140">Rtcxds. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-140">Rtcxds.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-141">Journal des transactions pour les données Rtcxds</span><span class="sxs-lookup"><span data-stu-id="ca06a-141">Transaction log for Rtcxds data</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-call-park-and-response-group"></a><span data-ttu-id="ca06a-142">Fichiers de données et fichiers journaux pour le parcage d’appel et le groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="ca06a-142">Data and Log Files for Call Park and Response Group</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca06a-143">Base de données d’applications</span><span class="sxs-lookup"><span data-stu-id="ca06a-143">Application database</span></span></th>
<th><span data-ttu-id="ca06a-144">Objectif du fichier de données ou du fichier journal</span><span class="sxs-lookup"><span data-stu-id="ca06a-144">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-145">Cpsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-145">Cpsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-146">Base de données d’informations dynamiques pour l’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ca06a-146">Dynamic information database for the Call Park application</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-147">Cpsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-147">Cpsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-148">Journal des transactions pour le fichier de données de l’application de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="ca06a-148">Transaction log for Call Park application data file</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-149">Rgsconfig. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-149">Rgsconfig.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-150">Fichier de données du service Lync Server Response Group pour la configuration des services</span><span class="sxs-lookup"><span data-stu-id="ca06a-150">Lync Server Response Group service data file for the configuration of the services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-151">Rgsconfig. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-151">Rgsconfig.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-152">Fichier journal des transactions pour la configuration de l’application Response Group</span><span class="sxs-lookup"><span data-stu-id="ca06a-152">Transaction log file for the Response Group application configuration</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-153">Rgsdyn. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-153">Rgsdyn.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-154">Fichier de données du service Response Group pour les opérations d’exécution</span><span class="sxs-lookup"><span data-stu-id="ca06a-154">Response Group service data file for runtime operations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-155">Rgsdyn. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-155">Rgsdyn.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-156">Fichier journal des transactions pour le fichier de données d’exécution du service Response Group</span><span class="sxs-lookup"><span data-stu-id="ca06a-156">Transaction log for the Response Group service runtime data file</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="data-and-log-files-for-archiving-and-monitoring-server"></a><span data-ttu-id="ca06a-157">Fichiers de données et fichiers journaux pour le serveur d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="ca06a-157">Data and Log Files for Archiving and Monitoring Server</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca06a-158">Fichiers de base de données d’archivage et de surveillance</span><span class="sxs-lookup"><span data-stu-id="ca06a-158">Archiving and Monitoring database files</span></span></th>
<th><span data-ttu-id="ca06a-159">Objectif du fichier de données ou du fichier journal</span><span class="sxs-lookup"><span data-stu-id="ca06a-159">Data file or log purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-160">LcsCdr. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-160">LcsCdr.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-161">Magasin de données pour le processus d’enregistrement des détails des appels (CDR) du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="ca06a-161">Data store for the call detail recording (CDR) process of the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-162">LcsCdr. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-162">LcsCdr.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-163">Fichier journal des transactions pour les données d’enregistrement des détails des appels (CDR)</span><span class="sxs-lookup"><span data-stu-id="ca06a-163">Transaction log for call detail recording (CDR) data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-164">QoEMetrics. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-164">QoEMetrics.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-165">Fichier de données de qualité de l’expérience stocké à partir du serveur de surveillance</span><span class="sxs-lookup"><span data-stu-id="ca06a-165">Quality of Experience data file stored from the Monitoring Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-166">QoEMetrics. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-166">QoEMetrics.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-167">Fichier journal des transactions pour les données de surveillance</span><span class="sxs-lookup"><span data-stu-id="ca06a-167">Transaction log for Monitoring data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca06a-168">LcsLog. mdf</span><span class="sxs-lookup"><span data-stu-id="ca06a-168">Lcslog.mdf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-169">Fichier de données pour la rétention des données de messagerie instantanée et de conférence sur un serveur d’archivage</span><span class="sxs-lookup"><span data-stu-id="ca06a-169">Data file for the retention of instant messaging and conferencing data on an Archiving Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca06a-170">LcsLog. ldf</span><span class="sxs-lookup"><span data-stu-id="ca06a-170">Lcslog.ldf</span></span></p></td>
<td><p><span data-ttu-id="ca06a-171">Fichier journal des transactions pour les données d’archivage</span><span class="sxs-lookup"><span data-stu-id="ca06a-171">Transaction log for Archiving data</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ca06a-p103">Cette rubrique fait référence au disque et au jeu RAID. Veuillez noter que dans la configuration des ressources SQL Server, on appelle disque un périphérique matériel unique. Un disque dur à deux partitions, la première comportant les fichiers journaux et l’autre comportant les fichiers de données, est différent de deux disques dont l’un est dédié aux fichiers journaux et l’autre aux fichiers de données.</span><span class="sxs-lookup"><span data-stu-id="ca06a-p103">In this topic, references are made to disk and to RAID set. Note that in the configuration of SQL Server resources, referring to a disk means a single hardware device. A hard disk drive with two partitions, one holding log files and the other partition holding data files, is not the same as two disks, each dedicated to either log or data files.</span></span>

<span data-ttu-id="ca06a-175">Concernant les jeux RAID, il existe diverses technologies RAID proposées par différents fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="ca06a-175">In reference to RAID sets, there are a number of different RAID technologies from various vendors.</span></span> <span data-ttu-id="ca06a-176">En outre, avec la prolifération des réseaux SAN (Storage Area Network), les jeux RAID dédiés à un seul système sont plus rares.</span><span class="sxs-lookup"><span data-stu-id="ca06a-176">And, with the proliferation of storage area networks (SAN), RAID sets dedicated to a single system are rarer.</span></span> <span data-ttu-id="ca06a-177">Vous devez consulter votre fournisseur de RAID ou SAN pour déterminer la configuration la plus adaptée à votre disposition de disque lors de la configuration des performances de SQL Server avec Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca06a-177">You should consult with your RAID or SAN vendor to determine what the best configuration is for your disk layout when configuring for SQL Server performance with Lync Server 2013.</span></span>

<span data-ttu-id="ca06a-178">Veuillez noter que tous les disques n’offrent pas les mêmes performances initialement.</span><span class="sxs-lookup"><span data-stu-id="ca06a-178">Note also that not all disk drives are created equally; some perform better than others.</span></span> <span data-ttu-id="ca06a-179">Les performances de disques provenant d’un même fabricant peuvent aussi varier en raison de la vitesse de rotation, de la taille du cache matériel et d’autres facteurs.</span><span class="sxs-lookup"><span data-stu-id="ca06a-179">Even drives from the same manufacturer can vary in performance because of rotational speed, hardware cache size, and other factors.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

