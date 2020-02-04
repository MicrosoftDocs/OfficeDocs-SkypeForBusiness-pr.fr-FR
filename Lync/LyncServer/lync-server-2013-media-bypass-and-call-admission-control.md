---
title: 'Lync Server 2013 : Déviation du trafic multimédia et contrôle d’admission des appels'
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
ms.openlocfilehash: 2034a58f686d62ab8e755c0e2c624a9a8994961e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="6e473-102">Déviation du trafic multimédia et contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e473-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e473-103">_**Dernière modification de la rubrique :** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6e473-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6e473-p101">La déviation du trafic multimédia et le contrôle d’admission des appels fonctionnent conjointement pour gérer le contrôle de la bande passante pour le trafic des données multimédias pendant les appels. La déviation du trafic multimédia facilite le flux des données multimédias sur des liaisons correctement connectées ; le contrôle d’admission des appels, quant à lui, gère le trafic sur les liaisons avec des restrictions de bande passante. Étant donné que la déviation du trafic multimédia et le contrôle d’admission des appels s’excluent mutuellement, vous devez tenir compte de l’un lorsque vous planifiez l’utilisation de l’autre. Les combinaisons suivantes sont prises en charge :</span><span class="sxs-lookup"><span data-stu-id="6e473-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="6e473-p102">La déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés. La déviation du trafic multimédia doit être définie sur **Utiliser les informations de site et de région**. Ces informations sont les mêmes que celles utilisées pour le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="6e473-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="6e473-p103">Si vous activez le contrôle d’admission des appels, vous ne pouvez pas sélectionner **Toujours ignorer** et inversement, car les deux configurations s’excluent mutuellement. C’est-à-dire, qu’une seule configuration s’appliquera à un appel PSTN donné. D’abord, une vérification a lieu pour déterminer si la déviation du trafic multimédia s’applique à l’appel. Si c’est le cas, le contrôle d’admission des appels n’est pas utilisé. Cela est logique, car si la déviation du trafic multimédia peut être appliquée à l’appel, celui-ci utilise par définition une connexion où le contrôle d’admission des appels n’est pas nécessaire. En revanche, si le contournement ne peut pas être appliqué à l’appel (c’est-à-dire, si les ID de contournement du client et de la passerelle ne correspondent pas), alors le contrôle d’admission des appels est appliqué à l’appel.</span><span class="sxs-lookup"><span data-stu-id="6e473-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="6e473-117">Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Toujours ignorer**.</span><span class="sxs-lookup"><span data-stu-id="6e473-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="6e473-118">Dans cette configuration, les sous-réseaux du client et de la jonction sont mappés à un seul ID de contournement, qui est calculé par le système.</span><span class="sxs-lookup"><span data-stu-id="6e473-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="6e473-119">Contrôle d’admission des appels non activé et déviation du trafic multimédia définie sur **Utiliser les informations de site et de région**.</span><span class="sxs-lookup"><span data-stu-id="6e473-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="6e473-p104">Lorsque **Utiliser les informations de site et de région** est activé, la vérification pour déterminer si le contournement doit s’appliquer fonctionne essentiellement de la même manière, que le contrôle d’admission des appels soit activé ou non. C’est-à-dire que, pour un appel PSTN donné, le sous-réseau du client est mappé à un site particulier, et l’ID de contournement pour ce sous-réseau est extrait. De même, le sous-réseau de la passerelle est mappé à un site particulier et l’ID de contournement pour ce sous-réseau est extrait. Le contournement aura lieu pour l’appel uniquement si les deux ID de contournement sont identiques. Si ce n’est pas le cas, la déviation du trafic multimédia n’aura pas lieu.</span><span class="sxs-lookup"><span data-stu-id="6e473-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="6e473-p105">Même si le contrôle d’admission des appels est désactivé globalement, la stratégie de bande passante doit être définie pour chaque site et liaison si vous voulez utiliser la configuration site-et-région pour décider d’appliquer le contournement ou non. La valeur réelle de la restriction de la bande passante ou le mode de celle-ci n’a aucune importance. L’objectif est que le système calcule automatiquement différents ID de contournement à associer à différents emplacements qui ne sont pas correctement connectés. Définir une restriction de bande passante signifie par définition qu’une liaison n’est pas correctement connectée.</span><span class="sxs-lookup"><span data-stu-id="6e473-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="6e473-129">Le contrôle d’admission des appels est activé et la déviation du trafic multimédia n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="6e473-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="6e473-130">Cela s’applique uniquement lorsque toutes les passerelles et les PBX IP ne sont pas correctement connectés ou ne remplissent pas toutes les conditions pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="6e473-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="6e473-131">Pour plus d’informations sur les exigences en matière de contournement du contenu multimédia, voir [configuration technique requise pour la dérivation multimédia dans Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="6e473-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6e473-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e473-132">See Also</span></span>


[<span data-ttu-id="6e473-133">Présentation de l’exclusion de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e473-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="6e473-134">Modes de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e473-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="6e473-135">Configuration technique requise pour la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e473-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

