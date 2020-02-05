---
title: Déploiement de régions, de sites et de sous-réseaux réseau dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 'Créez ou modifiez des régions réseau, des sites réseau et associez des sous-réseaux réseau dans Skype entreprise Server. Tous ces éléments sont utilisés pour les fonctionnalités avancées de voix entreprise : contournement du contenu multimédia, contrôle d’admission des appels et routage basé sur l’emplacement.'
ms.openlocfilehash: e181e8fffc431db67e0e597f3e8dccba710efdd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767517"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="a07cf-104">Déploiement de régions, de sites et de sous-réseaux réseau dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="a07cf-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="a07cf-105">Créez ou modifiez des régions réseau, des sites réseau et associez des sous-réseaux réseau dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="a07cf-106">Tous ces éléments sont utilisés pour les fonctionnalités avancées de voix entreprise : contournement du contenu multimédia, contrôle d’admission des appels et routage basé sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="a07cf-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="a07cf-107">Les fonctionnalités avancées de voix entreprise sont le [contrôle d’admission des appels](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), le contournement du [média](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), le [routage géolocalisation](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)et [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span><span class="sxs-lookup"><span data-stu-id="a07cf-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="a07cf-108">Ces fonctionnalités vous obligent à créer toutes les régions réseau, sites réseau et sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="a07cf-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="a07cf-109">Par exemple, toutes ces fonctionnalités requièrent que chaque sous-réseau de votre topologie soit associé à un site réseau spécifique, et que chaque site réseau soit associé à une région réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="a07cf-110">Pour plus d’informations sur ces conditions, voir [paramètres réseau pour les fonctions avancées de voix entreprise dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="a07cf-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="a07cf-111">Le contrôle d’admission des appels et E9-1-1 ont des exigences de configuration supplémentaires pour les sites réseau :</span><span class="sxs-lookup"><span data-stu-id="a07cf-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="a07cf-112">Le contrôle d’admission des appels nécessite de spécifier un profil de stratégie de bande passante pour chaque site soumis à des restrictions de bande passante de réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="a07cf-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="a07cf-113">Si vous envisagez de déployer le contrôle d’admission des appels, vous devez [créer des profils de stratégie de bande passante dans Skype entreprise Server avant de](create-bandwidth-policy-profiles.md) configurer les sites de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="a07cf-114">E9-1-1 nécessite de spécifier une stratégie d’emplacement pour chaque site.</span><span class="sxs-lookup"><span data-stu-id="a07cf-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="a07cf-115">Si vous envisagez de déployer E9-1-1, vous devez [créer des stratégies d’emplacement dans Skype entreprise Server avant de](create-location-policies.md) configurer les sites de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="a07cf-116">Créer ou modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="a07cf-116">Create or modify a Network Region</span></span>

<span data-ttu-id="a07cf-117">Si vous avez déjà créé des régions réseau pour l’une de ces fonctionnalités, vous n’avez pas besoin de créer de nouvelles régions réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront les mêmes régions réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="a07cf-p106">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité. Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="a07cf-p106">You may, however, need to modify an existing network region definition to apply feature-specific settings. For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a07cf-120">Pour créer une région réseau à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a07cf-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a07cf-121">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a07cf-122">Exécutez l’applet de commande New-CsNetworkRegion pour créer des régions réseau :</span><span class="sxs-lookup"><span data-stu-id="a07cf-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="a07cf-123">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a07cf-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="a07cf-124">Dans cet exemple, vous avez créé une région réseau appelée « AmeriqueduNord » associée à un site central avec l’ID de site renne.</span><span class="sxs-lookup"><span data-stu-id="a07cf-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="a07cf-125">Pour finir de créer des régions réseau pour votre topologie, répétez l’étape 2 avec des paramètres pour chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a07cf-126">Pour créer une région réseau dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a07cf-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a07cf-127">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a07cf-128">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="a07cf-129">Cliquez sur **Région**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-129">Click **Region**.</span></span>

4. <span data-ttu-id="a07cf-130">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-130">Click **New**.</span></span>

5. <span data-ttu-id="a07cf-131">Dans la page **Nouvelle région**, cliquez sur **Nom**, puis tapez le nom de la région réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="a07cf-132">Cliquez sur **Site central**, puis cliquez sur un site central dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a07cf-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="a07cf-133">Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="a07cf-134">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-134">Click **Commit**.</span></span>

