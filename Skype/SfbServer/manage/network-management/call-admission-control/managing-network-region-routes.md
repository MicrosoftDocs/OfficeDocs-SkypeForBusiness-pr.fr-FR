---
title: Gestion des itinéraires de région réseau
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Un itinéraire de région réseau définit l’itinéraire entre deux régions réseau. Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire de région réseau.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816434"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a><span data-ttu-id="315bd-104">Gestion d’itinéraires de région réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="315bd-104">Managing network region routes in Skype for Business Server</span></span>

<span data-ttu-id="315bd-105">Un *itinéraire de région réseau* définit l’itinéraire entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-105">A *network region route* defines the route between a pair of network regions.</span></span> <span data-ttu-id="315bd-106">Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels requiert un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-106">Each pair of network regions in your call admission control deployment requires a network region route.</span></span> <span data-ttu-id="315bd-107">Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="315bd-107">This enables every network region within the deployment to access every other region.</span></span> <span data-ttu-id="315bd-108">Utilisez les procédures de cette artilce pour afficher, créer, modifier ou supprimer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-108">Use the procedures in this artilce to view, create, modify, or delete network region routes.</span></span>

## <a name="view-network-region-route-information"></a><span data-ttu-id="315bd-109">Afficher les informations d’itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-109">View network region route information</span></span> 

<span data-ttu-id="315bd-110">Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="315bd-110">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="315bd-111">Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="315bd-111">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="315bd-112">Utilisez les procédures suivantes pour afficher les itinéraires de région réseau existants dans le Panneau de contrôle Skype Entreprise Server ou Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="315bd-112">Use the following procedures to view existing network region routes in Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="315bd-113">Pour afficher les informations d’itinéraire de région réseau dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="315bd-113">To view network region route information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="315bd-114">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="315bd-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="315bd-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="315bd-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="315bd-116">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**</span><span class="sxs-lookup"><span data-stu-id="315bd-116">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="315bd-117">Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="315bd-117">On the **Region Route** page, click the region route that you want to view.</span></span>


    > [!NOTE]  
    > <span data-ttu-id="315bd-118">Vous ne pouvez afficher qu’un itinéraire de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="315bd-118">You can only view one region route at a time.</span></span>


5.  <span data-ttu-id="315bd-119">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="315bd-119">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="315bd-120">Affichage des informations d’itinéraire de région réseau à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="315bd-120">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="315bd-121">Les informations d’itinéraire de région réseau peuvent être vues à l’Windows PowerShell l'Get-CsNetworkInterRegionRoute cmdlet.</span><span class="sxs-lookup"><span data-stu-id="315bd-121">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="315bd-122">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="315bd-122">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-route-information"></a><span data-ttu-id="315bd-123">Pour afficher les informations d’itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-123">To view network region route information</span></span>

  - <span data-ttu-id="315bd-124">Pour afficher des informations sur tous vos itinéraires de région réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="315bd-124">To view information about all your network region routes, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="315bd-125">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="315bd-125">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

<span data-ttu-id="315bd-126">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).</span><span class="sxs-lookup"><span data-stu-id="315bd-126">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>


## <a name="create-or-modify-network-region-routes"></a><span data-ttu-id="315bd-127">Créer ou modifier des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-127">Create or modify network region routes</span></span>

<span data-ttu-id="315bd-128">Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="315bd-128">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="315bd-129">Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="315bd-129">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="315bd-130">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-130">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="315bd-131">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-131">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="315bd-132">Utilisez cette rubrique pour créer ou modifier un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-132">Use this topic to create or modify a network region route.</span></span> 

### <a name="to-create-a-network-region-route"></a><span data-ttu-id="315bd-133">Pour créer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-133">To create a network region route</span></span>

