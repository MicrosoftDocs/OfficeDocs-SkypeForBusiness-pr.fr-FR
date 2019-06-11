---
title: 'Lync Server 2013: création ou modification de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f27088b59745bac580990b3e898f485d34dcad57
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="1005d-102">Créer ou modifier des sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1005d-102">Create or modify network subnets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1005d-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1005d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1005d-104">Un sous-réseau doit être associé à un site réseau pour vous permettre de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1005d-104">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="1005d-105">Le panneau de configuration de Lync Server vous permet de configurer les sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="1005d-105">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="1005d-106">Dans le panneau de configuration de Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1005d-106">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="1005d-107">Pour plus d’informations sur la suppression de sous-réseaux réseau, voir [Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="1005d-107">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="1005d-108">Dans la plupart des déploiements de Microsoft Lync Server 2013 sur lequel est implémenté le contrôle d’admission des appels, il existe généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="1005d-108">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="1005d-109">Pour cette raison, il est souvent préférable de configurer les sous-réseaux à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1005d-109">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="1005d-110">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** conjointement avec l’applet de cmdlet Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="1005d-110">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="1005d-111">L’utilisation conjointe de ces applets de passe vous permet de lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et de créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="1005d-111">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="1005d-112">Pour obtenir des exemples sur la façon de créer des sous-réseaux à partir d’un fichier. csv, voir [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="1005d-112">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="1005d-113">Pour créer un sous-réseau du réseau</span><span class="sxs-lookup"><span data-stu-id="1005d-113">To create a network subnet</span></span>

1.  <span data-ttu-id="1005d-114">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1005d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1005d-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1005d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1005d-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1005d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1005d-117">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="1005d-117">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="1005d-118">Sur la page **sous-réseau** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1005d-118">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="1005d-119">Dans **nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau** .</span><span class="sxs-lookup"><span data-stu-id="1005d-119">In **New Subnet**, enter a value in the **Subnet ID** field.</span></span> <span data-ttu-id="1005d-120">Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0) et doit être la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1005d-120">This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="1005d-121">Dans le champ **masque** , entrez une valeur numérique comprise entre 1 et 32.</span><span class="sxs-lookup"><span data-stu-id="1005d-121">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1005d-122">Cette valeur correspond au masque de passe à appliquer au sous-réseau qui est créé.</span><span class="sxs-lookup"><span data-stu-id="1005d-122">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="1005d-123">Dans **ID du site réseau**, sélectionnez le site auquel appartient ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1005d-123">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="1005d-124">Facultatif Tapez une valeur dans le champ **Description** pour fournir davantage d’informations sur ce sous-réseau qui ne peut pas être exprimé par le nom seul.</span><span class="sxs-lookup"><span data-stu-id="1005d-124">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="1005d-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1005d-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="1005d-126">Pour modifier un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="1005d-126">To modify a network subnet</span></span>

1.  <span data-ttu-id="1005d-127">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1005d-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1005d-128">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1005d-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1005d-129">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1005d-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1005d-130">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="1005d-130">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="1005d-131">Dans la page de **sous-réseau** , cliquez sur le sous-réseau que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="1005d-131">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="1005d-132">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1005d-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1005d-133">Dans la page **modifier le sous-réseau** , vous pouvez modifier le masque de la page, le site réseau associé ou la description.</span><span class="sxs-lookup"><span data-stu-id="1005d-133">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description.</span></span> <span data-ttu-id="1005d-134">Si vous modifiez le masque de réinitialisation, n’oubliez pas que l’ID de sous-réseau doit toujours être la première adresse de la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1005d-134">If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="1005d-135">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1005d-135">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1005d-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1005d-136">See Also</span></span>


[<span data-ttu-id="1005d-137">Supprimer des sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1005d-137">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="1005d-138">À propos des régions réseau, des sites réseau et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1005d-138">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="1005d-139">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1005d-139">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="1005d-140">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1005d-140">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="1005d-141">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1005d-141">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="1005d-142">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="1005d-142">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

