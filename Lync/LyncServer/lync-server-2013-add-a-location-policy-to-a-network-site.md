---
title: 'Lync Server 2013 : ajout d’une stratégie d’emplacement à un site réseau'
description: 'Lync Server 2013 : ajouter une stratégie d’emplacement à un site réseau.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567920"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="9d7b6-103">Ajouter une stratégie d’emplacement à un site réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d7b6-103">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d7b6-104">_**Dernière modification de la rubrique :** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="9d7b6-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="9d7b6-105">Les exemples suivants montrent comment ajouter la stratégie d’emplacement **Redmond** définie dans [Create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md) à un site réseau existant et comment créer un nouveau site réseau qui utilise la stratégie d’emplacement **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="9d7b6-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="9d7b6-106">Pour plus d’informations sur l’utilisation des sites réseau, reportez-vous à la documentation Lync Server Management Shell pour les applets de commande suivantes :</span><span class="sxs-lookup"><span data-stu-id="9d7b6-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9d7b6-107">**New-applet csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="9d7b6-107">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="9d7b6-108">**Get-applet csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="9d7b6-108">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="9d7b6-109">**Set-applet csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="9d7b6-109">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="9d7b6-110">**Remove-applet csnetworksite**</span><span class="sxs-lookup"><span data-stu-id="9d7b6-110">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="9d7b6-111">Pour affecter une stratégie d’emplacement à un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="9d7b6-111">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="9d7b6-112">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9d7b6-113">Exécutez les applets de commande suivantes pour modifier un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="9d7b6-114">Affectez la stratégie d’emplacement balisée **Redmond** à un site réseau existant nommé **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="9d7b6-115">Pour affecter une stratégie d’emplacement à un nouveau site réseau</span><span class="sxs-lookup"><span data-stu-id="9d7b6-115">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="9d7b6-116">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9d7b6-117">Exécutez l’applet de commande suivante pour créer un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="9d7b6-118">Créez un nouveau site réseau dans la région réseau et affectez la stratégie d’emplacement balisée **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="9d7b6-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

