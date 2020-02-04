---
title: 'Lync Server 2013 : Création ou modification d’un site réseau'
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
ms.openlocfilehash: ed721a48b12a497b25d58e7ebb65ff3a91980904
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-site-in-lync-server-2013"></a><span data-ttu-id="268b1-102">Création ou modification d’un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="268b1-102">Create or modify a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="268b1-103">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="268b1-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="268b1-104">Les déploiements de contrôle d’admission des appels (CAC), de E9-1-1 et de contournement de média multimédias dépendent de la configuration des *sites réseau* qui sont définis dans et qui sont toujours associés à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="268b1-104">Call admission control (CAC), E9-1-1, and media bypass deployments rely on the configuration of *network sites* which are defined within and always associated with a network region.</span></span> <span data-ttu-id="268b1-105">Un site réseau représente une succursale, un ensemble de bâtiments ou un campus.</span><span class="sxs-lookup"><span data-stu-id="268b1-105">A network site represents a branch office location, a set of buildings, or a campus.</span></span> <span data-ttu-id="268b1-106">Les sites réseau représentent des collections de sous-réseaux avec une bande passante similaire.</span><span class="sxs-lookup"><span data-stu-id="268b1-106">Network sites represent collections of subnets with similar bandwidth.</span></span>

<span data-ttu-id="268b1-107">Pour créer ou modifier des sites réseau, utilisez les procédures suivantes.</span><span class="sxs-lookup"><span data-stu-id="268b1-107">Use the following procedures to create or modify network sites.</span></span> <span data-ttu-id="268b1-108">Par exemple, si vous avez déjà créé des sites réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouveaux sites réseau. les autres fonctions vocales utilisent les mêmes sites.</span><span class="sxs-lookup"><span data-stu-id="268b1-108">For example, if you have already created network sites for one Voice feature, you do not need to create new network sites; other Voice features will use those same sites.</span></span> <span data-ttu-id="268b1-109">Cependant, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="268b1-109">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="268b1-110">Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="268b1-110">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="268b1-111">Le cas échéant, vous trouverez des exemples et des exigences spécifiques pour les sites réseau en ce qui concerne une fonctionnalité vocale avancée dans la documentation de déploiement pour chaque fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="268b1-111">Where they exist, you can find specific examples and requirements for network sites as they pertain to an advanced Voice feature in the Deployment documentation for each feature:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="268b1-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configurer les sites réseau pour le CAC dans Lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="268b1-112"><A href="lync-server-2013-configure-network-sites-for-cac.md">Configure network sites for CAC in Lync Server 2013</A></span></span></P></LI></UL>



</div>

