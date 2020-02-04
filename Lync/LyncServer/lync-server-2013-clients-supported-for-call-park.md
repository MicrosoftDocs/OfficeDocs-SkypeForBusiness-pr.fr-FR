---
title: 'Lync Server 2013 : Clients pris en charge pour le parcage d’appel'
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
ms.openlocfilehash: 52304a0241425a3b88c7f9419afa57f3d768fbb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756458"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="61684-102">Clients pris en charge pour le parcage d’appel dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61684-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61684-103">_**Dernière modification de la rubrique :** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="61684-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="61684-104">Cette section identifie les clients qui peuvent être utilisés pour parcr les appels et les clients qui peuvent être utilisés pour récupérer les appels en stationnement.</span><span class="sxs-lookup"><span data-stu-id="61684-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="61684-105">Clients pris en charge pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="61684-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="61684-106">Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), PSTN (réseau téléphonique commuté) ou mobile peuvent être parqués.</span><span class="sxs-lookup"><span data-stu-id="61684-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61684-p101">Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible.</span><span class="sxs-lookup"><span data-stu-id="61684-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="61684-109">Les clients suivants peuvent utiliser le parc d’appels pour les appels de parc :</span><span class="sxs-lookup"><span data-stu-id="61684-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="61684-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="61684-110">Lync 2013</span></span>

  - <span data-ttu-id="61684-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="61684-111">Lync 2010</span></span>

  - <span data-ttu-id="61684-112">Lync 2010 attendant</span><span class="sxs-lookup"><span data-stu-id="61684-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="61684-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="61684-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61684-114">Les téléphones mobiles ne peuvent pas utiliser le parc d’appels pour Park.</span><span class="sxs-lookup"><span data-stu-id="61684-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="61684-115">Clients pris en charge pour la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="61684-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="61684-p102">Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et PSTN ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="61684-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="61684-118">Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="61684-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="61684-119">Les clients suivants peuvent récupérer les appels qui sont au parking sur le parc d’appels :</span><span class="sxs-lookup"><span data-stu-id="61684-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="61684-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="61684-120">Lync 2013</span></span>

  - <span data-ttu-id="61684-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="61684-121">Lync 2010</span></span>

  - <span data-ttu-id="61684-122">Lync 2010 attendant</span><span class="sxs-lookup"><span data-stu-id="61684-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="61684-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="61684-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="61684-124">Téléphones de partie commune IP</span><span class="sxs-lookup"><span data-stu-id="61684-124">IP common area phones</span></span>

  - <span data-ttu-id="61684-125">Téléphones non IP connectés à l’infrastructure 2013 du serveur Lync, y compris les téléphones portables et les téléphones PBX (Private Branch Exchange)</span><span class="sxs-lookup"><span data-stu-id="61684-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

