---
title: 'Lync Server 2013 : clients pris en charge pour le parcage d’appel'
description: 'Lync Server 2013 : clients pris en charge pour le parcage d’appel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543490"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="5f049-103">Clients pris en charge pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f049-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f049-104">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="5f049-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="5f049-105">Cette section identifie les clients qu’il est possible d’utiliser pour le parcage des appels et ceux que vous pouvez utiliser pour récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="5f049-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="5f049-106">Clients pris en charge pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="5f049-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="5f049-107">Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), RTC (réseau téléphonique commuté) ou mobile peuvent être parqués.</span><span class="sxs-lookup"><span data-stu-id="5f049-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f049-p101">Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible.</span><span class="sxs-lookup"><span data-stu-id="5f049-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="5f049-110">Les clients suivants peuvent utiliser les appels de parcage d’appel vers parcage :</span><span class="sxs-lookup"><span data-stu-id="5f049-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="5f049-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5f049-111">Lync 2013</span></span>

  - <span data-ttu-id="5f049-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5f049-112">Lync 2010</span></span>

  - <span data-ttu-id="5f049-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="5f049-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="5f049-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5f049-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f049-115">Les téléphones mobiles ne peuvent pas utiliser le parcage d’appel vers des appels Park.</span><span class="sxs-lookup"><span data-stu-id="5f049-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="5f049-116">Clients pris en charge pour la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="5f049-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="5f049-p102">Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et RTC ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="5f049-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="5f049-119">Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="5f049-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="5f049-120">Les clients suivants peuvent récupérer des appels parqués sur le parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="5f049-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="5f049-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5f049-121">Lync 2013</span></span>

  - <span data-ttu-id="5f049-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5f049-122">Lync 2010</span></span>

  - <span data-ttu-id="5f049-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="5f049-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="5f049-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5f049-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="5f049-125">Téléphones de partie commune IP</span><span class="sxs-lookup"><span data-stu-id="5f049-125">IP common area phones</span></span>

  - <span data-ttu-id="5f049-126">Téléphones non IP connectés à l’infrastructure Lync Server 2013, y compris les téléphones de partie commune et les téléphones PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="5f049-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

