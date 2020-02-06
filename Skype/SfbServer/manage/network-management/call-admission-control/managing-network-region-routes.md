---
title: Gestion des itinéraires de région réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Un itinéraire de région réseau définit l’itinéraire entre deux régions du réseau. Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire de la région du réseau.
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817493"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="9639f-104">Gestion d’itinéraires de région réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9639f-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="9639f-105">Un *itinéraire de région réseau* définit l’itinéraire entre deux régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="9639f-106">Chaque paire de zones réseau dans le déploiement de votre contrôle d’admission des appels nécessite un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="9639f-107">Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="9639f-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="9639f-108">Les procédures décrites dans cet Artilce vous permettent d’afficher, de créer, de modifier ou de supprimer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="9639f-109">Afficher les informations sur les itinéraires de la région réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-109">View network region route information</span></span> 

<span data-ttu-id="9639f-110">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="9639f-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9639f-111">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="9639f-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9639f-112">Utilisez les procédures suivantes pour afficher les itinéraires des régions réseau existantes dans le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="9639f-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="9639f-113">Pour afficher les informations sur le routage de la région réseau dans Skype entreprise Server panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="9639f-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9639f-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9639f-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9639f-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9639f-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9639f-116">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="9639f-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9639f-117">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="9639f-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="9639f-118">Vous pouvez uniquement afficher un itinéraire par région à la fois.</span><span class="sxs-lookup"><span data-stu-id="9639f-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="9639f-119">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9639f-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9639f-120">Affichage des informations sur les itinéraires de région réseau à l’aide d’applets de requête Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9639f-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9639f-121">Les informations sur les itinéraires de région réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de requête get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="9639f-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="9639f-122">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9639f-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="9639f-123">Pour afficher les informations relatives aux itinéraires de la région réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-123">To view network region route information</span></span>

  - <span data-ttu-id="9639f-124">Pour afficher des informations sur l’ensemble des itinéraires de vos régions réseau, tapez la commande suivante dans le shell de gestion de Skype entreprise Server, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="9639f-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="9639f-125">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="9639f-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="9639f-126">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="9639f-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="9639f-127">Créer ou modifier des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-127">Create or modify network region routes</span></span>

<span data-ttu-id="9639f-128">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="9639f-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9639f-129">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="9639f-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9639f-130">Le panneau de configuration Skype entreprise Server vous permet de configurer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9639f-131">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9639f-132">Utilisez cette rubrique pour créer ou modifier un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="9639f-133">Pour créer un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-133">To create a network region route</span></span>

1.  <span data-ttu-id="9639f-134">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9639f-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9639f-135">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9639f-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9639f-136">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="9639f-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9639f-137">Sur la page itinéraire de la **région** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9639f-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="9639f-138">Dans la **zone nouvel itinéraire**de la région, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="9639f-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="9639f-139">Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9639f-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="9639f-140">Dans la liste déroulante \*\* \#région de réseau 1\*\* , sélectionnez l’une des deux régions auxquelles vous voulez être connectée par cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="9639f-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="9639f-141">Dans la liste déroulante de la \*\* \#région réseau 2\*\* , sélectionnez une autre région pour ce routage.</span><span class="sxs-lookup"><span data-stu-id="9639f-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="9639f-142">Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.</span><span class="sxs-lookup"><span data-stu-id="9639f-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="9639f-143">Utilisez la zone de liste **liaisons de région réseau** pour ajouter des liens de région à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="9639f-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="9639f-144">Cliquez sur le bouton **Ajouter** pour afficher la page de liaison de la **zone** .</span><span class="sxs-lookup"><span data-stu-id="9639f-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="9639f-145">Cliquez sur le lien d’une région pour l’ajouter à ce routage, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9639f-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="9639f-146">Continuez à cliquer sur le bouton **Ajouter** pour ajouter d’autres liens, ou sélectionnez un lien et cliquez sur **supprimer** pour supprimer un lien.</span><span class="sxs-lookup"><span data-stu-id="9639f-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="9639f-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9639f-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="9639f-148">Pour modifier un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-148">To modify a network region route</span></span>

1.  <span data-ttu-id="9639f-149">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9639f-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9639f-150">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9639f-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9639f-151">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="9639f-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9639f-152">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="9639f-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="9639f-153">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="9639f-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="9639f-154">Dans la **zone modifier le routage**des régions, vous pouvez modifier les régions jointes par cet itinéraire et les liaisons de région associées à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="9639f-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="9639f-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9639f-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="9639f-156">Supprimer des itinéraires de région réseau existants</span><span class="sxs-lookup"><span data-stu-id="9639f-156">Delete existing network region routes</span></span>

<span data-ttu-id="9639f-157">Chaque région au sein d’une configuration de contrôle d’admission des appels (CAC) doit disposer d’un moyen d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="9639f-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="9639f-158">Lorsque les liaisons de zone définissent des limitations de bande passante pour les connexions entre les régions et représentent également les liens physiques, un itinéraire détermine le chemin d’accès lié que la connexion traverse d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="9639f-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="9639f-159">Le panneau de configuration Skype entreprise Server vous permet de configurer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="9639f-160">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de la région du réseau.</span><span class="sxs-lookup"><span data-stu-id="9639f-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="9639f-161">Utilisez cette rubrique pour supprimer des itinéraires de la région de réseau existants.</span><span class="sxs-lookup"><span data-stu-id="9639f-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="9639f-162">Pour supprimer un itinéraire de la région du réseau</span><span class="sxs-lookup"><span data-stu-id="9639f-162">To delete a network region route</span></span>

1.  <span data-ttu-id="9639f-163">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9639f-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9639f-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="9639f-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="9639f-165">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **itinéraire des régions**.</span><span class="sxs-lookup"><span data-stu-id="9639f-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="9639f-166">Sur la page itinéraire de la **région** , cliquez sur le secteur que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="9639f-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="9639f-167">Vous pouvez supprimer plusieurs itinéraires par région à la fois.</span><span class="sxs-lookup"><span data-stu-id="9639f-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="9639f-168">Pour cela, appuyez sur CTRL et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="9639f-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="9639f-169">Pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **édition** .</span><span class="sxs-lookup"><span data-stu-id="9639f-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="9639f-170">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="9639f-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="9639f-171">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9639f-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="9639f-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9639f-172">See Also</span></span>

[<span data-ttu-id="9639f-173">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="9639f-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="9639f-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9639f-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9639f-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9639f-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="9639f-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9639f-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="9639f-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="9639f-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
