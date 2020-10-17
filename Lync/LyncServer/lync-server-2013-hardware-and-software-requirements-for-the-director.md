---
title: 'Lync Server 2013 : configuration matérielle et logicielle requise pour le directeur'
description: 'Lync Server 2013 : configuration matérielle et logicielle requise pour le directeur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dd868a3a566f1d89b4ada5a16695f8eb02b3b21
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552930"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a><span data-ttu-id="48c4c-103">Configuration matérielle et logicielle requise pour le directeur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48c4c-103">Hardware and software requirements for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48c4c-104">_**Dernière modification de la rubrique :** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="48c4c-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="48c4c-105">Cette section décrit la configuration matérielle et logicielle requise pour le directeur, ainsi que les scénarios de colocalisation pris en charge pour le directeur.</span><span class="sxs-lookup"><span data-stu-id="48c4c-105">This section details the hardware and software requirements for the Director, and the supported collocation scenarios for the Director.</span></span>

<div>

## <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="48c4c-106">Configuration matérielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="48c4c-106">Hardware Requirements for the Director</span></span>

<span data-ttu-id="48c4c-107">Le tableau suivant répertorie la configuration matérielle requise pour le directeur :</span><span class="sxs-lookup"><span data-stu-id="48c4c-107">The following table lists the hardware requirements for the Director:</span></span>

### <a name="hardware-requirements-for-the-director"></a><span data-ttu-id="48c4c-108">Configuration matérielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="48c4c-108">Hardware Requirements for the Director</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48c4c-109">Composant matériel</span><span class="sxs-lookup"><span data-stu-id="48c4c-109">Hardware component</span></span></th>
<th><span data-ttu-id="48c4c-110">Spécification minimale</span><span class="sxs-lookup"><span data-stu-id="48c4c-110">Minimum requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48c4c-111">UC</span><span class="sxs-lookup"><span data-stu-id="48c4c-111">CPU</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="48c4c-112">Processeur 64 bits, quadruple cœur 2,0 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="48c4c-112">64-bit processor, quad-core, 2.0 GHz or higher</span></span></p></li>
<li><p><span data-ttu-id="48c4c-113">Biprocesseur 64 bits, double cœur 2,0 GHz ou supérieur</span><span class="sxs-lookup"><span data-stu-id="48c4c-113">64-bit dual processor, dual-core, 2.0 GHz or higher</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48c4c-114">Mémoire</span><span class="sxs-lookup"><span data-stu-id="48c4c-114">Memory</span></span></p></td>
<td><p><span data-ttu-id="48c4c-115">4 gigaoctets (Go)</span><span class="sxs-lookup"><span data-stu-id="48c4c-115">4 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48c4c-116">Disque</span><span class="sxs-lookup"><span data-stu-id="48c4c-116">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="48c4c-117">Lecteur de disque dur (HDD) 10 000 tr/min</span><span class="sxs-lookup"><span data-stu-id="48c4c-117">10K RPM hard disk drive (HDD)</span></span></p></li>
<li><p><span data-ttu-id="48c4c-118">Disque SSD à hautes performances avec des performances supérieures ou égales à 10K tr/min (HDD)</span><span class="sxs-lookup"><span data-stu-id="48c4c-118">High-performance solid state drive (SSD) with performance equal to or better than 10K RPM HDD</span></span></p></li>
<li><p><span data-ttu-id="48c4c-119">2x disques RAID 10 (agrégés par bandes et en miroir) 15 000 tr/min pour les fichiers de données des bases de données</span><span class="sxs-lookup"><span data-stu-id="48c4c-119">2x RAID 10 (striped and mirrored) 15K RPM disks for database data files</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48c4c-120">Réseau</span><span class="sxs-lookup"><span data-stu-id="48c4c-120">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="48c4c-121">Cartes réseau Dual-port 1 gigabit par seconde (Gbps) (recommandé)</span><span class="sxs-lookup"><span data-stu-id="48c4c-121">Dual 1 gigabit per second (Gbps) network adapters (recommended)</span></span></p></li>
<li><p><span data-ttu-id="48c4c-122">Carte réseau d’un gigabit (prise en charge)</span><span class="sxs-lookup"><span data-stu-id="48c4c-122">Single 1 Gbps network adapter (supported)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a><span data-ttu-id="48c4c-123">Configuration logicielle requise pour le directeur</span><span class="sxs-lookup"><span data-stu-id="48c4c-123">Software Requirements for the Director</span></span>

<span data-ttu-id="48c4c-124">Le rôle directeur ne peut être déployé que sur des serveurs exécutant Lync Server 2013 Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="48c4c-124">The Director role can be deployed only on servers running Lync Server 2013 Enterprise Edition.</span></span>

<span data-ttu-id="48c4c-125">L’un des systèmes d’exploitation 64 bits suivants est requis pour les directeurs :</span><span class="sxs-lookup"><span data-stu-id="48c4c-125">One of the following 64-bit operating systems is required for the Directors:</span></span>

  - <span data-ttu-id="48c4c-126">Système d’exploitation Windows Server 2008 R2 Standard avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="48c4c-126">The Windows Server 2008 R2 Standard operating system with Service Pack 1</span></span>

  - <span data-ttu-id="48c4c-127">Système d’exploitation Windows Server 2008 R2 Enterprise avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="48c4c-127">The Windows Server 2008 R2 Enterprise operating system with Service Pack 1</span></span>

  - <span data-ttu-id="48c4c-128">Système d’exploitation Windows Server 2008 R2 Datacenter avec Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="48c4c-128">The Windows Server 2008 R2 Datacenter operating system with Service Pack 1</span></span>

  - <span data-ttu-id="48c4c-129">Le système d’exploitation Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="48c4c-129">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="48c4c-130">Système d’exploitation Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="48c4c-130">The Windows Server 2012 Datacenter operating system</span></span>

<span data-ttu-id="48c4c-131">Lync Server 2013 nécessite également l’installation des programmes et des mises à jour suivants, décrits dans la rubrique relative à la [prise en charge et aux exigences des serveurs supplémentaires dans Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48c4c-131">Lync Server 2013 also requires installation of the following programs and updates detailed in the topic [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="48c4c-132">Colocalisation prise en charge</span><span class="sxs-lookup"><span data-stu-id="48c4c-132">Supported Collocation</span></span>

<span data-ttu-id="48c4c-133">Le rôle serveur directeur ne peut pas être colocalisé avec un autre rôle serveur dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48c4c-133">The Director server role cannot be collocated with any other server role in Lync Server 2013.</span></span> <span data-ttu-id="48c4c-134">Toutefois, si vous ne déployez pas de directeur, les serveurs frontaux assumeront le rôle.</span><span class="sxs-lookup"><span data-stu-id="48c4c-134">However, if you do not deploy a Director, the Front End Servers will assume the role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

