---
title: Server Hardware Platforms pour Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a><span data-ttu-id="97912-102">Server Hardware Platforms pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97912-102">Server hardware platforms for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97912-103">_**Dernière modification de la rubrique :** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="97912-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="97912-104">Les rôles serveur Lync Server 2013 et les ordinateurs exécutant des outils d’administration de Lync Server nécessitent 64 bits.</span><span class="sxs-lookup"><span data-stu-id="97912-104">Lync Server 2013 server roles and computers running Lync Server administrative tools require 64-bit hardware.</span></span>

<span data-ttu-id="97912-105">Le matériel spécifique utilisé pour le déploiement de Lync Server 2013 peut varier en fonction de la taille et de l’utilisation requise.</span><span class="sxs-lookup"><span data-stu-id="97912-105">The specific hardware used for Lync Server 2013 deployment can vary, depending on size and usage requirements.</span></span> <span data-ttu-id="97912-106">Cette section décrit le matériel recommandé.</span><span class="sxs-lookup"><span data-stu-id="97912-106">This section describes the recommended hardware.</span></span> <span data-ttu-id="97912-107">Même s’il s’agit de recommandations, et non d’impératifs, l’utilisation de matériel ne respectant pas ces recommandations peut entraîner des baisses de performance significatives et d’autres problèmes.</span><span class="sxs-lookup"><span data-stu-id="97912-107">Although these are recommendations, not requirements, using hardware that does not meet these recommendations may result in significant performance issues and other issues.</span></span>

<div>

## <a name="recommended-hardware-platform"></a><span data-ttu-id="97912-108">Plateforme matérielle recommandée</span><span class="sxs-lookup"><span data-stu-id="97912-108">Recommended Hardware Platform</span></span>