9. <span data-ttu-id="a07cf-135">Pour finir de créer des régions réseau pour votre topologie, répétez les étapes 4 à 8 avec des paramètres pour d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="a07cf-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a07cf-136">Pour modifier une région réseau à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a07cf-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a07cf-137">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a07cf-138">Exécutez l’applet de commande Set-CsNetworkRegion pour modifier une région réseau existante :</span><span class="sxs-lookup"><span data-stu-id="a07cf-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="a07cf-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a07cf-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="a07cf-140">Dans cet exemple, vous avez modifié une région réseau existante appelée « AmeriqueduNord » (créée à l’aide des procédures décrites plus haut dans cette rubrique) en modifiant la description.</span><span class="sxs-lookup"><span data-stu-id="a07cf-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="a07cf-141">S’il existait une description pour la région « AmeriqueduNord », cette commande remplace celle-ci par cette valeur ; Si aucune description n’a été définie, la commande définit celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a07cf-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="a07cf-142">Pour modifier d’autres régions réseau, répétez l’étape 2 avec les paramètres d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="a07cf-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a07cf-143">Pour modifier une région réseau dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a07cf-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a07cf-144">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a07cf-145">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="a07cf-146">Cliquez sur le bouton de navigation **Région**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="a07cf-147">Dans le tableau, cliquez sur la région réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="a07cf-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="a07cf-148">Cliquez sur **Modifier**, puis sur **Afficher les détails…**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="a07cf-149">Dans la page **modifier la région** , modifiez les valeurs des paramètres de cette région de réseau selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a07cf-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="a07cf-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-150">Click **Commit**.</span></span>

8. <span data-ttu-id="a07cf-151">Pour finir de modifier les régions réseau, répétez les étapes 4 à 7 avec des paramètres pour d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="a07cf-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="a07cf-152">Création ou modification d’un site réseau</span><span class="sxs-lookup"><span data-stu-id="a07cf-152">Create or modify a network site</span></span>

<span data-ttu-id="a07cf-153">Si vous avez déjà créé des sites réseau pour l’une de ces fonctionnalités, vous n’avez pas besoin de créer de nouveaux sites réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront ces mêmes sites réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="a07cf-154">Cependant, il est possible que vous soyez obligé de modifier la définition d’un site réseau existant pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="a07cf-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="a07cf-155">Par exemple, si vous avez créé un site réseau pour E9-1-1, vous devez modifier le site réseau au cours du déploiement du contrôle d’admission des appels pour appliquer un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="a07cf-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a07cf-156">Pour créer un site réseau à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a07cf-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a07cf-157">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a07cf-158">Exécutez l’applet de commande New-CsNetworkSite pour créer des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="a07cf-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="a07cf-159">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a07cf-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="a07cf-160">Dans cet exemple, vous avez créé un site réseau appelé « Lyon » qui se trouve dans la région réseau « AmeriqueduNord ».</span><span class="sxs-lookup"><span data-stu-id="a07cf-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a07cf-161">La région NorthAmerica doit toujours exister pour que cette commande s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="a07cf-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="a07cf-162">Pour finir de créer des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a07cf-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a07cf-163">Pour créer un site réseau en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a07cf-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a07cf-164">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a07cf-165">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="a07cf-166">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="a07cf-167">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-167">Click **New**.</span></span>

5. <span data-ttu-id="a07cf-168">Dans la page **Nouveau site**, cliquez sur **Nom**, puis tapez le nom du site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="a07cf-169">Cliquez sur **Région**, puis cliquez sur une région dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a07cf-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="a07cf-170">Éventuellement, cliquez sur **Stratégie de bande passante**, puis sur une stratégie de bande passante dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a07cf-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a07cf-171">La stratégie de bande passante est uniquement requise si vous déployez le contrôle d’admission des appels sur le site.</span><span class="sxs-lookup"><span data-stu-id="a07cf-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="a07cf-172">Éventuellement, cliquez sur **Stratégie d’emplacement**, puis sur une stratégie d’emplacement dans la liste.</span><span class="sxs-lookup"><span data-stu-id="a07cf-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a07cf-173">La stratégie d’emplacement est uniquement requise si vous déployez le système E9-1-1 sur le site.</span><span class="sxs-lookup"><span data-stu-id="a07cf-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="a07cf-174">Éventuellement, cliquez sur **Description**, puis tapez des informations supplémentaires pour décrire ce site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="a07cf-175">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-175">Click **Commit**.</span></span>

