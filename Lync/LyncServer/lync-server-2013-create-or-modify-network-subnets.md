---
title: 'Lync Server 2013 : création ou modification de sous-réseaux'
description: 'Lync Server 2013 : créez ou modifiez des sous-réseaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify network subnets
ms:assetid: 1ba8c4e3-fbc7-4758-88ac-d651fef17bed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520957(v=OCS.15)
ms:contentKeyID: 48183548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37695707bf39b10c351a4990b132c9799406f9c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546920"
---
# <a name="create-or-modify-network-subnets-in-lync-server-2013"></a><span data-ttu-id="464b1-103">Création ou modification de sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464b1-103">Create or modify network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="464b1-104">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="464b1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="464b1-105">Un sous-réseau de réseau doit être associé à un site réseau afin de déterminer l’emplacement géographique de l’hôte appartenant à ce sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="464b1-105">A network subnet must be associated with a network site for the purposes of determining the geographic location of the host belonging to this subnet.</span></span> <span data-ttu-id="464b1-106">Vous pouvez utiliser le panneau de configuration Lync Server pour configurer des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="464b1-106">You can use Lync Server Control Panel to configure subnets.</span></span> <span data-ttu-id="464b1-107">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="464b1-107">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="464b1-108">Pour plus d’informations sur la suppression des sous-réseaux réseau, consultez [la rubrique Suppression de sous-réseaux réseau dans Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="464b1-108">For details about deleting network subnets, see [Deleting network subnets in Lync Server 2013](lync-server-2013-deleting-network-subnets.md).</span></span>

<span data-ttu-id="464b1-109">Dans la plupart des déploiements de Microsoft Lync Server 2013 où le contrôle d’admission des appels (CAC) est implémenté, il y aura généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="464b1-109">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="464b1-110">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="464b1-110">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="464b1-111">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** en association avec l’applet de commande Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="464b1-111">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="464b1-112">En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="464b1-112">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="464b1-113">Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier. csv, consultez la rubrique [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="464b1-113">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-create-a-network-subnet"></a><span data-ttu-id="464b1-114">Pour créer un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="464b1-114">To create a network subnet</span></span>

1.  <span data-ttu-id="464b1-115">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="464b1-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="464b1-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="464b1-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="464b1-117">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="464b1-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="464b1-118">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="464b1-118">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="464b1-119">Dans la page **Sous-réseau**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="464b1-119">On the **Subnet** page, click **New**.</span></span>

5.  <span data-ttu-id="464b1-p104">Dans **Nouveau sous-réseau**, entrez une valeur dans le champ **ID de sous-réseau**. Il doit s’agir d’une adresse IP (par exemple, 174.11.12.0), qui doit être la première adresse dans la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="464b1-p104">In **New Subnet**, enter a value in the **Subnet ID** field. This must be an IP address (for example, 174.11.12.0), and it must be the first address in the IP address range defined by the subnet.</span></span>

6.  <span data-ttu-id="464b1-122">Dans le champ **Masque**, entrez une valeur numérique comprise entre 1 et 32.</span><span class="sxs-lookup"><span data-stu-id="464b1-122">In the **Mask** field, enter a numeric value from 1 through 32.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="464b1-123">Cette valeur est le masque de bits à appliquer au sous-réseau en cours de création.</span><span class="sxs-lookup"><span data-stu-id="464b1-123">This value is the bitmask that is to be applied to the subnet being created.</span></span>

    
    </div>

7.  <span data-ttu-id="464b1-124">Dans le champ **ID de site réseau**, sélectionnez le site auquel ce sous-réseau appartient.</span><span class="sxs-lookup"><span data-stu-id="464b1-124">In **Network site ID**, select the site to which this subnet belongs.</span></span>

8.  <span data-ttu-id="464b1-125">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce sous-réseau, car son nom ne suffit pas à le décrire.</span><span class="sxs-lookup"><span data-stu-id="464b1-125">(Optional) Type a value in the **Description** field to provide more information about this subnet that cannot be expressed by the name alone.</span></span>

9.  <span data-ttu-id="464b1-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="464b1-126">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-subnet"></a><span data-ttu-id="464b1-127">Pour modifier un sous-réseau de réseau</span><span class="sxs-lookup"><span data-stu-id="464b1-127">To modify a network subnet</span></span>

1.  <span data-ttu-id="464b1-128">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="464b1-128">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="464b1-129">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="464b1-129">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="464b1-130">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="464b1-130">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="464b1-131">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="464b1-131">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="464b1-132">Dans la page **Sous-réseau**, cliquez sur le sous-réseau que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="464b1-132">On the **Subnet** page, click the subnet that you want to modify.</span></span>

5.  <span data-ttu-id="464b1-133">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="464b1-133">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="464b1-p106">Dans la page **Modifier le sous-réseau**, vous pouvez modifier le masque de bits, le site réseau associé ou la description du sous-réseau. Si vous modifiez le masque de bits, n’oubliez pas que l’ID du sous-réseau doit toujours être la première adresse dans la plage d’adresses IP définie par le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="464b1-p106">On the **Edit Subnet** page, you can modify the bitmask, associated network site, or description. If you modify the bitmask, keep in mind that the Subnet ID must still be the first address in the IP address range defined by the subnet.</span></span>

7.  <span data-ttu-id="464b1-136">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="464b1-136">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="464b1-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="464b1-137">See Also</span></span>


[<span data-ttu-id="464b1-138">Suppression de sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464b1-138">Deleting network subnets in Lync Server 2013</span></span>](lync-server-2013-deleting-network-subnets.md)  


[<span data-ttu-id="464b1-139">À propos des régions réseau, des sites et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="464b1-139">About network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-about-network-regions-sites-and-subnets.md)  


[<span data-ttu-id="464b1-140">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="464b1-140">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet)  
[<span data-ttu-id="464b1-141">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="464b1-141">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSubnet)  
[<span data-ttu-id="464b1-142">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="464b1-142">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSubnet)  
[<span data-ttu-id="464b1-143">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="464b1-143">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSubnet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

