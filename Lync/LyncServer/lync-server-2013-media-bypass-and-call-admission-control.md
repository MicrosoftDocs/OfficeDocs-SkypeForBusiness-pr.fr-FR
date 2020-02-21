---
title: 'Lync Server 2013 : déviation du trafic multimédia et contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10915a298fe2e50abdef09dc5acf92927a43cc65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="4e58c-102">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58c-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e58c-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="4e58c-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="4e58c-104">La déviation du trafic multimédia et le contrôle d’admission des appels (CAC) permettent de gérer le contrôle de la bande passante des appels.</span><span class="sxs-lookup"><span data-stu-id="4e58c-104">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media.</span></span> <span data-ttu-id="4e58c-105">La déviation du trafic multimédia facilite le flux de médias sur les liens bien connectés ; CAC gère le trafic sur les liens avec des contraintes de bande passante.</span><span class="sxs-lookup"><span data-stu-id="4e58c-105">Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints.</span></span> <span data-ttu-id="4e58c-106">Étant donné que la déviation du trafic multimédia et le contrôle d’admission des médias s’excluent mutuellement, vous devez être attentif à un lors de la planification de l’autre.</span><span class="sxs-lookup"><span data-stu-id="4e58c-106">Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other.</span></span> <span data-ttu-id="4e58c-107">Les combinaisons suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="4e58c-107">The following combinations are supported:</span></span>

  - <span data-ttu-id="4e58c-108">Le contrôle d’admission des médias et la déviation du trafic multimédia sont activés.</span><span class="sxs-lookup"><span data-stu-id="4e58c-108">CAC and Media Bypass are both enabled.</span></span> <span data-ttu-id="4e58c-109">La déviation du trafic multimédia doit être configurée pour **utiliser les informations de site et de région**.</span><span class="sxs-lookup"><span data-stu-id="4e58c-109">Media Bypass must be set to **Use Site and Region Information**.</span></span> <span data-ttu-id="4e58c-110">Ces informations sur les sites et les régions sont les mêmes que celles utilisées pour le contrôle d’admission des messages.</span><span class="sxs-lookup"><span data-stu-id="4e58c-110">This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="4e58c-111">Si vous activez le contrôle d’admission des droits, vous ne pouvez pas sélectionner **toujours Bypass**, et inversement, car les deux configurations s’excluent mutuellement.</span><span class="sxs-lookup"><span data-stu-id="4e58c-111">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive.</span></span> <span data-ttu-id="4e58c-112">Autrement dit, seule l’une des deux s’applique à un appel RTC donné.</span><span class="sxs-lookup"><span data-stu-id="4e58c-112">That is, only one of the two will apply to any given PSTN call.</span></span> <span data-ttu-id="4e58c-113">Tout d’abord, une vérification est effectuée afin de déterminer si la déviation du trafic multimédia s’applique à l’appel.</span><span class="sxs-lookup"><span data-stu-id="4e58c-113">First, a check is made to determine if media bypass applies to the call.</span></span> <span data-ttu-id="4e58c-114">Si c’est le cas, CAC n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="4e58c-114">If it does, then CAC is not used.</span></span> <span data-ttu-id="4e58c-115">Cela est logique, car si un appel est éligible pour contournement, il est par définition à l’aide d’une connexion où CAC n’est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4e58c-115">This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed.</span></span> <span data-ttu-id="4e58c-116">Si la contourner ne peut pas être appliquée à l’appel (autrement dit, si les ID de contournement du client et de la passerelle ne correspondent pas), le contrôle d’admission des appels est appliqué à l’appel.</span><span class="sxs-lookup"><span data-stu-id="4e58c-116">If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="4e58c-117">CAC non activé et contournement de média défini sur **toujours Bypass**.</span><span class="sxs-lookup"><span data-stu-id="4e58c-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="4e58c-118">Dans cette configuration, les sous-réseaux de client et de jonction sont mappés à un seul ID de contournement, qui est calculé par le système.</span><span class="sxs-lookup"><span data-stu-id="4e58c-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="4e58c-119">CAC non activé et contournement de média défini pour **utiliser les informations de site et de région**.</span><span class="sxs-lookup"><span data-stu-id="4e58c-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="4e58c-120">Lorsque les **informations de site et de région** sont activées, la détermination de contournement fonctionne de la même manière, que CAC soit activé ou non.</span><span class="sxs-lookup"><span data-stu-id="4e58c-120">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not.</span></span> <span data-ttu-id="4e58c-121">Autrement dit, pour tout appel RTC donné, le sous-réseau du client est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait.</span><span class="sxs-lookup"><span data-stu-id="4e58c-121">That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="4e58c-122">De même, le sous-réseau de la passerelle est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait.</span><span class="sxs-lookup"><span data-stu-id="4e58c-122">Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted.</span></span> <span data-ttu-id="4e58c-123">Uniquement si les deux ID de contournement sont identiques, le contournement se produit pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="4e58c-123">Only if the two bypass IDs are identical will bypass happen for the call.</span></span> <span data-ttu-id="4e58c-124">Si elles ne sont pas identiques, la déviation du trafic multimédia ne se produira pas.</span><span class="sxs-lookup"><span data-stu-id="4e58c-124">If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="4e58c-125">Même si le contrôle d’admission des appel est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et lien si vous voulez utiliser la configuration de site et de région pour contrôler la décision de contournement.</span><span class="sxs-lookup"><span data-stu-id="4e58c-125">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision.</span></span> <span data-ttu-id="4e58c-126">La valeur réelle de la contrainte de bande passante ou sa modalité n’a pas d’importance.</span><span class="sxs-lookup"><span data-stu-id="4e58c-126">The actual value of the bandwidth constraint or its modality doesn’t matter.</span></span> <span data-ttu-id="4e58c-127">Le but ultime est de faire en sorte que le système calcule automatiquement différents ID de contournement à associer à différents paramètres régionaux qui ne sont pas bien connectés.</span><span class="sxs-lookup"><span data-stu-id="4e58c-127">The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected.</span></span> <span data-ttu-id="4e58c-128">La définition d’une contrainte de bande passante par définition signifie qu’un lien n’est pas bien connecté.</span><span class="sxs-lookup"><span data-stu-id="4e58c-128">Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="4e58c-129">Le contrôle d’admission des médias est activé et la déviation du trafic multimédia n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="4e58c-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="4e58c-130">Cela ne s’applique que si toutes les passerelles et tous les PBX IP ne sont pas bien connectés ou ne répondent pas à d’autres exigences pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="4e58c-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="4e58c-131">Pour plus d’informations sur les conditions requises pour la déviation du trafic multimédia, voir [Technical Requirements for Media Bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4e58c-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4e58c-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e58c-132">See Also</span></span>


[<span data-ttu-id="4e58c-133">Vue d’ensemble de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58c-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="4e58c-134">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58c-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="4e58c-135">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e58c-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

