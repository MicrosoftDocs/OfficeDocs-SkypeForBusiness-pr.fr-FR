---
title: 'Lync Server 2013 : création de liens de région réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f40b9d569cbc571fe931a53b6f399b6273efd055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="9b859-102">Créer des liens de région réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b859-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b859-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9b859-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9b859-104">Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique.</span><span class="sxs-lookup"><span data-stu-id="9b859-104">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="9b859-105">Un *lien de région réseau* crée un lien entre deux régions configurées pour le contrôle d’admission des appels (CAC) et définit les limites de bande passante pour le trafic audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="9b859-105">A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="9b859-106">Pour plus d’informations sur l’utilisation des liaisons de région réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="9b859-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9b859-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b859-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="9b859-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b859-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="9b859-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b859-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="9b859-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b859-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="9b859-111">L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC, ainsi qu’un lien entre les régions EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="9b859-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="9b859-112">Chacun de ces liens de région est limité par la bande passante WAN, comme décrit dans la table informations sur la bande passante liée à la région dans l' [exemple : rassemblement de vos exigences de contrôle d’admission des appels dans la section Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="9b859-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="9b859-113">Pour créer des liaisons de région réseau à l’aide de Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="9b859-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="9b859-114">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9b859-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9b859-115">Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés.</span><span class="sxs-lookup"><span data-stu-id="9b859-115">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="9b859-116">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="9b859-116">For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="9b859-117">Pour créer des liens de région réseau à l’aide du panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9b859-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9b859-118">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b859-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b859-119">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b859-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9b859-120">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="9b859-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9b859-121">Cliquez sur le bouton de navigation **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="9b859-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="9b859-122">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="9b859-122">Click **New**.</span></span>

5.  <span data-ttu-id="9b859-123">Dans la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.</span><span class="sxs-lookup"><span data-stu-id="9b859-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="9b859-124">Cliquez sur la \*\* \#région réseau 1\*\*, puis cliquez sur la région réseau dans la liste que vous voulez lier à la \#région 2 du réseau.</span><span class="sxs-lookup"><span data-stu-id="9b859-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="9b859-125">Cliquez sur la \*\* \#zone réseau 2\*\*, puis cliquez sur une région réseau dans la liste que vous voulez lier à la \#région 1 du réseau.</span><span class="sxs-lookup"><span data-stu-id="9b859-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="9b859-126">Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante à appliquer au lien de région réseau.</span><span class="sxs-lookup"><span data-stu-id="9b859-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9b859-127">N’appliquez une stratégie de bande passante que si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien.</span><span class="sxs-lookup"><span data-stu-id="9b859-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="9b859-128">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9b859-128">Click **Commit**.</span></span>

10. <span data-ttu-id="9b859-129">Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="9b859-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
