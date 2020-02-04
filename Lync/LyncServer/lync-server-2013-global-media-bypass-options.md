---
title: 'Lync Server 2013 : options de contournement global de médias'
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
ms.openlocfilehash: 653c47cd993bac8ada899f62fa3be6700cd34c33
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="8db09-102">Options de contournement global de médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db09-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db09-103">_**Dernière modification de la rubrique :** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="8db09-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8db09-104">Cette rubrique part du principe que vous avez déjà configuré une dérivation multimédia pour des Trunks vers un homologue (une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un contrôleur de bordure de session (SBC) sur un fournisseur de services de téléphonie Internet) pour un site ou un service spécifique pour vous voulez que le média ignore le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="8db09-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="8db09-p101">Outre l’activation de la déviation du trafic multimédia pour des connexions de jonction associées à un homologue, vous devez également configurer les paramètres généraux de déviation du trafic multimédia. Les paramètres généraux de déviation du trafic multimédia peuvent spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC ou de l’employer en utilisant le mappage des sous-réseaux vers les sites et les régions réseau, ce qui est similaire à ce que fait le contrôle d’admission des appels, une autre fonctionnalité vocale avancée. Lorsque la déviation du trafic multimédia et le contrôle d’admission des appels sont tous les deux activés, les informations relatives aux régions, aux sites et aux sous-réseaux qui sont spécifiées pour le contrôle d’admission des appels sont utilisées automatiquement pour déterminer si la déviation du trafic multimédia doit être employée. Cela signifie que vous ne pouvez pas spécifier de toujours tenter la déviation du trafic multimédia pour les appels vers le RTC lorsque le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="8db09-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="8db09-109">Cette rubrique décrit l’utilisation conjointe du panneau de configuration de Lync Server et de Lync Server Management Shell pour configurer les paramètres globaux de contournement de médias.</span><span class="sxs-lookup"><span data-stu-id="8db09-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8db09-110">Pour configurer la déviation du trafic multimédia en suivant cette procédure, la connectivité entre les clients et l’homologue du serveur de médiation (par exemple, une passerelle RTC, un PBX IP ou un contrôleur SBC d’un fournisseur de jonction SIP [Session Initiation Protocol]) doit être de bonne qualité.</span><span class="sxs-lookup"><span data-stu-id="8db09-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="8db09-111">Si des restrictions de bande passante sont appliquées sur la liaison, la déviation du trafic multimédia ne peut pas être appliquée aux appels.</span><span class="sxs-lookup"><span data-stu-id="8db09-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="8db09-112">La déviation du trafic multimédia ne va pas interagir avec chaque passerelle RTC, chaque système IP-PBX et chaque contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="8db09-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="8db09-113">Microsoft a testé une série de passerelles RTC et de SBC avec l’aide de partenaires agréés et a réalisé des tests avec les systèmes IP-PBX de Cisco.</span><span class="sxs-lookup"><span data-stu-id="8db09-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="8db09-114">La dérivation de média est uniquement prise en charge avec les produits et les versions indiqués sur le programme d’interopérabilité d’ouverture de communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span><span class="sxs-lookup"><span data-stu-id="8db09-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="8db09-115">Étapes suivantes : sélectionner les paramètres globaux de contournement du média</span><span class="sxs-lookup"><span data-stu-id="8db09-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="8db09-116">Une fois que vous avez activé la contournement multimédia sur une connexion de Trunk à un homologue pour des sites ou services spécifiques, utilisez le contenu suivant :</span><span class="sxs-lookup"><span data-stu-id="8db09-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="8db09-117">Activez toujours la dérivation multimédia, comme décrit dans la rubrique [configurer la contournement multimédia dans Lync Server 2013 pour ignorer toujours le serveur de médiation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="8db09-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="8db09-118">Vous pouvez aussi configurer la contournement multimédia pour utiliser les informations sur les sites et les régions, comme décrit dans [configurer les paramètres globaux de contournement du contenu multimédia dans Lync Server 2013 pour utiliser les informations relatives au site et à la région](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="8db09-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8db09-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8db09-119">See Also</span></span>


[<span data-ttu-id="8db09-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db09-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="8db09-121">Association d’un sous-réseau à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db09-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="8db09-122">Configuration de la déviation du trafic multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db09-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="8db09-123">Déviation du trafic multimédia et serveur de médiation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db09-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

