---
title: 'Lync Server 2013 : nouvelles fonctionnalités de virtualisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New virtualization features
ms:assetid: edeb2c41-765e-47b8-8a2b-7a7ce09de2ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721926(v=OCS.15)
ms:contentKeyID: 49733861
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28932ba130d7dd67a81c3a4f4f9ab16c1bbbccac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-virtualization-features-in-lync-server-2013"></a><span data-ttu-id="22e00-102">Nouvelles fonctionnalités de virtualisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22e00-102">New virtualization features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e00-103">_**Dernière modification de la rubrique :** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="22e00-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="22e00-104">Lync Server 2013 prend en charge la virtualisation sur Windows Server 2012, Windows Server 2012 R2 et Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="22e00-104">Lync Server 2013 supports virtualization on both Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span> <span data-ttu-id="22e00-105">La prise en charge sur Windows Server 2012 et Windows Server 2012 R2 inclut la prise en charge des fonctionnalités de virtualisation d’e/s racines uniques (SR-IOV).</span><span class="sxs-lookup"><span data-stu-id="22e00-105">Support on Windows Server 2012 and Windows Server 2012 R2 includes support for the Single Root I/O Virtualization (SR-IOV) capabilities.</span></span> <span data-ttu-id="22e00-106">Avec SR-IOV, la fonction virtuelle d’une carte réseau physique est attribuée directement à une machine virtuelle.</span><span class="sxs-lookup"><span data-stu-id="22e00-106">With SR-IOV, the virtual function of a physical network adapter is assigned directly to a virtual machine.</span></span> <span data-ttu-id="22e00-107">Cela permet d’augmenter le débit réseau et de réduire la latence du réseau tout en réduisant la charge de l’UC hôte requise pour le traitement du trafic réseau.</span><span class="sxs-lookup"><span data-stu-id="22e00-107">This increases network throughput and reduces network latency while also reducing the host CPU overhead that is required for processing network traffic.</span></span> <span data-ttu-id="22e00-108">Pour tirer parti de SR-IOV, vous devez utiliser un serveur hôte qui a le BIOS qui prend en charge SR-IOV, ainsi que les cartes réseau qui prennent en charge SR-IOV.</span><span class="sxs-lookup"><span data-stu-id="22e00-108">To take advantage of SR-IOV, you must use a host server which has BIOS which supports SR-IOV, as well as use network adapters that support SR-IOV.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

