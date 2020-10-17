---
title: 'Lync Server 2013 : options globales de déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec067e84c87321374ed1d9beb98c086633f3e28c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515331"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="9b003-102">Options globales de déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b003-102">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b003-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9b003-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b003-104">Cette rubrique suppose que vous ayez déjà configuré la déviation du trafic multimédia pour toutes les jonctions à un homologue (une passerelle RTC (réseau téléphonique commuté), un système IP-PBX ou un contrôleur SBC (session Border Controller) sur un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour lequel vous souhaitez que le support contourne le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="9b003-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="9b003-105">En plus d’activer le contournement de média pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres globaux du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="9b003-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="9b003-106">Les paramètres globaux de déviation du trafic multimédia peuvent spécifier que la déviation du trafic multimédia pour les appels vers le RTC ou cette déviation du trafic multimédia est utilisée en utilisant le mappage des sous-réseaux aux sites réseau et aux régions réseau, de la même manière que le contrôle d’admission des appels, une autre fonctionnalité vocale avancée.</span><span class="sxs-lookup"><span data-stu-id="9b003-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="9b003-107">Lorsque la déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés, les informations de région réseau, de site réseau et de sous-réseau spécifiées pour le contrôle d’admission des appels sont automatiquement utilisées pour déterminer s’il faut employer le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="9b003-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="9b003-108">Cela signifie que vous ne pouvez pas spécifier que la déviation du trafic multimédia est toujours tentée pour les appels au réseau téléphonique commuté lorsque le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="9b003-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="9b003-109">Cette rubrique décrit comment utiliser le panneau de configuration Lync Server et Lync Server Management Shell conjointement pour configurer les paramètres globaux de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="9b003-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9b003-110">Pour configurer le contournement de média en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle PSTN, un PBX IP ou un contrôleur de frontière de session d’un fournisseur de jonction SIP) doit être bonne.</span><span class="sxs-lookup"><span data-stu-id="9b003-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="9b003-111">Si des restrictions de bande passante sont appliquées sur la liaison, le contournement de média ne peut pas être appliqué aux appels.</span><span class="sxs-lookup"><span data-stu-id="9b003-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="9b003-112">Le contournement de média ne va pas interagir avec chaque passerelle PSTN, chaque système IP-PBX et chaque SBC.</span><span class="sxs-lookup"><span data-stu-id="9b003-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="9b003-113">Microsoft a testé un ensemble de passerelles PSTN et de contrôleurs SBC avec des partenaires agréés et a effectué quelques tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="9b003-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="9b003-114">La déviation du trafic multimédia n’est prise en charge qu’avec les produits et les versions mentionnés dans le programme d’interopérabilité ouvert pour les communications unifiées – Lync Server à <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="9b003-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="9b003-115">Étapes suivantes : choisir les paramètres globaux du contournement de média</span><span class="sxs-lookup"><span data-stu-id="9b003-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="9b003-116">Après avoir activé le contournement de média sur des connexions de jonction vers un homologue pour des sites ou des services spécifiques, utilisez le contenu suivant pour :</span><span class="sxs-lookup"><span data-stu-id="9b003-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="9b003-117">Activez toujours la déviation du trafic multimédia, comme indiqué dans [configure Media Bypass in Lync Server 2013 pour toujours contourner le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="9b003-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="9b003-118">Ou configurez la déviation du trafic multimédia pour utiliser les informations de site et de région, comme indiqué dans [configure Media Bypass Global Settings in Lync Server 2013 pour utiliser les informations de site et de région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="9b003-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9b003-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b003-119">See Also</span></span>


[<span data-ttu-id="9b003-120">Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b003-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="9b003-121">Associer un sous-réseau à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b003-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="9b003-122">Configurer la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b003-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="9b003-123">Contournement de média et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b003-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

