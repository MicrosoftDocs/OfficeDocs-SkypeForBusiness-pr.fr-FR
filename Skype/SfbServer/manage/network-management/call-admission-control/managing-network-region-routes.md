---
title: Gestion des itinéraires de région réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Un itinéraire de région réseau définit l’itinéraire entre une paire de régions réseau. Chaque paire de régions de réseau dans votre déploiement du contrôle d’admission des appels nécessite un itinéraire de région réseau.
ms.openlocfilehash: 53b6383e08196fb22784f3fcd1e8d797c9b138de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888848"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="bb2fd-104">Gestion d’itinéraires de région réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb2fd-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="bb2fd-105">Un *itinéraire de région réseau* définit l’itinéraire entre une paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="bb2fd-106">Chaque paire de régions de réseau dans votre déploiement du contrôle d’admission des appels nécessite un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="bb2fd-107">Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="bb2fd-108">Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="bb2fd-109">Affichage des informations d’itinéraire de région de réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-109">View network region route information</span></span> 

<span data-ttu-id="bb2fd-110">Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="bb2fd-111">Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="bb2fd-112">Utilisez les procédures suivantes pour afficher les itinéraires de région réseau existante dans Skype pour le panneau de configuration serveur Business ou Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="bb2fd-113">Pour afficher des informations d’itinéraire de région de réseau de Business Server Control Panel dans Skype</span><span class="sxs-lookup"><span data-stu-id="bb2fd-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="bb2fd-114">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb2fd-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bb2fd-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bb2fd-117">Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="bb2fd-118">Vous ne pouvez afficher qu’un itinéraire de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="bb2fd-119">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bb2fd-120">Affichage des informations d’itinéraire de région réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb2fd-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bb2fd-121">Informations d’itinéraire de région de réseau peuvent être affichées à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkInterRegionRoute.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="bb2fd-122">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="bb2fd-123">Pour afficher les informations d’itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-123">To view network region route information</span></span>

  - <span data-ttu-id="bb2fd-124">Pour afficher des informations sur tous vos itinéraires de région réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="bb2fd-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="bb2fd-125">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="bb2fd-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="bb2fd-126">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="bb2fd-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="bb2fd-127">Créer ou modifier des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-127">Create or modify network region routes</span></span>

<span data-ttu-id="bb2fd-128">Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="bb2fd-129">Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="bb2fd-130">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="bb2fd-131">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="bb2fd-132">Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="bb2fd-133">Pour créer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-133">To create a network region route</span></span>

1.  <span data-ttu-id="bb2fd-134">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb2fd-135">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bb2fd-136">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bb2fd-137">Dans la page **Itinéraire de région** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="bb2fd-138">Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="bb2fd-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="bb2fd-139">Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="bb2fd-140">À partir de la **région réseau \#1** liste déroulante, sélectionnez une des deux régions à connecter par cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="bb2fd-141">À partir de la **région réseau \#2** liste déroulante, sélectionnez l’autre région pour cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="bb2fd-142">Cette zone doit être différente de la région sélectionnée pour la région de réseau \#1.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="bb2fd-143">Pour ajouter des liens de région à l’itinéraire, utilisez la zone de liste de **liens de région réseau** .</span><span class="sxs-lookup"><span data-stu-id="bb2fd-143">Use the **Network region links** list box to add region links to the route.</span></span> <span data-ttu-id="bb2fd-144">Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région** .</span><span class="sxs-lookup"><span data-stu-id="bb2fd-144">Click the **Add** button to display the **Region Link** page.</span></span> <span data-ttu-id="bb2fd-145">Cliquez sur un lien de région à ajouter à cet itinéraire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-145">Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="bb2fd-146">Continuez à cliquer sur le bouton **Ajouter** pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur **Supprimer** pour supprimer un lien.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="bb2fd-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="bb2fd-148">Pour modifier un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-148">To modify a network region route</span></span>

1.  <span data-ttu-id="bb2fd-149">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb2fd-150">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bb2fd-151">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bb2fd-152">Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="bb2fd-153">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="bb2fd-154">Dans **Modifier la région itinéraire**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région associés à l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="bb2fd-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="bb2fd-156">Supprimer les itinéraires de région réseau existante</span><span class="sxs-lookup"><span data-stu-id="bb2fd-156">Delete existing network region routes</span></span>

<span data-ttu-id="bb2fd-157">Chaque région au sein d’une configuration d’admission des appels (CAC) de contrôle doit avoir un moyen pour accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="bb2fd-158">Liens de région définir des restrictions de bande passante sur les connexions entre les régions et également représentent les liens physiques, un itinéraire détermine le chemin lié la connexion sera aller d’une région à l’autre.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="bb2fd-159">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="bb2fd-160">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="bb2fd-161">Utilisez cette rubrique pour supprimer les itinéraires de région réseau existante.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="bb2fd-162">Pour supprimer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="bb2fd-162">To delete a network region route</span></span>

1.  <span data-ttu-id="bb2fd-163">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bb2fd-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="bb2fd-165">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bb2fd-166">Dans la page **Itinéraire de région** , cliquez sur l’itinéraire de région que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="bb2fd-167">Vous pouvez supprimer plusieurs itinéraires de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-167">You can delete more than one region route at a time.</span></span> <span data-ttu-id="bb2fd-168">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs itinéraires de région tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-168">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="bb2fd-169">Ou, pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="bb2fd-169">Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="bb2fd-170">Dans le menu **Edition** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="bb2fd-171">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb2fd-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="bb2fd-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb2fd-172">See Also</span></span>

[<span data-ttu-id="bb2fd-173">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="bb2fd-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="bb2fd-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bb2fd-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="bb2fd-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bb2fd-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="bb2fd-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bb2fd-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="bb2fd-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="bb2fd-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
