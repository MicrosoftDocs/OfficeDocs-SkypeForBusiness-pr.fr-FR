---
title: 'Lync Server 2013 : configuration des régions réseau pour le contrôle d’admission des opérations'
description: 'Lync Server 2013 : configuration des régions réseau pour le contrôle d’admission des opérations.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577560"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="824bf-103">Configuration des régions réseau pour le contrôle d’admission des serveurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="824bf-103">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="824bf-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="824bf-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="824bf-105">Si vous avez déjà créé des régions réseau pour E9-1-1 ou une déviation du trafic multimédia, vous pouvez modifier les régions réseau existantes en ajoutant des paramètres spécifiques au contrôle d’admission des appels à l’aide de la cmdlet <STRONG>Set-applet csnetworkregion</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="824bf-105">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="824bf-106">Pour obtenir un exemple de la façon de modifier une région réseau, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="824bf-106">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="824bf-107">Les *régions réseau* sont les concentrateurs ou les dorsales réseau utilisés pour la configuration du contrôle d’admission des médias, E9-1-1 et la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="824bf-107">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="824bf-108">Utilisez la procédure suivante pour créer des régions réseau qui s’alignent sur les régions réseau dans l’exemple de topologie réseau pour le contrôle d’admission des opérations.</span><span class="sxs-lookup"><span data-stu-id="824bf-108">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="824bf-109">Pour afficher l’exemple de topologie réseau, reportez-vous à l’exemple [suivant : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="824bf-109">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="824bf-110">L’exemple de topologie réseau pour le contrôle d’admission des États comprend trois régions : Amérique du Nord, EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="824bf-110">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="824bf-111">Chaque région dispose d’un site central spécifié.</span><span class="sxs-lookup"><span data-stu-id="824bf-111">Each region has a specified central site.</span></span> <span data-ttu-id="824bf-112">Pour la région Amérique du Nord, le site central désigné est nommé CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="824bf-112">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="824bf-113">La procédure suivante montre comment utiliser la cmdlet **New-applet csnetworkregion** pour créer la région Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="824bf-113">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="824bf-114">Dans la procédure suivante, Lync Server Management Shell est utilisé pour créer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="824bf-114">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="824bf-115">Pour plus d’informations sur l’utilisation du panneau de configuration Lync Server pour créer une région réseau, voir <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or Modify a Network Region in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="824bf-115">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="824bf-116">Pour créer une région réseau pour le contrôle d’admission des appels</span><span class="sxs-lookup"><span data-stu-id="824bf-116">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="824bf-117">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="824bf-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="824bf-118">Pour chaque région que vous devez créer, exécutez la cmdlet **New-applet csnetworkregion** .</span><span class="sxs-lookup"><span data-stu-id="824bf-118">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="824bf-119">Par exemple, pour créer la région Amérique du Nord, exécutez :</span><span class="sxs-lookup"><span data-stu-id="824bf-119">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="824bf-120">Répétez l’étape 2 pour créer les régions réseau, EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="824bf-120">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

