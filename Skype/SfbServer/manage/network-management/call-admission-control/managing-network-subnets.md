---
title: Gestion des sous-réseaux
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
description: Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux. Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.
ms.openlocfilehash: e2ac69190ab93b4b6d81fed13538cc6fcaa91f20
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816394"
---
# <a name="managing-network-subnets-in-skype-for-business-server"></a><span data-ttu-id="068d8-104">Gestion des sous-réseaux réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="068d8-104">Managing network subnets in Skype for Business Server</span></span>

<span data-ttu-id="068d8-105">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server ou Skype Entreprise Server Management Shell pour gérer les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-105">You can use either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell to manage network subnets.</span></span> <span data-ttu-id="068d8-106">Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-106">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="068d8-107">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="068d8-107">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="068d8-108">Utilisez les sections de cet article pour afficher des informations sur les sous-réseaux ou créer, modifier ou supprimer des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-108">Use the sections in this article to view network subnet information or create, modify, or delete network subnets.</span></span> 

## <a name="view-network-subnet-information"></a><span data-ttu-id="068d8-109">Afficher les informations de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-109">View network subnet information</span></span> 

<span data-ttu-id="068d8-110">Vous pouvez utiliser la procédure suivante pour afficher un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-110">You can use the following procedure to view a network subnet.</span></span> <span data-ttu-id="068d8-111">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-111">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

### <a name="to-view-a-network-subnet"></a><span data-ttu-id="068d8-112">Pour afficher un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-112">To view a network subnet</span></span>

1.  <span data-ttu-id="068d8-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="068d8-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d8-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="068d8-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d8-115">Dans la barre de navigation de gauche, cliquez sur **Configuration** réseau, puis sur **Sous-réseau.**</span><span class="sxs-lookup"><span data-stu-id="068d8-115">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="068d8-116">Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="068d8-116">On the **Subnet** page, click the subnet that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="068d8-117">Vous ne pouvez afficher qu’un seul sous-réseau à la fois.</span><span class="sxs-lookup"><span data-stu-id="068d8-117">You can only view one subnet at a time.</span></span>

5.  <span data-ttu-id="068d8-118">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="068d8-118">On the **Edit** menu, click **Show details**.</span></span>

### <a name="view-network-subnet-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="068d8-119">Afficher les informations de configuration de sous-réseau à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="068d8-119">View network subnet configuration information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="068d8-120">Les informations de sous-réseau peuvent être vues à l’aide Windows PowerShell et de la cmdlet Get-CsNetworkSubnet réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-120">Network subnet information can be viewed by using Windows PowerShell and the Get-CsNetworkSubnet cmdlet.</span></span> <span data-ttu-id="068d8-121">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="068d8-121">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-subnet-information"></a><span data-ttu-id="068d8-122">Pour afficher les informations de sous-réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-122">To view network subnet information</span></span>

  - <span data-ttu-id="068d8-123">Pour afficher des informations sur tous vos sous-réseaux, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="068d8-123">To view information about all your network subnets, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSubnet
    
    <span data-ttu-id="068d8-124">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="068d8-124">That will return information similar to this:</span></span>
    
        Identity      : 172.11.15.0
        MaskBits      : 28
        Description   :
        NetworkSiteID : Redmond
        SubnetID      : 172.11.15.0


<span data-ttu-id="068d8-125">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="068d8-125">For more information, see the help topic for the [Get-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet) cmdlet.</span></span>


## <a name="create-or-modify-network-subnets"></a><span data-ttu-id="068d8-126">Créer ou modifier des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-126">Create or modify network subnets</span></span> 

<span data-ttu-id="068d8-127">Un sous-réseau de réseau doit être associé à un site réseau afin de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-127">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="068d8-128">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-128">You can use the Skype for Business Server Control Panel to configure subnets.</span></span> <span data-ttu-id="068d8-129">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-129">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="068d8-130">Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-130">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="068d8-131">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="068d8-131">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="068d8-132">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’Windows PowerShell cmdlet **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="068d8-132">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="068d8-133">En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="068d8-133">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="068d8-134">Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="068d8-134">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-create-a-network-subnet"></a><span data-ttu-id="068d8-135">Pour créer un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-135">To create a network subnet</span></span>

