---
title: 'Lync Server 2013 : clients pris en charge pour le parcage d’appel'
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
ms.openlocfilehash: ee3916e74a68121b027061429bacb44e2dafacdb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f48fc-102">Clients pris en charge pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f48fc-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f48fc-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="f48fc-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="f48fc-104">Cette section identifie les clients qu’il est possible d’utiliser pour le parcage des appels et ceux que vous pouvez utiliser pour récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="f48fc-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="f48fc-105">Clients pris en charge pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="f48fc-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="f48fc-106">Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), RTC (réseau téléphonique commuté) ou mobile peuvent être parqués.</span><span class="sxs-lookup"><span data-stu-id="f48fc-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f48fc-p101">Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible.</span><span class="sxs-lookup"><span data-stu-id="f48fc-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="f48fc-109">Les clients suivants peuvent utiliser les appels de parcage d’appel vers parcage :</span><span class="sxs-lookup"><span data-stu-id="f48fc-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="f48fc-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f48fc-110">Lync 2013</span></span>

  - <span data-ttu-id="f48fc-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f48fc-111">Lync 2010</span></span>

  - <span data-ttu-id="f48fc-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f48fc-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="f48fc-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f48fc-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f48fc-114">Les téléphones mobiles ne peuvent pas utiliser le parcage d’appel vers des appels Park.</span><span class="sxs-lookup"><span data-stu-id="f48fc-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="f48fc-115">Clients pris en charge pour la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="f48fc-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="f48fc-p102">Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et RTC ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="f48fc-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="f48fc-118">Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="f48fc-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="f48fc-119">Les clients suivants peuvent récupérer des appels parqués sur le parcage d’appel :</span><span class="sxs-lookup"><span data-stu-id="f48fc-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="f48fc-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="f48fc-120">Lync 2013</span></span>

  - <span data-ttu-id="f48fc-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="f48fc-121">Lync 2010</span></span>

  - <span data-ttu-id="f48fc-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="f48fc-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="f48fc-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="f48fc-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="f48fc-124">Téléphones de partie commune IP</span><span class="sxs-lookup"><span data-stu-id="f48fc-124">IP common area phones</span></span>

  - <span data-ttu-id="f48fc-125">Téléphones non IP connectés à l’infrastructure Lync Server 2013, y compris les téléphones de partie commune et les téléphones PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="f48fc-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