<span data-ttu-id="97912-109">Pour des performances optimales, nous vous recommandons d’exécuter Lync Server sur les serveurs dotés du matériel qui répond aux conditions énoncées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="97912-109">For best performance, we recommend that you run Lync Server on servers with hardware that meets the requirements in the following table.</span></span> <span data-ttu-id="97912-110">Si vous utilisez un matériel moins puissant, vous pouvez rencontrer des problèmes de fonctionnement ou des performances médiocres.</span><span class="sxs-lookup"><span data-stu-id="97912-110">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="97912-111">Notez que la configuration matérielle requise est supérieure à celle des versions précédentes de Lync Server, principalement par le biais de Lync Server 2013, tous les serveurs frontaux exécutant SQL Server.</span><span class="sxs-lookup"><span data-stu-id="97912-111">Note that these hardware requirements are higher than those of previous versions of Lync Server, primarily because in Lync Server 2013, all Front End Servers run SQL Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97912-112">L’Association de cartes réseau est prise en charge et doit être transparente pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97912-112">NIC teaming is supported and should be transparent to Lync Server.</span></span> <span data-ttu-id="97912-113">Pour plus d’informations, reportez-vous à <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server ou Lync Server et à l’équipe des cartes réseau</A>.</span><span class="sxs-lookup"><span data-stu-id="97912-113">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server or Lync Server and network adapter teaming</A>.</span></span>



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a><span data-ttu-id="97912-114">Matériel recommandé pour les serveurs frontaux, les serveurs principaux, les serveurs Standard Edition Server, les serveurs de conversation permanente, le magasin de conversation permanente et le magasin de conformité de conversation permanente (rôles Serveur principal pour le serveur de conversation permanente)</span><span class="sxs-lookup"><span data-stu-id="97912-114">Recommended Hardware for Front End Servers, Back End Servers, Standard Edition Servers, Persistent Chat Servers, and Persistent Chat Store and Persistent Chat Compliance Store (Back End Server Roles for Persistent Chat Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97912-115">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="97912-115">Hardware component</span></span></th>
<th><span data-ttu-id="97912-116">Recommandation</span><span class="sxs-lookup"><span data-stu-id="97912-116">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97912-117">Processeur</span><span class="sxs-lookup"><span data-stu-id="97912-117">CPU</span></span></p></td>
<td><p><span data-ttu-id="97912-118">Biprocesseur 64 bits, six cœurs, 2,26 GHz ou supérieur.</span><span class="sxs-lookup"><span data-stu-id="97912-118">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="97912-119">Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97912-119">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97912-120">Mémoire</span><span class="sxs-lookup"><span data-stu-id="97912-120">Memory</span></span></p></td>
<td><p><span data-ttu-id="97912-121">32 giga-octets (Go).</span><span class="sxs-lookup"><span data-stu-id="97912-121">32 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97912-122">Disque</span><span class="sxs-lookup"><span data-stu-id="97912-122">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97912-123">8 disques durs ou plus 10 000 tr/min avec au moins 72 Go d’espace disponible. </span><span class="sxs-lookup"><span data-stu-id="97912-123">8 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="97912-124">Deux de ces disques doivent utiliser RAID 1 et six doivent utiliser RAID 10.</span><span class="sxs-lookup"><span data-stu-id="97912-124">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="97912-125">-Ou</span><span class="sxs-lookup"><span data-stu-id="97912-125">- OR -</span></span></p></li>
<li><p><span data-ttu-id="97912-126">Disques SSD (Solid State Drive) qui fournissent des performances similaires à 8 disques durs mécaniques 10 000 tr/min.</span><span class="sxs-lookup"><span data-stu-id="97912-126">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97912-127">Réseau</span><span class="sxs-lookup"><span data-stu-id="97912-127">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97912-128">1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP).</span><span class="sxs-lookup"><span data-stu-id="97912-128">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97912-129">Les configurations à double ou à hébergement multiple ne sont pas prises en charge pour les serveurs frontaux, serveurs dorsaux, serveurs Standard Edition et serveurs de chat permanent.</span><span class="sxs-lookup"><span data-stu-id="97912-129">Dual or multi-homed configurations are not supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers.</span></span><BR><span data-ttu-id="97912-130">ILO/DRAC/etc. connexions non exposées au système d’exploitation et permettant de surveiller et de gérer le matériel du serveur ne constituent pas un serveur multi-résident et sont donc pris en charge.</span><span class="sxs-lookup"><span data-stu-id="97912-130">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a><span data-ttu-id="97912-131">Matériel recommandé pour les serveurs Edge, les serveurs de médiation autonomes et les directeurs</span><span class="sxs-lookup"><span data-stu-id="97912-131">Recommended Hardware for Edge Servers, Standalone Mediation Servers, and Directors</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97912-132">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="97912-132">Hardware component</span></span></th>
<th><span data-ttu-id="97912-133">Recommandation</span><span class="sxs-lookup"><span data-stu-id="97912-133">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97912-134">Processeur</span><span class="sxs-lookup"><span data-stu-id="97912-134">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97912-135">processeur double cœur, cadencé à 4 bits, 2,0 gigahertz (GHz) ou version ultérieure. 64</span><span class="sxs-lookup"><span data-stu-id="97912-135">64-bit dual processor, quad-core, 2.0 gigahertz (GHz) or higher.</span></span></p>
<p><span data-ttu-id="97912-136">-Ou</span><span class="sxs-lookup"><span data-stu-id="97912-136">- OR -</span></span></p></li>
<li><p><span data-ttu-id="97912-137">processeur à 4 ou 4 processeurs cadencé à 4 ou 4 processeurs, 2,0 GHz ou supérieur. 64</span><span class="sxs-lookup"><span data-stu-id="97912-137">64-bit 4-way processor, dual-core, 2.0 GHz or higher.</span></span></p></li>
</ul>
<p><span data-ttu-id="97912-138">Les processeurs Intel Itanium ne sont pas pris en charge pour les rôles serveur Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97912-138">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97912-139">Mémoire</span><span class="sxs-lookup"><span data-stu-id="97912-139">Memory</span></span></p></td>
<td><p><span data-ttu-id="97912-140">16 gigaoctets (Go).</span><span class="sxs-lookup"><span data-stu-id="97912-140">16 gigabytes (GB).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97912-141">Disque</span><span class="sxs-lookup"><span data-stu-id="97912-141">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97912-142">4 Mo ou davantage de disques durs 10 000 RPM dotés d’au moins 72 Go d’espace libre sur le disque dur.</span><span class="sxs-lookup"><span data-stu-id="97912-142">4 or more 10,000 RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="97912-143">La configuration des disques doit être de type 2x RAID 1.</span><span class="sxs-lookup"><span data-stu-id="97912-143">The disks should be in a 2x RAID 1 configuration.</span></span></p>
<p><span data-ttu-id="97912-144">-Ou</span><span class="sxs-lookup"><span data-stu-id="97912-144">- OR -</span></span></p></li>
<li><p><span data-ttu-id="97912-145">Disques SSD (Solid State Drive) qui fournissent des performances similaires à 4 disques durs mécaniques 10 000 tr/min. </span><span class="sxs-lookup"><span data-stu-id="97912-145">Solid state drives (SSDs) which provide performance similar to 4 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97912-146">Réseau</span><span class="sxs-lookup"><span data-stu-id="97912-146">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97912-147">1 carte réseau double port, 1 Gbits/s ou supérieur (2 recommandé, ce qui nécessite l’association à une seule adresse MAC et une seule adresse IP).</span><span class="sxs-lookup"><span data-stu-id="97912-147">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address).</span></span> <span data-ttu-id="97912-148">2 interfaces réseau sont requises sur les serveurs Edge et sont prises en charge sur les serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="97912-148">2 network interfaces are required on Edge Servers, and are supported on standalone Mediation Servers.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="97912-149">Les configurations à double ou à hébergement multiple ne sont pas prises en charge pour les directeurs.</span><span class="sxs-lookup"><span data-stu-id="97912-149">Dual or multi-homed configurations are not supported for Directors.</span></span><BR><span data-ttu-id="97912-150">ILO/DRAC/etc. connexions non exposées au système d’exploitation et permettant de surveiller et de gérer le matériel du serveur ne constituent pas un serveur multi-résident et sont donc pris en charge.</span><span class="sxs-lookup"><span data-stu-id="97912-150">ILO/DRAC/etc. connections not exposed to the Operating System and used to monitor and manage the server hardware do not constitute a multi-homed server and thus are supported.</span></span>


</div>
<p><span data-ttu-id="97912-151">Les serveurs Edge requièrent deux interfaces réseau qui sont des cartes réseau à double-port, 1 Gbit/s ou une version ultérieure (ou deux cartes réseau couplées, pour un total de quatre, chaque paire étant associée à une adresse MAC unique et une seule adresse IP, pour un total de deux paires).</span><span class="sxs-lookup"><span data-stu-id="97912-151">Edge Servers will require two network interfaces that are dual-port network adapters, 1 Gbps or higher (or two paired network adapters, for a total of four, each pair being teamed with a single MAC address and a single IP address, for a total of two pairs).</span></span></p>
<p><span data-ttu-id="97912-152">L’installation de cartes d’interface réseau supplémentaires (NIC) pour permettre la configuration d’une adresse IP RTC spécifique est prise en charge sur les serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="97912-152">Installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported on standalone Mediation Servers.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

