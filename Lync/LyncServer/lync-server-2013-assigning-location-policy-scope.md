---
title: 'Lync Server 2013 : affectation de l’étendue de la stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning location policy scope
ms:assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205360(v=OCS.15)
ms:contentKeyID: 48185734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 395b8a4271338231b4c2c1927f7e40fb21a1cb14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="7ced7-102">Attribution de l’étendue de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ced7-102">Assigning location policy scope in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ced7-103">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="7ced7-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="7ced7-104">Comme avec d’autres stratégies serveur Lync, des stratégies d’emplacement peuvent être affectées à plusieurs niveaux d’étendue : global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7ced7-104">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="7ced7-105">Toutefois, l’étendue des stratégies d’emplacement au niveau utilisateur se comporte de manière légèrement différente de celle des autres stratégies serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="7ced7-105">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="7ced7-106">Les stratégies d’emplacement par utilisateur ne peuvent pas seulement être appliquées aux objets de point de terminaison (par exemple, les utilisateurs et les objets de contact de zone commune), ils peuvent également être appliqués aux sites réseau de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ced7-106">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="7ced7-107">Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale).</span><span class="sxs-lookup"><span data-stu-id="7ced7-107">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="7ced7-108">Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="7ced7-108">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="7ced7-109">Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7ced7-109">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="7ced7-110">Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="7ced7-110">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ced7-111">La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="7ced7-111">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

