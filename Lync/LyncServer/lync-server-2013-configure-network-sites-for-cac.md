---
title: 'Lync Server 2013 : configurer les sites réseau pour le CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b678cab0ea8b473e6ea33ab5db951b105a11fa78
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971232"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="57416-102">Configurer les sites réseau pour le CAC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57416-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57416-103">_**Dernière modification de la rubrique :** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="57416-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="57416-104">Si vous avez déjà créé des sites réseau pour le contournement de E9-1-1 ou du contenu multimédia, vous pouvez modifier les sites réseau existants pour appliquer un profil de stratégie de bande passante à l’aide de l’applet de connexion <STRONG>Set-CsNetworkSite</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="57416-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="57416-105">Pour obtenir un exemple illustrant comment modifier un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57416-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="57416-106">Les *sites réseau* sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="57416-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="57416-107">Utilisez les procédures suivantes pour créer des sites réseau qui s’alignent sur les sites réseau dans l’exemple de topologie réseau pour CAC.</span><span class="sxs-lookup"><span data-stu-id="57416-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="57416-108">Les procédures suivantes vous expliquent comment créer et configurer des sites réseau limités par une bande passante WAN et exiger ainsi des stratégies de bande passante qui limitent le flux de trafic audio ou vidéo en temps réel.</span><span class="sxs-lookup"><span data-stu-id="57416-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="57416-109">Dans l’exemple de déploiement CAC, la région Amérique du Nord comporte six sites.</span><span class="sxs-lookup"><span data-stu-id="57416-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="57416-110">Trois de ces sites sont limités par une bande passante WAN : Reno, Portland et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="57416-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="57416-111">Les trois autres sites, qui ne sont *pas* limités par la bande passante WAN : New York, Chicago et détroit.</span><span class="sxs-lookup"><span data-stu-id="57416-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="57416-112">Pour obtenir un exemple illustrant la création ou la modification de ces sites, voir [créer ou modifier un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="57416-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="57416-113">Pour afficher l’exemple de topologie du réseau, reportez-vous à la rubrique [exemple : rassemblement des exigences relatives au contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="57416-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="57416-114">Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer un site réseau.</span><span class="sxs-lookup"><span data-stu-id="57416-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="57416-115">Pour plus d’informations sur l’utilisation du panneau de configuration de Lync Server pour créer un site réseau, voir <A href="lync-server-2013-create-or-modify-a-network-site.md">créer ou modifier un site réseau dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="57416-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="57416-116">Pour créer un site réseau pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="57416-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="57416-117">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="57416-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="57416-118">Exécutez l’applet de nouvelle applet de **CsNetworkSite** pour créer des sites réseau et appliquer un profil de stratégie de bande passante approprié à chaque site.</span><span class="sxs-lookup"><span data-stu-id="57416-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="57416-119">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="57416-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="57416-120">Pour terminer la création de sites réseau pour la topologie d’exemple complète, répétez l’étape 2 pour les sites réseau limités en bande passante dans les régions EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="57416-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

