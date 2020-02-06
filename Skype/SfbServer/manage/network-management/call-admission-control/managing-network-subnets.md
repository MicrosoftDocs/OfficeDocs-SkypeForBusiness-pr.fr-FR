---
title: Gestion des sous-réseaux réseau
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
description: Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.
ms.openlocfilehash: fd7d71b3971b176939967830ca3e071ef4c77dbf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817463"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="753b5-104">Gestion des sous-réseaux réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="753b5-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="753b5-105">Vous pouvez utiliser le panneau de configuration Skype entreprise Server ou Skype entreprise Server Management Shell pour gérer les sous-réseaux du réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="753b5-106">Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="753b5-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="753b5-107">Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="753b5-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="753b5-108">Les sections de cet article vous permettent d’afficher les informations de sous-réseau ou de créer, modifier ou supprimer des sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="753b5-109">Afficher les informations de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-109">View network subnet information</span></span> 

<span data-ttu-id="753b5-110">Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="753b5-111">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="753b5-112">Pour afficher un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-112">To view a network subnet</span></span>

1.  <span data-ttu-id="753b5-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="753b5-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="753b5-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="753b5-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="753b5-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="753b5-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="753b5-116">Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="753b5-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="753b5-117">Vous ne pouvez afficher qu’un seul sous-réseau à la fois.</span><span class="sxs-lookup"><span data-stu-id="753b5-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="753b5-118">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="753b5-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="753b5-119">Afficher les informations de configuration de sous-réseau en utilisant des applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="753b5-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="753b5-120">Les informations de sous-réseau peuvent être affichées à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="753b5-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="753b5-121">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="753b5-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="753b5-122">Pour afficher les informations de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-122">To view network subnet information</span></span>

  - <span data-ttu-id="753b5-123">Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="753b5-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="753b5-124">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="753b5-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="753b5-125">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="753b5-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="753b5-126">Créer ou modifier des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-126">Create or modify network subnets</span></span> 

<span data-ttu-id="753b5-127">Un sous-réseau doit être associé à un site réseau pour vous permettre de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="753b5-128">Le panneau de configuration Skype entreprise Server vous permet de configurer les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="753b5-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="753b5-129">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="753b5-130">Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="753b5-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="753b5-131">Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="753b5-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="753b5-132">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="753b5-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="753b5-133">L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="753b5-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="753b5-134">Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="753b5-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="753b5-135">Pour créer un sous-réseau du réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-135">To create a network subnet</span></span>

1.  <span data-ttu-id="753b5-136">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="753b5-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="753b5-137">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="753b5-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="753b5-138">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="753b5-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="753b5-139">Sur la page **sous-réseau** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="753b5-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="753b5-140">Dans **nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** .</span><span class="sxs-lookup"><span data-stu-id="753b5-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="753b5-141">Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0) et doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="753b5-142">Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.</span><span class="sxs-lookup"><span data-stu-id="753b5-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="753b5-143">Cette valeur correspond au masque de passe à appliquer au sous-réseau qui est créé.</span><span class="sxs-lookup"><span data-stu-id="753b5-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="753b5-144">Dans **ID du site réseau**, sélectionnez le site auquel appartient ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="753b5-145">Facultatif Tapez une valeur dans le champ **Description** pour fournir davantage d’informations sur ce sous-réseau qui ne peut pas être exprimé par le nom seul.</span><span class="sxs-lookup"><span data-stu-id="753b5-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="753b5-146">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="753b5-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="753b5-147">Pour modifier un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="753b5-148">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="753b5-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="753b5-149">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="753b5-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="753b5-150">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="753b5-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="753b5-151">Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="753b5-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="753b5-152">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="753b5-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="753b5-153">Dans la page **modifier le sous-réseau** , vous pouvez modifier le masque de la page, le site réseau associé ou la description.</span><span class="sxs-lookup"><span data-stu-id="753b5-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="753b5-154">Si vous modifiez le masque de réinitialisation, n’oubliez pas que l’ID de sous-réseau doit toujours être la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="753b5-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="753b5-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="753b5-156">Supprimer des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-156">Delete network subnets</span></span>

<span data-ttu-id="753b5-157">Vous pouvez utiliser la procédure suivante pour supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="753b5-158">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="753b5-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="753b5-159">Dans la plupart des déploiements de Skype entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il existe généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="753b5-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="753b5-160">Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="753b5-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="753b5-161">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="753b5-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="753b5-162">L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="753b5-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="753b5-163">Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="753b5-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="753b5-164">Pour supprimer un sous-réseau du réseau</span><span class="sxs-lookup"><span data-stu-id="753b5-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="753b5-165">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="753b5-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="753b5-166">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="753b5-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="753b5-167">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="753b5-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="753b5-168">Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="753b5-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="753b5-169">Vous pouvez supprimer plusieurs sous-réseaux à la fois.</span><span class="sxs-lookup"><span data-stu-id="753b5-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="753b5-170">Pour cela, appuyez sur CTRL et sélectionnez plusieurs sous-réseaux tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="753b5-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="753b5-171">Pour sélectionner tous les sous-réseaux, cliquez sur **tout sélectionner** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="753b5-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="753b5-172">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="753b5-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="753b5-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="753b5-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="753b5-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="753b5-174">See Also</span></span>

[<span data-ttu-id="753b5-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="753b5-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="753b5-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="753b5-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="753b5-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="753b5-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="753b5-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="753b5-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
