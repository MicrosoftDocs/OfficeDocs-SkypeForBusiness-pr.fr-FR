---
title: Créer des itinéraires interrégion réseau dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Créez ou modifiez des itinéraires interrégion réseau, qui sont utilisés par Voix Entreprise d’admission des appels dans Skype Entreprise Server.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093122"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="1d18d-103">Créer des itinéraires interrégion réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1d18d-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="1d18d-104">Créez ou modifiez des itinéraires interrégion réseau, qui sont utilisés par Voix Entreprise d’admission des appels dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1d18d-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1d18d-105">Un itinéraire interrégion réseau définit l’itinéraire entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="1d18d-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="1d18d-106">Chaque paire de régions réseau dans votre déploiement de contrôle d’admission des appels nécessite un itinéraire interrégion réseau.</span><span class="sxs-lookup"><span data-stu-id="1d18d-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="1d18d-107">Cela permet à chaque région réseau incluse dans le déploiement d’accéder à toute autre région.</span><span class="sxs-lookup"><span data-stu-id="1d18d-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="1d18d-108">Alors que les liaisons de région définissent des restrictions de bande passante sur les connexions entre les régions, un itinéraire interrégion détermine le chemin d’accès lié que la connexion traversera d’une région à une autre.</span><span class="sxs-lookup"><span data-stu-id="1d18d-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="1d18d-109">Dans l’exemple de topologie, des itinéraires interrégion réseau doivent être définis pour chacune des trois paires de régions : Amérique du Nord/EMEA, EMEA/APAC et Amérique du Nord/APAC.</span><span class="sxs-lookup"><span data-stu-id="1d18d-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1d18d-110">Pour créer des itinéraires interrégion réseau à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1d18d-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1d18d-111">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1d18d-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1d18d-112">Exécutez l’applet de commande **New-CsNetworkInterRegionRoute** pour définir les itinéraires nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1d18d-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="1d18d-113">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="1d18d-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="1d18d-114">L’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liaisons de région réseau, car il n’existe aucun lien de région réseau direct entre elles.</span><span class="sxs-lookup"><span data-stu-id="1d18d-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1d18d-115">Pour créer des itinéraires interrégion réseau à l’aide du Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1d18d-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1d18d-116">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1d18d-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1d18d-117">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="1d18d-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1d18d-118">Cliquez sur le bouton de navigation **Itinéraire de région**.</span><span class="sxs-lookup"><span data-stu-id="1d18d-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="1d18d-119">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1d18d-119">Click **New**.</span></span>
    
5. <span data-ttu-id="1d18d-120">Dans la page **Nouvel itinéraire de** région, cliquez sur **Nom,** puis tapez un nom pour l’itinéraire interrégion réseau.</span><span class="sxs-lookup"><span data-stu-id="1d18d-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="1d18d-121">Cliquez sur **Région réseau n° 1**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 2.</span><span class="sxs-lookup"><span data-stu-id="1d18d-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="1d18d-122">Cliquez sur **Région réseau n° 2**, puis cliquez dans la liste sur une région réseau que vous souhaitez acheminer vers la région réseau n° 1.</span><span class="sxs-lookup"><span data-stu-id="1d18d-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="1d18d-123">Cliquez **sur Ajouter** en **dehors** du champ Liens de région réseau, puis ajoutez un lien de région réseau qui sera utilisé dans l’itinéraire interrégion réseau.</span><span class="sxs-lookup"><span data-stu-id="1d18d-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1d18d-124">Si vous créez un itinéraire pour deux régions réseau qui n’ont pas de lien de région réseau direct entre elles, vous devez ajouter tous les liens nécessaires pour terminer l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="1d18d-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="1d18d-125">Par exemple, l’itinéraire interrégion réseau Amérique du Nord/APAC nécessite deux liaisons de région réseau, car il n’existe aucun lien de région réseau direct entre elles.</span><span class="sxs-lookup"><span data-stu-id="1d18d-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="1d18d-126">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1d18d-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="1d18d-127">Pour terminer la création d’itinéraires interrégion réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres itinéraires interrégion réseau.</span><span class="sxs-lookup"><span data-stu-id="1d18d-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1d18d-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1d18d-128">See also</span></span>

[<span data-ttu-id="1d18d-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1d18d-129">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1d18d-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1d18d-130">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1d18d-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1d18d-131">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1d18d-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1d18d-132">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)