1.  <span data-ttu-id="068d8-136">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="068d8-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d8-137">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="068d8-137">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d8-138">Dans la barre de navigation de gauche, cliquez sur **Configuration** réseau, puis sur **Sous-réseau.**</span><span class="sxs-lookup"><span data-stu-id="068d8-138">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="068d8-139">Dans la page **Sous-réseau**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="068d8-139">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="068d8-p107">Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau**. Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), qui doit être la première adresse dans la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-p107">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="068d8-142">Dans le champ **Masque**, entrez une valeur numérique comprise entre 1 et 32.</span><span class="sxs-lookup"><span data-stu-id="068d8-142">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="068d8-143">Cette valeur est le masque de bits à appliquer au sous-réseau en cours de création.</span><span class="sxs-lookup"><span data-stu-id="068d8-143">This value is the bitmask that is to be applied to the subnet being created.</span></span>

7.  <span data-ttu-id="068d8-144">Dans le champ **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.</span><span class="sxs-lookup"><span data-stu-id="068d8-144">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="068d8-145">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau, car son nom ne suffit pas à le décrire.</span><span class="sxs-lookup"><span data-stu-id="068d8-145">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="068d8-146">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="068d8-146">Click **Commit**.</span></span>


### <a name="to-modify-a-network-subnet"></a><span data-ttu-id="068d8-147">Pour modifier un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-147">To modify a network subnet</span></span>

1.  <span data-ttu-id="068d8-148">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="068d8-148">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d8-149">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="068d8-149">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d8-150">Dans la barre de navigation de gauche, cliquez sur **Configuration** réseau, puis sur **Sous-réseau.**</span><span class="sxs-lookup"><span data-stu-id="068d8-150">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="068d8-151">Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="068d8-151">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="068d8-152">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="068d8-152">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="068d8-p108">Dans la page **Modifier le sous-réseau**, vous pouvez modifier le masque de bits, le site réseau associé ou la description du sous-réseau. Si vous modifiez le masque de bits, n’oubliez pas que l’ID du sous-réseau doit toujours être la première adresse dans la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-p108">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="068d8-155">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="068d8-155">Click **Commit**.</span></span>

## <a name="delete-network-subnets"></a><span data-ttu-id="068d8-156">Supprimer des sous-réseaux réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-156">Delete network subnets</span></span>

<span data-ttu-id="068d8-157">La procédure suivante vous permet de supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-157">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="068d8-158">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="068d8-158">From the Skype for Business Server Control Panel, you can create, modify, or delete a network subnet.</span></span> 

<span data-ttu-id="068d8-159">Dans la plupart des déploiements de Skype Entreprise Server où le contrôle d’admission des appels (CAC) est implémenté, il y a généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="068d8-159">In most deployments of Skype for Business Server where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="068d8-160">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="068d8-160">Because of this, it is often best to configure subnets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="068d8-161">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’Windows PowerShell cmdlet **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="068d8-161">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="068d8-162">En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (.csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="068d8-162">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="068d8-163">Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier .csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="068d8-163">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>


### <a name="to-delete-a-network-subnet"></a><span data-ttu-id="068d8-164">Pour supprimer un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="068d8-164">To delete a network subnet</span></span>

1.  <span data-ttu-id="068d8-165">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="068d8-165">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="068d8-166">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="068d8-166">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="068d8-167">Dans la barre de navigation de gauche, cliquez sur **Configuration** réseau, puis sur **Sous-réseau.**</span><span class="sxs-lookup"><span data-stu-id="068d8-167">In the left navigation bar, click **Network Configuration**, and then click **Subnet**.</span></span>

4.  <span data-ttu-id="068d8-168">Dans la page **Sous-réseau**, cliquez sur le sous-réseau à supprimer.</span><span class="sxs-lookup"><span data-stu-id="068d8-168">On the **Subnet** page, click the subnet that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="068d8-p111">Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez les différents sous-réseaux à supprimer. Pour sélectionner la totalité des sous-réseaux, cliquez sur **Sélectionner tout** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="068d8-p111">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="068d8-172">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="068d8-172">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="068d8-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="068d8-173">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="068d8-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="068d8-174">See Also</span></span>

[<span data-ttu-id="068d8-175">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="068d8-175">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  

[<span data-ttu-id="068d8-176">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="068d8-176">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  

[<span data-ttu-id="068d8-177">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="068d8-177">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  

[<span data-ttu-id="068d8-178">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="068d8-178">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
