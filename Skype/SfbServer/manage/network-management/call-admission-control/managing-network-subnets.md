---
title: Gestion des sous-réseaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.
ms.openlocfilehash: 7b09428f3bdc44f8626cac072b5f4838e08f9efc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913355"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="dc4ae-104">Gestion des sous-réseaux réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="dc4ae-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="dc4ae-105">Vous pouvez utiliser soit le Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell pour gérer les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="dc4ae-106">Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="dc4ae-107">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="dc4ae-108">Utilisez les sections de cet article pour afficher les informations de sous-réseau de réseau ou créer, modifier ou supprimer des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="dc4ae-109">Afficher les informations de sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-109">View network subnet information</span></span> 

<span data-ttu-id="dc4ae-110">Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau de réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="dc4ae-111">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="dc4ae-112">Pour afficher un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-112">To view a network subnet</span></span>

1.  <span data-ttu-id="dc4ae-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc4ae-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc4ae-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc4ae-116">Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="dc4ae-117">Vous ne pouvez afficher qu’un seul sous-réseau à la fois.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="dc4ae-118">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc4ae-119">Afficher les informations de configuration de sous-réseau de réseau à l’aide de cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc4ae-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dc4ae-120">Informations relatives au sous-réseau peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="dc4ae-121">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="dc4ae-122">Pour afficher les informations de sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-122">To view network subnet information</span></span>

  - <span data-ttu-id="dc4ae-123">Pour afficher des informations sur tous les sous-réseaux de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="dc4ae-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="dc4ae-124">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="dc4ae-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="dc4ae-125">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) .</span><span class="sxs-lookup"><span data-stu-id="dc4ae-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="dc4ae-126">Créer ou modifier des sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="dc4ae-126">Create or modify network subnets</span></span> 

<span data-ttu-id="dc4ae-127">Un sous-réseau de réseau doit être associé à un site réseau à des fins de détermination de l’emplacement géographique de l’hôte appartenant à ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="dc4ae-128">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="dc4ae-129">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="dc4ae-130">Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="dc4ae-131">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="dc4ae-132">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="dc4ae-133">L’utilisation conjointe de ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="dc4ae-134">Pour obtenir des exemples illustrant comment créer des sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="dc4ae-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="dc4ae-135">Pour créer un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-135">To create a network subnet</span></span>

1.  <span data-ttu-id="dc4ae-136">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc4ae-137">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc4ae-138">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc4ae-139">Dans la page **sous-réseau** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="dc4ae-140">Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** .</span><span class="sxs-lookup"><span data-stu-id="dc4ae-140">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="dc4ae-141">Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), et elle doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-141">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="dc4ae-142">Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="dc4ae-143">Cette valeur est le masque de bits à appliquer au sous-réseau créé.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="dc4ae-144">**ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="dc4ae-145">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau ne suffit pas au nom seul.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="dc4ae-146">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="dc4ae-147">Pour modifier un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="dc4ae-148">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc4ae-149">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc4ae-150">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc4ae-151">Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="dc4ae-152">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="dc4ae-153">Dans la page **Modifier un sous-réseau** , vous pouvez modifier le masque de bits, le site réseau associé ou la description.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-153">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="dc4ae-154">Si vous modifiez le masque de bits, n’oubliez pas que l’ID de sous-réseau doit être toujours la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-154">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="dc4ae-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="dc4ae-156">Supprimer les sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="dc4ae-156">Delete network subnets</span></span>

<span data-ttu-id="dc4ae-157">Vous pouvez utiliser la procédure suivante pour supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="dc4ae-158">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer un sous-réseau de réseau.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="dc4ae-159">Dans la plupart des déploiements Skype pour Business Server où le contrôle d’admission des appels (CAC) est implémenté, généralement sera un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="dc4ae-160">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="dc4ae-161">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de commande Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="dc4ae-162">L’utilisation conjointe de ces applets de commande, vous pouvez lire les paramètres de sous-réseau dans un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="dc4ae-163">Pour obtenir des exemples illustrant comment créer des sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="dc4ae-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="dc4ae-164">Pour supprimer un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="dc4ae-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="dc4ae-165">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc4ae-166">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc4ae-167">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="dc4ae-168">Dans la page **sous-réseau** , cliquez sur le sous-réseau que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="dc4ae-169">Vous pouvez supprimer plusieurs sous-réseaux à la fois.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-169">You can delete more than one subnet at a time.</span></span> <span data-ttu-id="dc4ae-170">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs sous-réseaux tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-170">To do this, press CTRL and select multiple subnets while holding down the CTRL key.</span></span> <span data-ttu-id="dc4ae-171">Ou, pour sélectionner tous les sous-réseaux, cliquez sur **Sélectionner tout** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="dc4ae-171">Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="dc4ae-172">Dans le menu **Edition** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="dc4ae-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc4ae-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="dc4ae-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dc4ae-174">See Also</span></span>

[<span data-ttu-id="dc4ae-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc4ae-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="dc4ae-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc4ae-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="dc4ae-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc4ae-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="dc4ae-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dc4ae-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
