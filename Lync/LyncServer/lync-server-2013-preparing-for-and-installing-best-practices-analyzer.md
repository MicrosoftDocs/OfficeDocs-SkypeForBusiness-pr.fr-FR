---
title: 'Lync Server 2013 : préparation et installation de Best Practices Analyzer'
description: 'Lync Server 2013 : préparation et installation de Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 005c5ac372a3564e74af549832830ebae899e9d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549930"
---
# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="b7540-103">Préparation et installation de Best Practices Analyzer dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7540-103">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7540-104">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="b7540-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="b7540-105">Vous devez être connecté en tant que membre du groupe Administrateurs pour pouvoir effectuer les tâches qui sont décrites dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="b7540-105">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="b7540-106">Configuration requise pour l’installation de l’outil Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="b7540-106">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="b7540-107">Pour exécuter Lync Server 2013, Best Practices Analyzer pour analyser votre environnement, l’ordinateur doit exécuter une édition 64 bits de l’un des systèmes d’exploitation suivants :</span><span class="sxs-lookup"><span data-stu-id="b7540-107">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="b7540-108">Système d’exploitation Windows Server 2008 R2 avec Service Pack 1 (SP1) standard</span><span class="sxs-lookup"><span data-stu-id="b7540-108">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="b7540-109">Système d’exploitation Windows Server 2008 R2 avec SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7540-109">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="b7540-110">Système d’exploitation Windows Server 2008 R2 avec SP1 Datacenter</span><span class="sxs-lookup"><span data-stu-id="b7540-110">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="b7540-111">Système d’exploitation Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="b7540-111">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="b7540-112">Système d’exploitation Windows Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="b7540-112">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="b7540-113">Système d’exploitation Windows Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7540-113">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="b7540-114">Système d’exploitation Windows Server 2012 R2 Datacenter</span><span class="sxs-lookup"><span data-stu-id="b7540-114">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="b7540-115">Système d’exploitation Windows Server 2012 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="b7540-115">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="b7540-116">Système d’exploitation Windows Server 2012 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b7540-116">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="b7540-117">Système d’exploitation Windows 8</span><span class="sxs-lookup"><span data-stu-id="b7540-117">Windows 8 operating system</span></span>

  - <span data-ttu-id="b7540-118">système d’exploitation Windows 7</span><span class="sxs-lookup"><span data-stu-id="b7540-118">Windows 7 operating system</span></span>

<span data-ttu-id="b7540-119">L’ordinateur doit également exécuter ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b7540-119">The computer must also be running the following:</span></span>

  - <span data-ttu-id="b7540-120">Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="b7540-120">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="b7540-121">Pour Lync Server 2013, vous devez installer manuellement l’édition 64 bits de Microsoft .NET Framework 4,5 sur le serveur avant d’installer Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7540-121">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="b7540-122">Lync Server 2013, composants principaux.</span><span class="sxs-lookup"><span data-stu-id="b7540-122">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="b7540-123">Package de compatibilité descendante WMI.</span><span class="sxs-lookup"><span data-stu-id="b7540-123">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="b7540-124">Pour plus d’informations, consultez la rubrique [installer WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) dans la documentation de migration.</span><span class="sxs-lookup"><span data-stu-id="b7540-124">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="b7540-125">Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="b7540-125">Windows PowerShell 3.0.</span></span> <span data-ttu-id="b7540-126">Pour plus d’informations, voir [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="b7540-126">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="b7540-127">Vous pouvez installer Best Practices Analyzer sur des ordinateurs avec un système d’exploitation pris en charge qui n’exécute pas Lync Server 2013, les composants principaux ou le package de compatibilité descendante WMI, mais vous pouvez utiliser Best Practices Analyzer sur ces ordinateurs uniquement pour afficher des rapports, et non pour exécuter des analyses.</span><span class="sxs-lookup"><span data-stu-id="b7540-127">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="b7540-128">Choix d’un ordinateur pour l’installation</span><span class="sxs-lookup"><span data-stu-id="b7540-128">Choosing a Computer for Installation</span></span>

<span data-ttu-id="b7540-129">Nous vous recommandons d’installer Lync Server 2013, Best Practices Analyzer sur un ordinateur dédié à la gestion de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7540-129">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="b7540-130">Vous pouvez installer l’outil sur un serveur exécutant Lync Server 2013 ou un ordinateur d’administration exécutant les outils d’administration Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7540-130">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="b7540-131">Si vous installez l’outil sur un serveur qui exécute Lync Server, nous vous recommandons d’utiliser l’outil pour analyser uniquement ce serveur.</span><span class="sxs-lookup"><span data-stu-id="b7540-131">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="b7540-132">Installation de l’outil Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="b7540-132">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="b7540-133">Vous pouvez télécharger Best Practices Analyzer pour Lync Server 2013 à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539) .</span><span class="sxs-lookup"><span data-stu-id="b7540-133">You can download the Best Practices Analyzer for Lync Server 2013 at [https://go.microsoft.com/fwlink/p/?linkId=266539](https://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="b7540-134">Pour installer l’outil Best Practices Analyzer, démarrez l’exécution du fichier d’installation Microsoft RtcBPA.msi sur l’ordinateur où vous souhaitez installer l’outil, puis suivez les instructions à l’écran.</span><span class="sxs-lookup"><span data-stu-id="b7540-134">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="b7540-135">L’emplacement par défaut pour l’installation des fichiers programme est \<system drive\> \\ Program Files \\ Lync Server 2013 \\ BPA.</span><span class="sxs-lookup"><span data-stu-id="b7540-135">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

