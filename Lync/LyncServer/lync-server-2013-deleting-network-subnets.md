---
title: 'Lync Server 2013 : suppression de sous-réseaux réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 013de3ae58424473aa42aee767982fd84a9d651e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504271"
---
# <a name="deleting-network-subnets-in-lync-server-2013"></a><span data-ttu-id="48e86-102">Suppression de sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e86-102">Deleting network subnets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48e86-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="48e86-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="48e86-104">La procédure suivante vous permet de supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="48e86-104">You can use the following procedure to delete a subnet.</span></span> <span data-ttu-id="48e86-105">Dans le panneau de configuration Lync Server, vous pouvez créer, modifier ou supprimer un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="48e86-105">From the Lync Server Control Panel, you can create, modify, or delete a network subnet.</span></span> <span data-ttu-id="48e86-106">Pour plus d’informations sur la création ou la modification de sous-réseaux réseau, voir [créer ou modifier des sous-réseaux dans Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="48e86-106">For details on creating or modifying network subnets, see [Create or modify network subnets in Lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).</span></span>

<span data-ttu-id="48e86-107">Dans la plupart des déploiements de Microsoft Lync Server 2013 où le contrôle d’admission des appels (CAC) est implémenté, il y aura généralement un grand nombre de sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="48e86-107">In most deployments of Microsoft Lync Server 2013 where call admission control (CAC) is implemented, there will typically be a large number of subnets.</span></span> <span data-ttu-id="48e86-108">Pour cette raison, il est souvent préférable de configurer des sous-réseaux à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="48e86-108">Because of this, it is often best to configure subnets from the Lync Server Management Shell.</span></span> <span data-ttu-id="48e86-109">À partir de là, vous pouvez appeler **New-CsNetworkSubnet** en association avec l’applet de commande Windows PowerShell **Import-CSV**.</span><span class="sxs-lookup"><span data-stu-id="48e86-109">From there you can call **New-CsNetworkSubnet** in conjunction with the Windows PowerShell cmdlet **Import-CSV**.</span></span> <span data-ttu-id="48e86-110">En utilisant ces cmdlets ensemble, vous pouvez lire les paramètres de sous-réseau à partir d’un fichier de valeurs séparées par des virgules (. csv) et créer plusieurs sous-réseaux en même temps.</span><span class="sxs-lookup"><span data-stu-id="48e86-110">By using these cmdlets together, you can read in subnet settings from a comma-separated values (.csv) file and create multiple subnets at the same time.</span></span> <span data-ttu-id="48e86-111">Pour obtenir des exemples de création de sous-réseaux à partir d’un fichier. csv, consultez la rubrique [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span><span class="sxs-lookup"><span data-stu-id="48e86-111">For examples of how to create subnets from a .csv file, see [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).</span></span>

<div>

## <a name="to-delete-a-network-subnet"></a><span data-ttu-id="48e86-112">Pour supprimer un sous-réseau</span><span class="sxs-lookup"><span data-stu-id="48e86-112">To delete a network subnet</span></span>

1.  <span data-ttu-id="48e86-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="48e86-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="48e86-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48e86-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="48e86-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="48e86-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="48e86-116">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Sous-réseau**.</span><span class="sxs-lookup"><span data-stu-id="48e86-116">In the left navigation bar, click **Network Configuration** and then click **Subnet**.</span></span>

4.  <span data-ttu-id="48e86-117">Dans la page **Sous-réseau**, cliquez sur le sous-réseau à supprimer.</span><span class="sxs-lookup"><span data-stu-id="48e86-117">On the **Subnet** page, click the subnet that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="48e86-p104">Vous pouvez supprimer plusieurs sous-réseaux à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez les différents sous-réseaux à supprimer. Pour sélectionner la totalité des sous-réseaux, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="48e86-p104">You can delete more than one subnet at a time. To do this, press CTRL and select multiple subnets while holding down the CTRL key. Or, to select all subnets, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="48e86-121">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="48e86-121">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="48e86-122">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="48e86-122">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48e86-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48e86-123">See Also</span></span>


[<span data-ttu-id="48e86-124">Création ou modification de sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48e86-124">Create or modify network subnets in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

