---
title: 'Lync Server 2013 : prise en charge du système d’exploitation serveur et outils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8773b4519497286d82d82b0da399fd66350919c0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="0c7ca-102">Serveur et outils pris en charge par le système d’exploitation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c7ca-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c7ca-103">_**Dernière modification de la rubrique :** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="0c7ca-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="0c7ca-104">Lync Server 2013 est disponible uniquement en 64 bits, ce qui nécessite le matériel 64 bits et les éditions 64 bits de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="0c7ca-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="0c7ca-105">Cela signifie que tous les rôles serveur et tous les ordinateurs exécutant les outils d’administration Lync Server 2013 exécutent un système d’exploitation de l’édition 64 bits.</span><span class="sxs-lookup"><span data-stu-id="0c7ca-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="0c7ca-106">Systèmes d’exploitation pour les rôles serveur</span><span class="sxs-lookup"><span data-stu-id="0c7ca-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="0c7ca-107">Lync Server 2013 prend en charge les versions 64 bits des systèmes d’exploitation suivants pour tous les rôles serveur dans Lync Server 2013 :</span><span class="sxs-lookup"><span data-stu-id="0c7ca-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="0c7ca-108">Le système d’exploitation standard Windows Server 2008 R2 avec Service Pack 1 (SP1) (requis) ou le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="0c7ca-109">Le système d’exploitation Windows Server 2008 R2 avec SP1 Enterprise (requis) ou le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="0c7ca-110">Le système d’exploitation Windows Server 2008 R2 avec SP1 Datacenter (requis) ou le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="0c7ca-111">Le système d’exploitation Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="0c7ca-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="0c7ca-112">Système d’exploitation Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="0c7ca-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="0c7ca-113">Les systèmes d’exploitation Windows Server 2012 R2 sont pris en charge avec les mises à jour cumulatives pour Lync Server 2013 : octobre 2013.</span><span class="sxs-lookup"><span data-stu-id="0c7ca-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="0c7ca-114">Lync Server 2013 n’est pas pris en charge sur les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="0c7ca-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="0c7ca-115">Option d'installation minimale de Windows Server 2008 R2 ou de Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0c7ca-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="0c7ca-116">Les systèmes d’exploitation Windows Web Server 2008 R2 ou Windows Web Server 2012.</span><span class="sxs-lookup"><span data-stu-id="0c7ca-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="0c7ca-117">Windows Server 2008 R2 HPC Edition ou Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="0c7ca-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="0c7ca-118">Systèmes d’exploitation supplémentaires pour les outils d’administration</span><span class="sxs-lookup"><span data-stu-id="0c7ca-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="0c7ca-119">Les outils d’administration Lync Server 2013 sont installés par défaut sur les serveurs exécutant Lync Server 2013, mais vous pouvez installer les outils d’administration séparément sur les autres ordinateurs exécutant les systèmes d’exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="0c7ca-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="0c7ca-120">Il s’agit notamment des versions 64 bits suivantes des systèmes d’exploitation suivants, en plus des éditions 64 bits des systèmes d’exploitation pris en charge pour le déploiement des rôles serveur (comme décrit dans la section précédente).</span><span class="sxs-lookup"><span data-stu-id="0c7ca-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="0c7ca-121">Le système d’exploitation Windows 7 avec le système d’exploitation SP1 (requis) ou le Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="0c7ca-122">Système d’exploitation Windows 8 ou Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="0c7ca-123">Système d’exploitation Windows 8,1 ou Service Pack le plus récent (recommandé)</span><span class="sxs-lookup"><span data-stu-id="0c7ca-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="0c7ca-124">Systèmes d’exploitation pour d’autres serveurs dans votre déploiement</span><span class="sxs-lookup"><span data-stu-id="0c7ca-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="0c7ca-125">Pour plus d’informations sur les conditions requises pour les serveurs principaux et les autres serveurs de base de données, voir [Database Software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ca-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="0c7ca-126">Pour plus d’informations sur les conditions requises pour les serveurs proxy inverses (pour le déploiement Edge), voir [prise en charge des services Internet (IIS) dans Lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ca-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="0c7ca-127">Pour plus d’informations sur les autres logiciels requis, y compris la prise en charge de l’infrastructure et de la virtualisation, voir les autres rubriques de la [prise en charge du logiciel et de l’infrastructure des serveurs dans Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="0c7ca-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

