---
title: 'Lync Server 2013 : Configuration matérielle et logicielle requise pour le directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="c1b88-102">Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1b88-102">Hardware and software requirements for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1b88-103">_**Dernière modification de la rubrique:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="c1b88-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="c1b88-104">Cette section détaille les configurations matérielles et logicielles requises pour le directeur et les scénarios de colocalisation pris en charge pour le directeur.</span><span class="sxs-lookup"><span data-stu-id="c1b88-104">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="c1b88-105">Configuration matérielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="c1b88-105">Hardware Requirements for the Director</span></span>

<span data-ttu-id="c1b88-106">Le tableau suivant répertorie la configuration matérielle requise pour le directeur:</span><span class="sxs-lookup"><span data-stu-id="c1b88-106">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="c1b88-107">Configuration matérielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="c1b88-107">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c1b88-108">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="c1b88-108">Hardware component</span></span></th>
<th><span data-ttu-id="c1b88-109">Spécification minimale</span><span class="sxs-lookup"><span data-stu-id="c1b88-109">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c1b88-110">Processeur</span><span class="sxs-lookup"><span data-stu-id="c1b88-110">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c1b88-111">processeur 64 bits, quadruple cœur, 2,0 GHz ou version ultérieure</span><span class="sxs-lookup"><span data-stu-id="c1b88-111">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="c1b88-112">processeur double cœur, 2,0 GHz ou version ultérieure 64</span><span class="sxs-lookup"><span data-stu-id="c1b88-112">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1b88-113">Mémoire</span><span class="sxs-lookup"><span data-stu-id="c1b88-113">Memory</span></span></p></td>
<td><p><span data-ttu-id="c1b88-114">4 gigaoctets (Go)</span><span class="sxs-lookup"><span data-stu-id="c1b88-114">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c1b88-115">Disque</span><span class="sxs-lookup"><span data-stu-id="c1b88-115">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c1b88-116">disque dur (HDD) 10 000 tr/min</span><span class="sxs-lookup"><span data-stu-id="c1b88-116">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="c1b88-117">Disque SSD haute performance avec performances égale ou supérieure à 10 000 tr/min</span><span class="sxs-lookup"><span data-stu-id="c1b88-117">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="c1b88-118">2 RAID 10 (bandes et miroirs) pour les fichiers de données de base de données</span><span class="sxs-lookup"><span data-stu-id="c1b88-118">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c1b88-119">Réseau</span><span class="sxs-lookup"><span data-stu-id="c1b88-119">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c1b88-120">2 cartes réseau 1 Gbit/s (Gbps)</span><span class="sxs-lookup"><span data-stu-id="c1b88-120">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="c1b88-121">Carte réseau 1 Gbps unique (prise en charge)</span><span class="sxs-lookup"><span data-stu-id="c1b88-121">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="c1b88-122">Configuration logicielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="c1b88-122">Software Requirements for the Director</span></span>

<span data-ttu-id="c1b88-123">Le rôle directeur peut être déployé uniquement sur les serveurs exécutant Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="c1b88-123">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="c1b88-124">L’un des systèmes d’exploitation 64 bits suivants est requis pour les directeurs:</span><span class="sxs-lookup"><span data-stu-id="c1b88-124">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="c1b88-125">Système d’exploitation Windows Server 2008 R2 Standard avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c1b88-125">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c1b88-126">Système d’exploitation Windows Server 2008 R2 entreprise avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c1b88-126">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c1b88-127">Système d’exploitation Windows Server 2008 R2 Datacenter avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="c1b88-127">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="c1b88-128">Système d’exploitation Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="c1b88-128">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="c1b88-129">Système d’exploitation Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c1b88-129">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="c1b88-130">Lync Server 2013 nécessite également l’installation des mises à jour et des programmes suivants sur le sujet du [support technique supplémentaire et des exigences de Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1b88-130">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="c1b88-131">Colocalisation prises en charge</span><span class="sxs-lookup"><span data-stu-id="c1b88-131">Supported Collocation</span></span>

<span data-ttu-id="c1b88-132">Le rôle serveur Director ne peut pas être localisé avec un autre rôle serveur dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1b88-132">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="c1b88-133">Toutefois, si vous ne déployez pas de réalisateur, le rôle serveur frontal sera supposé.</span><span class="sxs-lookup"><span data-stu-id="c1b88-133">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

