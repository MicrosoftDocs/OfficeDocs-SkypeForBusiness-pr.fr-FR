---
title: 'Lync Server 2013 : affectation de l’étendue de la stratégie d’emplacement'
description: 'Lync Server 2013 : affectation de l’étendue de la stratégie d’emplacement.'
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
ms.openlocfilehash: 9f6c46150241b0b224e8005556c0f2f594d8bce5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563380"
---
# <a name="assigning-location-policy-scope-in-lync-server-2013"></a><span data-ttu-id="02fed-103">Affectation de l’étendue de la stratégie d’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02fed-103">Assigning location policy scope in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02fed-104">_**Dernière modification de la rubrique :** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="02fed-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="02fed-105">Comme pour les autres stratégies Lync Server, les stratégies d’emplacement peuvent être attribuées à plusieurs niveaux d’étendue : global, site et User.</span><span class="sxs-lookup"><span data-stu-id="02fed-105">As with other Lync Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="02fed-106">Toutefois, l’étendue des stratégies d’emplacement au niveau de l’utilisateur se comporte de manière légèrement différente de celle des autres stratégies Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02fed-106">However, the scope of user-level location policies behaves a bit differently than with other Lync Server policies.</span></span> <span data-ttu-id="02fed-107">Non seulement les stratégies d’emplacement par utilisateur peuvent être appliquées à des objets de point de terminaison (par exemple, les objets de contact des utilisateurs et du téléphone de partie commune), mais elles peuvent également être appliquées aux sites réseau Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02fed-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Lync Server network sites.</span></span> <span data-ttu-id="02fed-108">Les sites réseau sont des regroupements de sous-réseaux clients associés à un emplacement géographique (mais pas nécessairement tous les sous-réseaux dans un site central ou un site de succursale).</span><span class="sxs-lookup"><span data-stu-id="02fed-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="02fed-109">Tous les clients connectés aux sous-réseaux dans un site réseau utilisent automatiquement la stratégie d’emplacement affectée à ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="02fed-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="02fed-110">Dans les cas où une stratégie d’emplacement de niveau utilisateur est affectée à un utilisateur et à un site réseau, la stratégie d’emplacement de site réseau remplace les paramètres de stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02fed-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>

<span data-ttu-id="02fed-111">Une stratégie d’emplacement est affectée à chaque site réseau. Différentes valeurs d’utilisations PSTN, d’URI de notification et d’URI de conférence sont affectées à chaque stratégie.</span><span class="sxs-lookup"><span data-stu-id="02fed-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02fed-112">La raison associée à ce comportement d’étendue de stratégie particulière est que lorsqu’un utilisateur hébergé sur un pool dans un site de bureau visite un autre site et doit passer un appel d’urgence, les paramètres de routage d’appels E9-1-1 adaptés à ce réseau sont appliqués, indépendamment du pool ou du site auquel l’utilisateur est affecté.</span><span class="sxs-lookup"><span data-stu-id="02fed-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

