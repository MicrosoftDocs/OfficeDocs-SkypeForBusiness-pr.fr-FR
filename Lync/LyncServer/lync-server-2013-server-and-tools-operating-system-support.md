---
title: 'Lync Server 2013 : Prise en charge du système d’exploitation pour le serveur et les outils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19ae4b69eb261a9d23d767dcd3847d8986847b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="c6c46-102">Prise en charge du système d’exploitation pour le serveur et les outils dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6c46-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6c46-103">_**Dernière modification de la rubrique:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="c6c46-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="c6c46-104">Lync Server 2013 est disponible uniquement en 64 bits, qui nécessite une application matérielle 64 bits et des éditions 64 bits de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="c6c46-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="c6c46-105">Cela signifie que tous les rôles serveur et ordinateurs exécutant les outils d’administration Lync Server 2013 exécutent un système d’exploitation 64-bit Edition.</span><span class="sxs-lookup"><span data-stu-id="c6c46-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="c6c46-106">Systèmes d’exploitation pour rôles de serveur</span><span class="sxs-lookup"><span data-stu-id="c6c46-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="c6c46-107">Lync Server 2013 prend en charge les éditions 64 bits des systèmes d’exploitation suivants pour tous les rôles de serveur dans Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c6c46-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="c6c46-108">Le système d’exploitation standard Windows Server 2008 R2 avec Service Pack 1 (SP1) standard (requis) ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c6c46-109">Système d’exploitation Windows Server 2008 R2 avec SP1 Enterprise (requis) ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c6c46-110">Système d’exploitation Windows Server 2008 R2 avec SP1 SP1 (requis) ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c6c46-111">Système d’exploitation Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="c6c46-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="c6c46-112">Système d’exploitation Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c6c46-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="c6c46-113">Les systèmes d’exploitation Windows Server 2012 R2 sont pris en charge avec les mises à jour cumulatives pour Lync Server 2013: octobre 2013.</span><span class="sxs-lookup"><span data-stu-id="c6c46-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="c6c46-114">Lync Server 2013 n’est pas pris en charge sur les éléments suivants:</span><span class="sxs-lookup"><span data-stu-id="c6c46-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="c6c46-115">Option d’installation du serveur principal de Windows Server 2008 R2 ou Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="c6c46-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="c6c46-116">Système d’exploitation Windows Web Server 2008 R2 ou Windows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="c6c46-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="c6c46-117">Windows Server 2008 R2 HPC Edition ou Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="c6c46-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="c6c46-118">Autres systèmes d’exploitation pour les outils d’administration</span><span class="sxs-lookup"><span data-stu-id="c6c46-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="c6c46-119">Les outils d’administration de Lync Server 2013 sont installés par défaut sur les serveurs exécutant Lync Server 2013, mais vous pouvez installer les outils d’administration séparément sur d’autres ordinateurs exécutant des systèmes d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="c6c46-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="c6c46-120">Il s’agit des versions 64 bits suivantes des systèmes d’exploitation suivants, en plus des éditions 64 bits des systèmes d’exploitation pris en charge pour le déploiement de rôles de serveur (comme décrit dans la section précédente).</span><span class="sxs-lookup"><span data-stu-id="c6c46-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="c6c46-121">Système d’exploitation Windows 7 avec le système d’exploitation SP1 (requis) ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c6c46-122">Le système d’exploitation Windows 8 ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="c6c46-123">Le système d’exploitation Windows 8,1 ou le dernier Service Pack (recommandé)</span><span class="sxs-lookup"><span data-stu-id="c6c46-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="c6c46-124">Systèmes d’exploitation pour d’autres serveurs dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="c6c46-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="c6c46-125">Pour plus d’informations sur la configuration requise pour les serveurs principaux et les autres serveurs de base de données, voir [prise en charge des logiciels de base de données dans Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="c6c46-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="c6c46-126">Pour plus d’informations sur la configuration requise pour les serveurs proxy inverse (pour le déploiement Edge), voir [prise en charge des services Internet dans Lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="c6c46-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="c6c46-127">Pour plus d’informations sur les configurations logicielles requises, y compris sur la prise en charge de l’infrastructure et de la virtualisation, voir les autres rubriques relatives à la [prise en charge des logiciels et de l’infrastructure de serveur dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="c6c46-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

