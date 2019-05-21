---
title: Liaison des régions réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC). '
ms.openlocfilehash: b9ffa45c8a0a09ba4a7f9f0ebf6402b87116f01f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279556"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="436bf-103">Liaison des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="436bf-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="436bf-104">Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="436bf-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="436bf-105">Les sections de cet article vous permettent d’afficher des informations sur le lien de la région newtwork ou de configurer ou supprimer des liens vers des régions Netwrok.</span><span class="sxs-lookup"><span data-stu-id="436bf-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="436bf-106">Afficher les informations sur le lien de la région de réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-106">View network region link information</span></span> 

<span data-ttu-id="436bf-107">Vous pouvez afficher les liens entre deux régions réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="436bf-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="436bf-108">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="436bf-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="436bf-109">Le panneau de configuration Skype entreprise Server vous permet d’afficher un lien existant entre deux régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="436bf-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="436bf-110">Pour afficher un lien de région réseau dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="436bf-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="436bf-111">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436bf-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436bf-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="436bf-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="436bf-113">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="436bf-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="436bf-114">Dans la page de liaison de la **zone** , cliquez sur le lien de la région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="436bf-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="436bf-115">Vous pouvez uniquement afficher des informations sur un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="436bf-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="436bf-116">Dans le menu **édition** , cliquez sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="436bf-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="436bf-117">Afficher les informations sur les liens de région réseau à l’aide d’applets de requête Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="436bf-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="436bf-118">Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et de l’applet **de requête get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="436bf-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="436bf-119">Vous pouvez exécuter cette applet de commande dans Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="436bf-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="436bf-120">Pour afficher les informations sur le lien dans la région réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-120">To view network region link information</span></span>

  - <span data-ttu-id="436bf-121">Pour afficher des informations sur tous les liens de votre région réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="436bf-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="436bf-122">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="436bf-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="436bf-123">Pour plus d’informations, consultez la rubrique [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="436bf-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="436bf-124">Configurer les liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-124">Configure network region links</span></span> 

<span data-ttu-id="436bf-125">Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="436bf-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="436bf-126">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="436bf-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="436bf-127">Le panneau de configuration Skype entreprise Server vous permet de définir un lien entre deux régions du réseau et de définir les limites de bande passante pour les connexions audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="436bf-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="436bf-128">Pour créer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-128">To create a network region link</span></span>

1.  <span data-ttu-id="436bf-129">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436bf-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436bf-130">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="436bf-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="436bf-131">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="436bf-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="436bf-132">Dans la page de **liaison région** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="436bf-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="436bf-133">Dans le **lien nouvelle zone**, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="436bf-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="436bf-134">Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="436bf-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="436bf-135">Dans la liste déroulante \*\* \#région réseau 1\*\* , sélectionnez l’une des deux régions à lier.</span><span class="sxs-lookup"><span data-stu-id="436bf-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="436bf-136">Dans la liste déroulante \*\* \#région de réseau 2\*\* , sélectionnez la autre zone à lier.</span><span class="sxs-lookup"><span data-stu-id="436bf-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="436bf-137">Cette région doit être différente de la région sélectionnée pour la région \#réseau 1.</span><span class="sxs-lookup"><span data-stu-id="436bf-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="436bf-138">Facultatif Si vous voulez appliquer des limitations de bande passante aux appels audio et vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .</span><span class="sxs-lookup"><span data-stu-id="436bf-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="436bf-139">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="436bf-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="436bf-140">Pour modifier un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-140">To modify a network region link</span></span>

1.  <span data-ttu-id="436bf-141">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436bf-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436bf-142">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="436bf-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="436bf-143">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="436bf-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="436bf-144">Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="436bf-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="436bf-145">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="436bf-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="436bf-146">Dans le **lien modifier la région**, vous pouvez modifier les régions liées ou le profil de la stratégie de bande passante pour ce lien.</span><span class="sxs-lookup"><span data-stu-id="436bf-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="436bf-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="436bf-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="436bf-148">Supprimer des liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-148">Delete network region links</span></span>

<span data-ttu-id="436bf-149">Vous pouvez configurer des liens entre deux régions réseau dans le cadre de la commande d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="436bf-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="436bf-150">Les régions d’un réseau sont liées par le biais de la connectivité du réseau étendu (WAN) physique.</span><span class="sxs-lookup"><span data-stu-id="436bf-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="436bf-151">Le panneau de configuration Skype entreprise Server vous permet de supprimer un lien existant entre deux régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="436bf-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="436bf-152">Pour supprimer un lien de zone réseau</span><span class="sxs-lookup"><span data-stu-id="436bf-152">To delete a network region link</span></span>

1.  <span data-ttu-id="436bf-153">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="436bf-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="436bf-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="436bf-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="436bf-155">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **liaison de région**.</span><span class="sxs-lookup"><span data-stu-id="436bf-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="436bf-156">Dans la page de liaison de la **zone** , cliquez sur le lien dans la région que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="436bf-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="436bf-157">Vous pouvez supprimer plusieurs liens vers une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="436bf-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="436bf-158">Pour cela, appuyez sur CTRL et sélectionnez les liens de plusieurs régions tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="436bf-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="436bf-159">Pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="436bf-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="436bf-160">Dans le menu **modifier** , sélectionnez **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="436bf-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="436bf-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="436bf-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="436bf-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="436bf-162">See Also</span></span>

[<span data-ttu-id="436bf-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="436bf-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="436bf-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="436bf-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="436bf-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="436bf-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="436bf-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="436bf-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
