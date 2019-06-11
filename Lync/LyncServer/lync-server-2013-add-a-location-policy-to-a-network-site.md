---
title: 'Lync Server 2013: ajouter une stratégie d’emplacement à un site réseau'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="dc652-102">Ajouter une stratégie d’emplacement à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc652-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc652-103">_**Dernière modification de la rubrique:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="dc652-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="dc652-104">Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans [créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md) à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie de localisation **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="dc652-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="dc652-105">Pour plus d’informations sur l’utilisation des sites réseau, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:</span><span class="sxs-lookup"><span data-stu-id="dc652-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="dc652-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc652-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="dc652-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc652-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="dc652-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc652-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="dc652-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc652-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="dc652-110">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="dc652-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="dc652-111">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dc652-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="dc652-112">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="dc652-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="dc652-113">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant appelé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="dc652-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="dc652-114">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="dc652-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="dc652-115">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dc652-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="dc652-116">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="dc652-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="dc652-117">Créez un site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="dc652-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