1.  <span data-ttu-id="315bd-134">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="315bd-134">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="315bd-135">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="315bd-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="315bd-136">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**</span><span class="sxs-lookup"><span data-stu-id="315bd-136">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="315bd-137">Dans la page **Itinéraire de région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="315bd-137">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="315bd-138">Dans **Nouvel itinéraire de région**, tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="315bd-138">In **New Region Route**, type a value in the **Name** field.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="315bd-139">Cette valeur doit être unique dans votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="315bd-139">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="315bd-140">Dans la liste de listes bas Région réseau **\# 1,** sélectionnez l’une des deux régions à connecter par cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="315bd-140">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="315bd-141">Dans la liste de listes bas Région réseau **\# 2,** sélectionnez l’autre région pour cet itinéraire.</span><span class="sxs-lookup"><span data-stu-id="315bd-141">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="315bd-142">Cette région doit être différente de la région sélectionnée pour la région \# réseau 1.</span><span class="sxs-lookup"><span data-stu-id="315bd-142">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="315bd-p107">Utilisez la zone de liste **Liens de région réseau** pour ajouter des liens de région à l’itinéraire. Cliquez sur le bouton **Ajouter** pour afficher la page **Lien de région**. Cliquez sur un lien de région pour l’ajouter à cet itinéraire, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="315bd-p107">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="315bd-146">Continuez à cliquer sur le bouton **Ajouter** pour ajouter davantage de liens, ou sélectionnez un lien et cliquez sur **Supprimer** pour le supprimer.</span><span class="sxs-lookup"><span data-stu-id="315bd-146">Continue to click the **Add** button to add more links, or select a link and click **Remove** to remove a link.</span></span>

9.  <span data-ttu-id="315bd-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="315bd-147">Click **Commit**.</span></span>


### <a name="to-modify-a-network-region-route"></a><span data-ttu-id="315bd-148">Pour modifier un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-148">To modify a network region route</span></span>

1.  <span data-ttu-id="315bd-149">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="315bd-149">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="315bd-150">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="315bd-150">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="315bd-151">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**</span><span class="sxs-lookup"><span data-stu-id="315bd-151">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="315bd-152">Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="315bd-152">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="315bd-153">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="315bd-153">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="315bd-154">Dans **Modifier l’itinéraire de région**, vous pouvez modifier les régions liées par cet itinéraire et les liens de région qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="315bd-154">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="315bd-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="315bd-155">Click **Commit**.</span></span>


## <a name="delete-existing-network-region-routes"></a><span data-ttu-id="315bd-156">Supprimer des itinéraires de région réseau existants</span><span class="sxs-lookup"><span data-stu-id="315bd-156">Delete existing network region routes</span></span>

<span data-ttu-id="315bd-157">Chaque région au sein d’un contrôle d’admission des appels doit disposer d’un moyen lui permettant d’accéder à toutes les autres régions.</span><span class="sxs-lookup"><span data-stu-id="315bd-157">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="315bd-158">Alors que les liens de région définissent des restrictions de bande passante sur les connexions entre les régions et qu’ils représentent également des liens physiques, un itinéraire détermine le chemin lié que la connexion traverse d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="315bd-158">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="315bd-159">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des itinéraires de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-159">You can use the Skype for Business Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="315bd-160">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un itinéraire de région réseau.</span><span class="sxs-lookup"><span data-stu-id="315bd-160">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="315bd-161">Utilisez cette rubrique pour supprimer des itinéraires de région réseau existants.</span><span class="sxs-lookup"><span data-stu-id="315bd-161">Use this topic to delete existing network region routes.</span></span> 

### <a name="to-delete-a-network-region-route"></a><span data-ttu-id="315bd-162">Pour supprimer un itinéraire de région réseau</span><span class="sxs-lookup"><span data-stu-id="315bd-162">To delete a network region route</span></span>

1.  <span data-ttu-id="315bd-163">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="315bd-163">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="315bd-164">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="315bd-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="315bd-165">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Itinéraire de région.**</span><span class="sxs-lookup"><span data-stu-id="315bd-165">In the left navigation bar, click **Network Configuration**, and then click **Region Route**.</span></span>

4.  <span data-ttu-id="315bd-166">Dans la page **Itinéraire de région**, cliquez sur l’itinéraire de région à supprimer.</span><span class="sxs-lookup"><span data-stu-id="315bd-166">On the **Region Route** page, click the region route that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="315bd-p109">Vous pouvez supprimer plusieurs itinéraires de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs itinéraires de région. Ou, pour sélectionner tous les itinéraires de région, cliquez sur **Sélectionner tout** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="315bd-p109">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="315bd-170">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="315bd-170">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="315bd-171">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="315bd-171">Click **OK**.</span></span>



## <a name="see-also"></a><span data-ttu-id="315bd-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="315bd-172">See Also</span></span>

[<span data-ttu-id="315bd-173">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="315bd-173">Managing network regions in Skype for Business Server</span></span>](managing-network-regions.md)

[<span data-ttu-id="315bd-174">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="315bd-174">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[<span data-ttu-id="315bd-175">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="315bd-175">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[<span data-ttu-id="315bd-176">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="315bd-176">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[<span data-ttu-id="315bd-177">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="315bd-177">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
