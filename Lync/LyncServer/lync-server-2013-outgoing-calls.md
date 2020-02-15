---
title: 'Lync Server 2013 : appels sortants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="81e96-102">Appels sortants dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e96-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81e96-103">_**Dernière modification de la rubrique :** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="81e96-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="81e96-104">Le routage des appels sortants d’utilisateurs activés pour le routage géodépendant est affecté par l’emplacement réseau du point de terminaison de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="81e96-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="81e96-105">Le tableau suivant montre comment le routage géodépendant affecte le routage des appels sortants en fonction de l’emplacement du point de terminaison de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="81e96-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="81e96-106">Appelant passant un appel sortant vers le réseau téléphonique commuté (RTC)</span><span class="sxs-lookup"><span data-stu-id="81e96-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="81e96-107">Point de terminaison d’utilisateur situé dans un site réseau activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="81e96-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="81e96-108">Point de terminaison d’utilisateur situé dans un site réseau inconnu ou non activé pour le routage géodépendant</span><span class="sxs-lookup"><span data-stu-id="81e96-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="81e96-109">Autorisation des appels sortants</span><span class="sxs-lookup"><span data-stu-id="81e96-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="81e96-110">L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="81e96-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="81e96-111">L’appel est autorisé en fonction de la stratégie de voix de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="81e96-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="81e96-112">Routage des appels sortants</span><span class="sxs-lookup"><span data-stu-id="81e96-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="81e96-113">L’appel est acheminé en fonction de la stratégie de routage des communications vocales du site réseau</span><span class="sxs-lookup"><span data-stu-id="81e96-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="81e96-114">L’appel est acheminé en fonction de la stratégie de voix de l’utilisateur et uniquement via des jonctions non activées pour le routage géodépendant (le cas échéant)</span><span class="sxs-lookup"><span data-stu-id="81e96-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="81e96-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81e96-115">See Also</span></span>


[<span data-ttu-id="81e96-116">Scénarios de routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="81e96-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

