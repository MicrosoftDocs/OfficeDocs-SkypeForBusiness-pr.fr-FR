---
title: Créer des liens de région réseau dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Créer ou modifier des liens de région réseau, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server.
ms.openlocfilehash: 729b20010390bf0a8865adce96a398d362009552
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874003"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="e68b4-103">Créer des liens de région réseau dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="e68b4-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="e68b4-104">Créer ou modifier des liens de région réseau, qui sont utilisés par le contrôle d’admission des appels d’appel Enterprise Voice dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="e68b4-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="e68b4-105">Au sein d’un réseau, les régions sont liées par une connectivité au réseau étendu physique.</span><span class="sxs-lookup"><span data-stu-id="e68b4-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="e68b4-106">Un lien de région réseau crée un lien entre deux régions configurées pour le contrôle d’admission des appels et définit les restrictions de bande passante sur le trafic audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="e68b4-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="e68b4-107">L’exemple de topologie possède un lien entre les régions Amérique du Nord et APAC, ainsi qu’un lien entre les régions EMEA et APAC.</span><span class="sxs-lookup"><span data-stu-id="e68b4-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="e68b4-108">Chacun de ces liens de région est limité par la bande passante du WAN, comme décrit dans la table d’informations sur la bande passante de lien de région dans [exemple : collecte des conditions requises pour le contrôle d’admission des appels dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e68b4-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e68b4-109">Pour créer des liens de région réseau à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e68b4-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e68b4-110">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e68b4-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e68b4-111">Exécutez l’applet de commande New-CsNetworkRegionLink pour créer des liens de région et appliquer des profils de stratégie de bande passante appropriés.</span><span class="sxs-lookup"><span data-stu-id="e68b4-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="e68b4-112">Par exemple, exécutez :</span><span class="sxs-lookup"><span data-stu-id="e68b4-112">For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e68b4-113">Pour créer des liens de région réseau à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="e68b4-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e68b4-114">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="e68b4-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="e68b4-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**.</span><span class="sxs-lookup"><span data-stu-id="e68b4-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="e68b4-116">Cliquez sur le bouton de navigation **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="e68b4-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="e68b4-117">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e68b4-117">Click **New**.</span></span>
    
5. <span data-ttu-id="e68b4-118">Dans la page **Nouveau lien de région**, cliquez sur **Nom**, puis tapez le nom du lien de région réseau.</span><span class="sxs-lookup"><span data-stu-id="e68b4-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="e68b4-119">Cliquez sur **Région réseau n° 1**, puis, dans la liste, cliquez sur la région réseau à lier à la Région réseau n° 2.</span><span class="sxs-lookup"><span data-stu-id="e68b4-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="e68b4-120">Cliquez sur **Région réseau n° 2**, puis, dans la liste, cliquez sur la région réseau à lier à la Région réseau n° 1.</span><span class="sxs-lookup"><span data-stu-id="e68b4-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="e68b4-121">Si vous le souhaitez, vous pouvez cliquer sur **Stratégie de bande passante**, puis sélectionner le profil de stratégie de bande passante à appliquer au lien de région réseau.</span><span class="sxs-lookup"><span data-stu-id="e68b4-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e68b4-122">N’appliquez une stratégie de bande passante que si le lien de région réseau est contraint par la bande passante et que vous souhaitez utiliser le contrôle d’admission des appels pour contrôler le trafic multimédia sur ce lien.</span><span class="sxs-lookup"><span data-stu-id="e68b4-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="e68b4-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e68b4-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="e68b4-124">Pour finir de créer des liens région réseau pour votre topologie, répétez les étapes 4 à 9 avec les paramètres d’autres régions.</span><span class="sxs-lookup"><span data-stu-id="e68b4-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e68b4-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e68b4-125">See also</span></span>

[<span data-ttu-id="e68b4-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e68b4-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="e68b4-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e68b4-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="e68b4-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e68b4-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="e68b4-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="e68b4-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
