---
title: 'Lync Server 2013 : création ou modification d’un site réseau'
description: 'Lync Server 2013 : créez ou modifiez un site réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network site
ms:assetid: 14e24856-9996-4da4-9f31-300940bdf5aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398218(v=OCS.15)
ms:contentKeyID: 48183488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4db9080f866becfcb94972787e099a69eac28c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562200"
---
# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="a1937-103">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1937-103">Create or modify a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1937-104">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a1937-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a1937-105">Les déploiements du contrôle d’admission des appels, du système E9-1-1 et du contournement de média s’appuient sur la configuration des *sites réseau* qui sont définis dans une région du réseau et toujours associés à celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a1937-105">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="a1937-106">Un site réseau représente une succursale, un ensemble de bâtiments ou un campus.</span><span class="sxs-lookup"><span data-stu-id="a1937-106">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="a1937-107">Les sites réseau représentent des ensembles de sous-réseaux avec une bande passante similaire.</span><span class="sxs-lookup"><span data-stu-id="a1937-107">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="a1937-p102">Les procédures suivantes vous permettent de créer ou de modifier des sites réseau. Par exemple, si vous avez créé des sites réseau pour une fonctionnalité vocale, vous n’avez pas besoin de créer d’autres sites réseau ; les autres fonctionnalités vocales utiliseront ces mêmes sites. Toutefois, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité.  Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a1937-p102">Use the following procedures to create or modify network sites. For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites. You may, however, need to modify an existing network site definition to apply feature-specific settings. For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1937-112">Vous pouvez trouver des exemples et des conditions spécifiques pour les sites réseau concernant chaque fonctionnalité vocale avancée dans la documentation de déploiement :</span><span class="sxs-lookup"><span data-stu-id="a1937-112">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="a1937-113"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configuration des sites réseau pour le contrôle d’admission des adresses dans Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="a1937-113"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="a1937-114">Pour plus d’informations sur l’utilisation des sites réseau, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="a1937-114">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a1937-115">New-applet csnetworksite</span><span class="sxs-lookup"><span data-stu-id="a1937-115">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="a1937-116">Get-applet csnetworksite</span><span class="sxs-lookup"><span data-stu-id="a1937-116">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="a1937-117">Set-applet csnetworksite</span><span class="sxs-lookup"><span data-stu-id="a1937-117">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="a1937-118">Remove-applet csnetworksite</span><span class="sxs-lookup"><span data-stu-id="a1937-118">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="a1937-119">Créer un site réseau</span><span class="sxs-lookup"><span data-stu-id="a1937-119">Create a Network Site</span></span>

<span data-ttu-id="a1937-120">Créez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="a1937-120">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="a1937-121">Pour créer un site réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a1937-121">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="a1937-122">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1937-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1937-123">Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="a1937-123">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="a1937-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1937-124">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="a1937-125">Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica » (Amérique du Nord).</span><span class="sxs-lookup"><span data-stu-id="a1937-125">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1937-126">La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="a1937-126">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="a1937-127">Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a1937-127">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="a1937-128">Pour créer un site réseau à l’aide du Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="a1937-128">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1937-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1937-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1937-130">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1937-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a1937-131">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a1937-131">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a1937-132">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="a1937-132">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="a1937-133">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a1937-133">Click **New**.</span></span>

5.  <span data-ttu-id="a1937-134">Dans la page **Nouveau site**, cliquez sur **Nom**, puis tapez le nom du site réseau.</span><span class="sxs-lookup"><span data-stu-id="a1937-134">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="a1937-135">Cliquez sur **Région**, puis cliquez sur une région dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1937-135">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="a1937-136">Éventuellement, cliquez sur **Stratégie de bande passante**, puis sur une stratégie de bande passante dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1937-136">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1937-137">La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site.</span><span class="sxs-lookup"><span data-stu-id="a1937-137">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="a1937-138">Éventuellement, cliquez sur **Stratégie d’emplacement**, puis sur une stratégie d’emplacement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a1937-138">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1937-139">La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site.</span><span class="sxs-lookup"><span data-stu-id="a1937-139">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="a1937-140">Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="a1937-140">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="a1937-141">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a1937-141">Click **Commit**.</span></span>

11. <span data-ttu-id="a1937-142">Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a1937-142">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="a1937-143">Modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="a1937-143">Modify a Network Site</span></span>

<span data-ttu-id="a1937-144">Modifiez une région réseau pouvant être utilisée par le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="a1937-144">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="a1937-145">Pour modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="a1937-145">To modify a network site</span></span>

1.  <span data-ttu-id="a1937-146">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a1937-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1937-147">Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="a1937-147">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="a1937-148">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a1937-148">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="a1937-p104">Dans cet exemple, le site appelé « Albuquerque » est déplacé dans la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou le contournement de média, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.</span><span class="sxs-lookup"><span data-stu-id="a1937-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a1937-p105">Bien que le paramètre BypassID existe pour le contournement de média, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="a1937-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="a1937-153">Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a1937-153">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="a1937-154">Pour modifier un site réseau à l’aide du Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="a1937-154">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1937-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1937-155">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1937-156">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1937-156">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a1937-157">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a1937-157">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="a1937-158">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="a1937-158">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="a1937-159">Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="a1937-159">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="a1937-160">Cliquez sur **Modifier**, puis sur **Afficher les détails…**.</span><span class="sxs-lookup"><span data-stu-id="a1937-160">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="a1937-161">Dans la page **Modifier le site**, changez les valeurs des paramètres de ce site réseau comme il convient.</span><span class="sxs-lookup"><span data-stu-id="a1937-161">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="a1937-162">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a1937-162">Click **Commit**.</span></span>

8.  <span data-ttu-id="a1937-163">Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a1937-163">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

