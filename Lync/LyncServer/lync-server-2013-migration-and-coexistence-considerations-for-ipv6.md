---
title: 'Lync Server 2013 : Remarques sur la migration et la coexistence pour IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8adf81df14d5c87eb2b54b63d9a58fc1b6f5b97e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="232a6-102">Remarques sur la migration et la coexistence pour IPv6 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="232a6-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="232a6-103">_**Dernière modification de la rubrique:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="232a6-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="232a6-104">Le protocole IP version 6 (IPv6) n’est pas pris en charge sur Lync Server 2010 ou Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="232a6-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="232a6-105">Dans le cadre de la phase de test, vous pouvez tester le coexistence de Lync Server 2010 et de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="232a6-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="232a6-106">Nous vous recommandons d’effectuer la mise à niveau de tous les pools pour un site central vers Lync Server 2013 avant d’activer le protocole IPv6 (réseau à double pile) pour tous les pools.</span><span class="sxs-lookup"><span data-stu-id="232a6-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="232a6-107">Si vous devez configurer un pool uniquement pour IPv6, nous recommandons que vous configuriez un pool IPv6 uniquement dans votre environnement de laboratoire pour le test.</span><span class="sxs-lookup"><span data-stu-id="232a6-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="232a6-108">Les scénarios suivants sont pris en charge pendant la migration et la coexistence :</span><span class="sxs-lookup"><span data-stu-id="232a6-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="232a6-109">Lync Server 2013, Lync Server 2010 et les pools Office Communications Server 2007 R2 en mode IPv4, coexistence de Lync Server 2013 en mode double pile.</span><span class="sxs-lookup"><span data-stu-id="232a6-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="232a6-110">Pool Lync Server 2013 en mode IPv6 uniquement, si le pool IPv6 uniquement est silo.</span><span class="sxs-lookup"><span data-stu-id="232a6-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