11. <span data-ttu-id="a07cf-176">Pour finir de créer des sites réseau pour votre topologie, répétez les étapes 4 à 10 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a07cf-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a07cf-177">Pour modifier un site réseau à l’aide de Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a07cf-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a07cf-178">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a07cf-179">Exécutez l’applet de commande Set-CsNetworkSite pour modifier des sites réseau :</span><span class="sxs-lookup"><span data-stu-id="a07cf-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="a07cf-180">Exemple :</span><span class="sxs-lookup"><span data-stu-id="a07cf-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="a07cf-181">Dans cet exemple, le site appelé « Albuquerque » est déplacé vers la région réseau « AmeriqueduNord ».</span><span class="sxs-lookup"><span data-stu-id="a07cf-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="a07cf-182">Pour modifier la configuration du site réseau afin de déployer le contrôle d’admission des appels, le système E9-1-1 ou la déviation du trafic multimédia, modifiez les paramètres du site réseau en exécutant l’applet de commande Set-CsNetworkSite avec le paramètre BWPolicyProfileID ou LocationPolicy, respectivement.</span><span class="sxs-lookup"><span data-stu-id="a07cf-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a07cf-p110">Même si le paramètre BypassID existe pour la déviation du trafic multimédia, nous vous recommandons vivement de ne pas remplacer les ID de contournement générés automatiquement. Vous n’avez pas besoin de spécifier des paramètres supplémentaires pour configurer un site réseau pour la déviation du trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="a07cf-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="a07cf-185">Pour finir de modifier des sites réseau pour votre topologie, répétez l’étape 2 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a07cf-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a07cf-186">Pour modifier un site réseau en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a07cf-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a07cf-187">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a07cf-188">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="a07cf-189">Cliquez sur le bouton de navigation **Site**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="a07cf-190">Dans le tableau, cliquez sur le site réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="a07cf-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="a07cf-191">Cliquez sur **Modifier**, puis sur **Afficher les détails…**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="a07cf-192">Dans la page **modifier le site** , modifiez les valeurs des paramètres de ce site de réseau selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a07cf-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="a07cf-193">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-193">Click **Commit**.</span></span>

8. <span data-ttu-id="a07cf-194">Pour finir de modifier les sites réseau, répétez les étapes 4 à 7 avec les paramètres pour d’autres sites.</span><span class="sxs-lookup"><span data-stu-id="a07cf-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="a07cf-195">Association d’un sous-réseau à un site réseau</span><span class="sxs-lookup"><span data-stu-id="a07cf-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="a07cf-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="a07cf-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="a07cf-197">Chaque sous-réseau de votre réseau doit être associé à un site réseau spécifique, car les informations de sous-réseau servent à définir le site réseau sur lequel figure un point de terminaison lorsqu’une nouvelle session est initiée.</span><span class="sxs-lookup"><span data-stu-id="a07cf-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="a07cf-198">Lorsque l’emplacement de chaque partie d’une session est connu, les fonctionnalités avancées de voix entreprise peuvent appliquer ces informations pour déterminer le mode de gestion de l’appel ou du routage.</span><span class="sxs-lookup"><span data-stu-id="a07cf-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="a07cf-199">Toutes les adresses IP publiques configurées des serveurs Edge audio/vidéo de votre déploiement doivent être ajoutées à vos paramètres de configuration réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="a07cf-200">Ces adresses IP sont ajoutées sous forme de sous-réseaux avec un masque de 32.</span><span class="sxs-lookup"><span data-stu-id="a07cf-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="a07cf-201">Le site réseau associé doit correspondre au site réseau configuré approprié.</span><span class="sxs-lookup"><span data-stu-id="a07cf-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="a07cf-202">Par exemple, l’adresse IP publique qui correspond au service Edge A/V dans le site central de Chicago serait NetworkSiteID Chicago.</span><span class="sxs-lookup"><span data-stu-id="a07cf-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a07cf-203">Pour associer un sous-réseau à un site réseau en utilisant Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a07cf-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="a07cf-204">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="a07cf-205">Exécutez l’applet de commande **New-CsNetworkSubnet** pour associer un sous-réseau à un site réseau :</span><span class="sxs-lookup"><span data-stu-id="a07cf-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="a07cf-206">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a07cf-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="a07cf-207">Dans cet exemple, vous avez créé une association entre le sous-réseau 172.11.12.13 et le site réseau « Chicago ».</span><span class="sxs-lookup"><span data-stu-id="a07cf-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="a07cf-208">Répétez l’étape 2 pour tous les sous-réseaux de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="a07cf-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="a07cf-209">Pour associer des sous-réseaux à des sites réseau en important un fichier CSV</span><span class="sxs-lookup"><span data-stu-id="a07cf-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="a07cf-p113">Créez un fichier CSV incluant tous les sous-réseaux que vous souhaitez ajouter. Par exemple, créez un fichier **subnet.csv** avec le contenu suivant :</span><span class="sxs-lookup"><span data-stu-id="a07cf-p113">Create a CSV file that includes all of the subnets you want to add. For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="a07cf-212">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="a07cf-213">Exécutez l’applet de commande suivante pour importer **subnet. csv**, puis stockez son contenu dans le magasin de gestion du serveur Lync :</span><span class="sxs-lookup"><span data-stu-id="a07cf-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a07cf-214">Pour associer un sous-réseau à un site réseau en utilisant le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a07cf-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a07cf-215">Ouvrez le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a07cf-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="a07cf-216">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="a07cf-217">Cliquez sur le bouton de navigation **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="a07cf-218">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-218">Click **New**.</span></span>

