---
title: Configuration des paramètres généraux de déviation du trafic multimédia pour utiliser les informations de site et de région
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="19b21-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span><span class="sxs-lookup"><span data-stu-id="19b21-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19b21-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="19b21-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="19b21-104">Cette rubrique part du principe que vous avez déjà configuré le contournement multimédia pour toutes les connexions de Trunk du serveur de médiation à un homologue (une passerelle RTC (réseau téléphonique commuté), un PBX IP ou un contrôleur de bordure de session (SBC) sur un service de téléphonie sur Internet. Fournisseur (ITSP) pour un site ou un service spécifique pour lequel vous souhaitez que le média ignore le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="19b21-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="19b21-105">Cette rubrique part du principe que vous avez défini tous les sites centraux et les sites de succursale dans le générateur de topologie de telle sorte qu’ils correspondent à la région du réseau, au site réseau et à la configuration de sous-réseau que vous avez exécutées conformément aux étapes de la rubrique <A href="lync-server-2013-create-or-modify-a-network-region.md">créer ou modifier une région réseau dans Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">créez ou modifiez un site réseau dans lync Server 2013</A>, puis <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associez un sous-réseau à un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="19b21-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="19b21-106">S’il ne correspond pas, l’action de contournement du support n’aboutira pas.</span><span class="sxs-lookup"><span data-stu-id="19b21-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="19b21-107">Outre l’activation de l’exclusion de médias pour les connexions de Trunk individuelles associées à un homologue, vous devez également configurer des paramètres globaux.</span><span class="sxs-lookup"><span data-stu-id="19b21-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="19b21-108">Si vous suivez les étapes décrites dans cette rubrique pour configurer des paramètres globaux pour la dérivation de médias, il est supposé que l’une ou les deux situations suivantes affectent votre configuration:</span><span class="sxs-lookup"><span data-stu-id="19b21-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="19b21-109">Vous *ne disposez pas* de la bonne connectivité entre les points de terminaison Lync Server et les homologues pour lesquels vous avez configuré une contournement multimédia sur la connexion Trunk.</span><span class="sxs-lookup"><span data-stu-id="19b21-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="19b21-110">Le contrôle d’admission des appels (CAC) pour la gestion de la bande passante est activé.</span><span class="sxs-lookup"><span data-stu-id="19b21-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="19b21-111">Pour plus d’informations sur les considérations relatives aux contrôles d’admission des appels et au contournement du contenu multimédia, voir la section «contrôle d’admission des appels de connexions RTC» dans le <A href="lync-server-2013-media-bypass-and-mediation-server.md">serveur de contournement de média et le serveur de médiation de Lync server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="19b21-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="19b21-p103">Les informations relatives aux régions du réseau et aux sites réseau sont partagées entre les fonctionnalités Voix Entreprise avancées de contrôle d’admission des appels et de déviation du trafic multimédia lorsque ces deux fonctionnalités sont activées. Par conséquent, si vous avez déjà configuré le contrôle d’admission des appels, vous n’avez pas besoin d’effectuer la procédure ci-dessous pour modifier les informations relatives aux sites et aux régions destinées à la déviation du trafic multimédia. Suivez les étapes de cette procédure si vous n’avez pas encore configuré les régions et les sites du réseau pour le contrôle d’admission des appels et si vous souhaitez modifier les paramètres de déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="19b21-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="19b21-115">Vous pouvez aussi suivre ces étapes si vous voulez utiliser les informations sur les sites et les régions pour faire la décision d’ignorer, mais n’avez pas l’intention d’activer le contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="19b21-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="19b21-116">Dans d’autres cas, les liens limités en bande passante doivent toujours être représentés par le biais de stratégies d’intersite réseau, comme décrit dans la rubrique [créer des stratégies de réseau intersite dans Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="19b21-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="19b21-117">Les contraintes de bande passante réelles ne sont pas aussi importantes dans ce cas, car le contrôle d’admission des appels n’a pas été activé.</span><span class="sxs-lookup"><span data-stu-id="19b21-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="19b21-118">Ces liens servent à partitionner les sous-réseaux pour spécifier ceux qui n’ont pas de limites de bande passante et qui peuvent donc utiliser une dérivation multimédia.</span><span class="sxs-lookup"><span data-stu-id="19b21-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="19b21-119">Notez que cela est également vrai lorsque le contrôle d’admission des appels et l’exclusion de médias sont activés.</span><span class="sxs-lookup"><span data-stu-id="19b21-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="19b21-120">Par ailleurs, en cas de contournement, il est nécessaire de garantir une cohérence entre un site défini dans le générateur de topologie et tel qu’il est défini lorsque vous configurez des régions réseau et des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="19b21-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="19b21-121">Par exemple, si vous disposez d’un site de succursale que vous avez défini dans le générateur de topologie comme ayant uniquement une passerelle RTC déployée, ce site de succursale doit être configuré avec une stratégie vocale d’entreprise permettant aux utilisateurs du site de succursale d’avoir leurs appels RTC via le RTC. passerelle sur le site de la succursale.</span><span class="sxs-lookup"><span data-stu-id="19b21-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="19b21-122">Pour configurer les informations relatives aux sites et aux régions pour la déviation du trafic multimédia</span><span class="sxs-lookup"><span data-stu-id="19b21-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="19b21-123">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="19b21-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19b21-124">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="19b21-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="19b21-125">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="19b21-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="19b21-126">Double-cliquez sur la configuration **Globale** dans le tableau.</span><span class="sxs-lookup"><span data-stu-id="19b21-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="19b21-127">Dans la page **Modifier la configuration globale**, activez la case à cocher **Activer la déviation du trafic multimédia**.</span><span class="sxs-lookup"><span data-stu-id="19b21-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="19b21-128">Cliquez sur **Utiliser la configuration des sites et des régions**.</span><span class="sxs-lookup"><span data-stu-id="19b21-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="19b21-129">Si nécessaire, activez la case à cocher **Activer la déviation pour les sites non mappés**.</span><span class="sxs-lookup"><span data-stu-id="19b21-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="19b21-p107">N’activez cette case à cocher que si des sites de grande taille et des sites de succursale sont associées à la même région, les premiers (par exemple, un grand site central) sans contraintes de bande passante et les seconds avec des contraintes de bande passante. Lorsque vous activez la déviation du trafic pour les sites non mappés, la configuration est rationalisée. Vous ne spécifiez que les sous-réseaux associés aux sites de succursale au lieu d’avoir à spécifier tous les sous-réseaux associés à tous les sites. Nous vous recommandons de ne pas activer cette case à cocher si le contrôle d’admission des appels est activé.</span><span class="sxs-lookup"><span data-stu-id="19b21-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="19b21-133">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="19b21-133">Click **Commit**.</span></span>

<span data-ttu-id="19b21-134">Ensuite, ajoutez des sous-réseaux au site réseau, comme décrit dans la section [associer des sous-réseaux avec les sites réseau pour le contournement de médias dans Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="19b21-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="19b21-135">(Les procédures réelles pour l’Association de sous-réseaux avec les sites réseau sont décrites dans [la section associer un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) Après avoir associé tous les sous-réseaux aux sites réseau, le déploiement par dérivation de média est terminé.</span><span class="sxs-lookup"><span data-stu-id="19b21-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="19b21-136">Si vous n’avez pas encore créé de régions et de sites réseau, vous devez les créer pour poursuivre le déploiement de la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="19b21-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="19b21-137">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-create-or-modify-a-network-region.md">création ou modification d’une région réseau dans Lync server 2013</A> et <A href="lync-server-2013-create-or-modify-a-network-site.md">création ou modification d’un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="19b21-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19b21-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19b21-138">See Also</span></span>


[<span data-ttu-id="19b21-139">Associez des sous-réseaux aux sites réseau pour une dérivation multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19b21-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

