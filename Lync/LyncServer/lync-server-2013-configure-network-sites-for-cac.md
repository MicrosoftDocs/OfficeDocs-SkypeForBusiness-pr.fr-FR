---
title: 'Lync Server 2013 : configuration des sites réseau pour le contrôle d’admission des opérations'
description: 'Lync Server 2013 : configurez les sites réseau pour le contrôle d’admission des opérations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24adbbb1f5ee46618c685e072d519a338cb9b0af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565000"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="ec67c-103">Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec67c-103">Configure network sites for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec67c-104">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="ec67c-104">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="ec67c-105">Si vous avez déjà créé des sites réseau pour E9-1-1 ou le contournement de média, vous pouvez modifier les sites réseau existants pour appliquer un profil de stratégie de bande passante à l’aide de l’applet de commande <STRONG>Set-CsNetworkSite</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ec67c-105">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="ec67c-106">Pour obtenir un exemple de la façon de modifier un site réseau, reportez-vous à la rubrique <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ec67c-106">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ec67c-p102">Les *sites réseau* sont les bureaux ou emplacements au sein de chaque région réseau des déploiements de contrôle d’admission des appels (Call Admission Control ou CAC), E9-1-1 et de contournement de média. Utilisez les procédures suivantes pour créer des sites réseau qui s’alignent sur les sites réseau de l’exemple de topologie de réseau pour le service CAC. Ces procédures indiquent comment créer et configurer des sites réseau restreints par la bande passante de réseau étendu et qui nécessitent, par conséquent, des stratégies de bande passante qui limitent le flux du trafic audio ou vidéo en temps réel.</span><span class="sxs-lookup"><span data-stu-id="ec67c-p102">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments. Use the following procedures to create network sites that align to network sites in the example network topology for CAC. These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="ec67c-110">Dans l’exemple de déploiement CAC, la région Amérique du Nord comporte six sites.</span><span class="sxs-lookup"><span data-stu-id="ec67c-110">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="ec67c-111">Parmi ces sites, trois sont restreints par la bande passante de réseau étendu : Reno, Portland et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="ec67c-111">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="ec67c-112">Les trois autres sites, qui ne sont *pas* restreints par la bande passante de réseau étendu sont les suivants : New York, Chicago et Détroit.</span><span class="sxs-lookup"><span data-stu-id="ec67c-112">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="ec67c-113">Pour obtenir un exemple de création ou de modification de ces autres sites réseau, reportez-vous à la rubrique [créer ou modifier un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="ec67c-113">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="ec67c-114">Pour afficher l’exemple de topologie réseau, reportez-vous à l’exemple [suivant : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="ec67c-114">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="ec67c-115">Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer un site réseau.</span><span class="sxs-lookup"><span data-stu-id="ec67c-115">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="ec67c-116">Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server pour créer un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ec67c-116">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="ec67c-117">Pour créer des sites réseau pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="ec67c-117">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="ec67c-118">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ec67c-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ec67c-119">Exécutez l’applet de commande **New-CsNetworkSite** pour créer des sites réseau, puis appliquez un profil de stratégie de bande passante approprié à chaque site.</span><span class="sxs-lookup"><span data-stu-id="ec67c-119">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="ec67c-120">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="ec67c-120">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="ec67c-121">Afin de terminer la création de sites réseau pour l’ensemble de l’exemple de topologie, répétez l’étape 2 pour les sites réseau à bande passante restreinte dans les régions EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="ec67c-121">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