5. <span data-ttu-id="a07cf-219">Dans la page **Nouveau sous-réseau**, cliquez sur **ID de sous-réseau**, puis entrez la première adresse de la plage d’adresses IP définie par le sous-réseau que vous souhaitez associer à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="a07cf-220">Cliquez sur **Masque**, puis entrez le masque de bits à appliquer au sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="a07cf-221">Cliquez sur **ID de site réseau**, puis sélectionnez l’ID du site auquel vous ajoutez ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a07cf-222">Si vous n’avez pas encore créé de sites réseau, cette liste est vide.</span><span class="sxs-lookup"><span data-stu-id="a07cf-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="a07cf-223">Pour plus d’informations sur la procédure, reportez-vous à [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span><span class="sxs-lookup"><span data-stu-id="a07cf-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="a07cf-224">Vous pouvez également récupérer des ID de site pour votre déploiement en exécutant l’applet de commande **Get-CsNetworkSite**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="a07cf-225">Pour plus d’informations, reportez-vous à la documentation Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a07cf-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="a07cf-226">Éventuellement, cliquez sur **Description**, puis entrez des informations supplémentaires pour décrire ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="a07cf-227">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a07cf-227">Click **Commit**.</span></span>

<span data-ttu-id="a07cf-228">Répétez ces étapes pour ajouter d’autres sous-réseaux à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="a07cf-229">Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="a07cf-230">L’alerte n’est générée qu’une seule fois par période de huit heures.</span><span class="sxs-lookup"><span data-stu-id="a07cf-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="a07cf-231">Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="a07cf-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="a07cf-232">**Source** : Service de stratégie de bande passante (principal) CS</span><span class="sxs-lookup"><span data-stu-id="a07cf-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="a07cf-233">**Numéro d’événement** : 36034</span><span class="sxs-lookup"><span data-stu-id="a07cf-233">**Event number**: 36034</span></span>

 <span data-ttu-id="a07cf-234">**Niveau** : 2</span><span class="sxs-lookup"><span data-stu-id="a07cf-234">**Level**: 2</span></span>

 <span data-ttu-id="a07cf-235">**Description**: les sous-réseaux pour les adresses IP suivantes \<: une liste d'\> adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="a07cf-236">**Cause** : les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="a07cf-237">**Résolution** : ajoutez aux paramètres de configuration réseau les sous-réseaux correspondant à la liste des adresses IP et associez chaque sous-réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="a07cf-p116">Par exemple, si la liste d’adresses IP qui s’affiche dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :</span><span class="sxs-lookup"><span data-stu-id="a07cf-p116">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="a07cf-240">Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="a07cf-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="a07cf-241">Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="a07cf-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="a07cf-242">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a07cf-242">See also</span></span>
<span data-ttu-id="a07cf-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="a07cf-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="a07cf-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a07cf-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="a07cf-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a07cf-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="a07cf-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a07cf-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="a07cf-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="a07cf-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="a07cf-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="a07cf-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="a07cf-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="a07cf-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="a07cf-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="a07cf-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="a07cf-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="a07cf-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

