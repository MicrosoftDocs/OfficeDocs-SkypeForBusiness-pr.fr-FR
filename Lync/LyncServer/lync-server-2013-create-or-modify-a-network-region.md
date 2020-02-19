---
title: 'Lync Server 2013 : création ou modification d’une région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3579286f0cf4b77c84baa013aead13b3b671549c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a><span data-ttu-id="8462c-102">Création ou modification d’une région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8462c-102">Create or modify a network region in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8462c-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8462c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8462c-104">Les *régions réseau* sont les concentrateurs réseau ou dorsales principales utilisées dans la configuration du contrôle d’admission des appels, du service E9-1-1 et du contournement de média.</span><span class="sxs-lookup"><span data-stu-id="8462c-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="8462c-105">Les procédures suivantes vous permettent de créer ou de modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="8462c-105">Use the following procedures to create or modify network regions.</span></span> <span data-ttu-id="8462c-106">Par exemple, si vous avez déjà créé des régions réseau pour une fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau ; d’autres fonctionnalités Voix Entreprise avancées utiliseront ces mêmes régions.</span><span class="sxs-lookup"><span data-stu-id="8462c-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="8462c-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8462c-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="8462c-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis déployez ensuite le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="8462c-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="8462c-109">Pour plus d’informations, reportez-vous à la rubrique [configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="8462c-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8462c-110">Toutes les exigences ayant trait à des fonctionnalités pour les définitions des régions réseau sont documentées dans les rubriques de déploiement des fonctionnalités concernées.</span><span class="sxs-lookup"><span data-stu-id="8462c-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<span data-ttu-id="8462c-111">Pour plus d’informations sur l’utilisation des régions réseau, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="8462c-111">For details about working with network regions, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8462c-112">New-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="8462c-112">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [<span data-ttu-id="8462c-113">Get-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="8462c-113">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="8462c-114">Set-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="8462c-114">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [<span data-ttu-id="8462c-115">Remove-applet csnetworkregion</span><span class="sxs-lookup"><span data-stu-id="8462c-115">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a><span data-ttu-id="8462c-116">Créer une région réseau</span><span class="sxs-lookup"><span data-stu-id="8462c-116">Create a Network Region</span></span>

<span data-ttu-id="8462c-117">Créez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="8462c-117">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="8462c-118">Pour créer une région réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8462c-118">To create a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8462c-119">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8462c-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8462c-120">Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :</span><span class="sxs-lookup"><span data-stu-id="8462c-120">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="8462c-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8462c-121">For example:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    <span data-ttu-id="8462c-122">Dans cet exemple, vous avez créé une région réseau appelée « NorthAmerica » (Amérique du Nord) qui est associée à un site central avec l’ID de site CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="8462c-122">In this example, you created a network region called “NorthAmerica” that is associated with a central site with site ID CHICAGO.</span></span>

3.  <span data-ttu-id="8462c-123">Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="8462c-123">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="8462c-124">Pour créer une région réseau à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="8462c-124">To create a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8462c-125">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8462c-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8462c-126">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8462c-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8462c-127">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="8462c-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8462c-128">Cliquez sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="8462c-128">Click **Region**.</span></span>

4.  <span data-ttu-id="8462c-129">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8462c-129">Click **New**.</span></span>

5.  <span data-ttu-id="8462c-130">Dans la page **Nouvelle région**, cliquez sur **Nom**, puis tapez le nom de la région réseau.</span><span class="sxs-lookup"><span data-stu-id="8462c-130">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6.  <span data-ttu-id="8462c-131">Cliquez sur **Site central**, puis cliquez sur un site central dans la liste.</span><span class="sxs-lookup"><span data-stu-id="8462c-131">Click **Central site**, and then click a central site in the list.</span></span>

7.  <span data-ttu-id="8462c-132">Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="8462c-132">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8.  <span data-ttu-id="8462c-133">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8462c-133">Click **Commit**.</span></span>

9.  <span data-ttu-id="8462c-134">Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="8462c-134">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-region"></a><span data-ttu-id="8462c-135">Modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="8462c-135">Modify a Network Region</span></span>

<span data-ttu-id="8462c-136">Modifiez les paramètres d’une région réseau existante pour gérer les changements apportés aux informations de base sur les régions ou les changements requis dans le cadre d’une nouvelle fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="8462c-136">Modify settings for an existing network region to accommodate changes to the basic region information or changes required by a new feature.</span></span>

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a><span data-ttu-id="8462c-137">Pour modifier une région réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="8462c-137">To modify a network region using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="8462c-138">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8462c-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8462c-139">Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :</span><span class="sxs-lookup"><span data-stu-id="8462c-139">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    <span data-ttu-id="8462c-140">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="8462c-140">For example:</span></span>
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    <span data-ttu-id="8462c-p103">Dans cet exemple, vous avez modifié une région réseau existante appelée « NorthAmerica » (créée en suivant les procédures décrites plus haut dans cette rubrique) en changeant sa description. Si une description existait dans la région « NorthAmerica », cette commande la remplace par cette valeur. Si aucune description n’a été définie, cette commande s’en charge.</span><span class="sxs-lookup"><span data-stu-id="8462c-p103">In this example, you modified an existing network region called “NorthAmerica” (created using the procedures earlier in this topic) by changing the description. If a description existed for the “NorthAmerica” region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3.  <span data-ttu-id="8462c-143">Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="8462c-143">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a><span data-ttu-id="8462c-144">Pour modifier une région réseau à l’aide du panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="8462c-144">To modify a network region using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8462c-145">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8462c-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8462c-146">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8462c-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8462c-147">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="8462c-147">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8462c-148">Cliquez sur le bouton de navigation **Région**.</span><span class="sxs-lookup"><span data-stu-id="8462c-148">Click the **Region** navigation button.</span></span>

4.  <span data-ttu-id="8462c-149">Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="8462c-149">In the table, click the network region that you want to modify.</span></span>

5.  <span data-ttu-id="8462c-150">Cliquez sur **Modifier**, puis sur **Afficher les détails…**.</span><span class="sxs-lookup"><span data-stu-id="8462c-150">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="8462c-151">Dans la page **Modifier la région**, changez les valeurs des paramètres de cette région réseau comme il convient.</span><span class="sxs-lookup"><span data-stu-id="8462c-151">On the **Edit Region** page, change the values for this network region’s settings as appropriate.</span></span>

7.  <span data-ttu-id="8462c-152">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8462c-152">Click **Commit**.</span></span>

8.  <span data-ttu-id="8462c-153">Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="8462c-153">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