<span data-ttu-id="268b1-113">Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="268b1-113">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="268b1-114">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="268b1-114">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

  - [<span data-ttu-id="268b1-115">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="268b1-115">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)

  - [<span data-ttu-id="268b1-116">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="268b1-116">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

  - [<span data-ttu-id="268b1-117">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="268b1-117">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)

<div>

## <a name="create-a-network-site"></a><span data-ttu-id="268b1-118">Créer un site réseau</span><span class="sxs-lookup"><span data-stu-id="268b1-118">Create a Network Site</span></span>

<span data-ttu-id="268b1-119">Créez une région réseau qui peut être utilisée par le contrôle d’admission des appels, le E9-1-1 ou le contournement multimédia.</span><span class="sxs-lookup"><span data-stu-id="268b1-119">Create a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-create-a-network-site-by-using-management-shell"></a><span data-ttu-id="268b1-120">Pour créer un site réseau à l’aide de Management Shell</span><span class="sxs-lookup"><span data-stu-id="268b1-120">To create a network site by using Management Shell</span></span>

1.  <span data-ttu-id="268b1-121">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="268b1-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="268b1-122">Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="268b1-122">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>
    
        New-CsNetworkSite -NetworkSiteID <string>
    
    <span data-ttu-id="268b1-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="268b1-123">For example:</span></span>
    
        New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
    
    <span data-ttu-id="268b1-124">Dans cet exemple, vous avez créé un site réseau appelé « Chicago » qui se trouve dans la région « NorthAmerica » (Amérique du Nord).</span><span class="sxs-lookup"><span data-stu-id="268b1-124">In this example, you created a network site called “Chicago” that is in the “NorthAmerica” network region.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="268b1-125">La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="268b1-125">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

    
    </div>

3.  <span data-ttu-id="268b1-126">Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="268b1-126">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-create-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="268b1-127">Pour créer un site réseau en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="268b1-127">To create a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="268b1-128">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="268b1-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="268b1-129">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="268b1-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="268b1-130">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="268b1-130">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="268b1-131">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="268b1-131">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="268b1-132">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="268b1-132">Click **New**.</span></span>

5.  <span data-ttu-id="268b1-133">Dans la page **Nouveau site**, cliquez sur **Nom**, puis tapez le nom du site réseau.</span><span class="sxs-lookup"><span data-stu-id="268b1-133">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6.  <span data-ttu-id="268b1-134">Cliquez sur **Région**, puis cliquez sur une région dans la liste.</span><span class="sxs-lookup"><span data-stu-id="268b1-134">Click **Region**, and then click a region in the list.</span></span>

7.  <span data-ttu-id="268b1-135">Éventuellement, cliquez sur **Stratégie de bande passante**, puis sur une stratégie de bande passante dans la liste.</span><span class="sxs-lookup"><span data-stu-id="268b1-135">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="268b1-136">La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site.</span><span class="sxs-lookup"><span data-stu-id="268b1-136">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

    
    </div>

8.  <span data-ttu-id="268b1-137">Éventuellement, cliquez sur **Stratégie d’emplacement**, puis sur une stratégie d’emplacement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="268b1-137">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="268b1-138">La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site.</span><span class="sxs-lookup"><span data-stu-id="268b1-138">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

    
    </div>

9.  <span data-ttu-id="268b1-139">Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="268b1-139">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="268b1-140">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="268b1-140">Click **Commit**.</span></span>

11. <span data-ttu-id="268b1-141">Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="268b1-141">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

</div>

</div>

<div>

## <a name="modify-a-network-site"></a><span data-ttu-id="268b1-142">Modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="268b1-142">Modify a Network Site</span></span>

<span data-ttu-id="268b1-143">Modification d’une région réseau qui peut être utilisée par le contrôle d’admission des appels, E9-1-1 ou contournement multimédia.</span><span class="sxs-lookup"><span data-stu-id="268b1-143">Modify a network region that can be used by call admission control, E9-1-1, or media bypass.</span></span>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="268b1-144">Pour modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="268b1-144">To modify a network site</span></span>

1.  <span data-ttu-id="268b1-145">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="268b1-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="268b1-146">Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="268b1-146">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>
    
        Set-CsNetworkSite -Identity <string>
    
    <span data-ttu-id="268b1-147">Exemple :</span><span class="sxs-lookup"><span data-stu-id="268b1-147">For example:</span></span>
    
        Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
    
    <span data-ttu-id="268b1-p104">Dans cet exemple, le site appelé « Albuquerque » est déplacé dans la région « NorthAmerica ». Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.</span><span class="sxs-lookup"><span data-stu-id="268b1-p104">In this example, the site called “Albuquerque” is moved to the “NorthAmerica” network region. To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="268b1-p105">Même si le paramètre BypassID existe pour la déviation du trafic multimédia, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="268b1-p105">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

    
    </div>

3.  <span data-ttu-id="268b1-152">Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="268b1-152">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-by-using-lync-server-control-panel"></a><span data-ttu-id="268b1-153">Pour modifier un site réseau en utilisant le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="268b1-153">To modify a network site by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="268b1-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="268b1-154">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="268b1-155">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="268b1-155">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="268b1-156">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="268b1-156">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="268b1-157">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="268b1-157">Click the **Site** navigation button.</span></span>

4.  <span data-ttu-id="268b1-158">Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="268b1-158">In the table, click the network site that you want to modify.</span></span>

5.  <span data-ttu-id="268b1-159">Cliquez sur **Modifier**, puis sur **Afficher les détails…**.</span><span class="sxs-lookup"><span data-stu-id="268b1-159">Click **Edit**, and then click **Show details…**.</span></span>

6.  <span data-ttu-id="268b1-160">Dans la page **Modifier le site**, changez les valeurs des paramètres de ce site réseau comme il convient.</span><span class="sxs-lookup"><span data-stu-id="268b1-160">On the **Edit Site** page, change the values for this network site’s settings as appropriate.</span></span>

7.  <span data-ttu-id="268b1-161">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="268b1-161">Click **Commit**.</span></span>

8.  <span data-ttu-id="268b1-162">Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="268b1-162">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

