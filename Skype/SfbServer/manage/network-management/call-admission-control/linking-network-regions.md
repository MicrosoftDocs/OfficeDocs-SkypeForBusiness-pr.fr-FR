---
title: Liaison des régions réseau
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC). '
ms.openlocfilehash: 4ea6ddcc72d2cadea32608288d1db93ba8505aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884683"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="de5ab-103">Liaison des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="de5ab-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="de5ab-104">Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="de5ab-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="de5ab-105">Utilisez les sections de cet article pour afficher les informations de lien de région PERIPHERIE, configurer ou supprimer des liens de région réseau.</span><span class="sxs-lookup"><span data-stu-id="de5ab-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="de5ab-106">Affichage des informations de lien de région de réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-106">View network region link information</span></span> 

<span data-ttu-id="de5ab-107">Vous pouvez afficher les liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="de5ab-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="de5ab-108">Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique.</span><span class="sxs-lookup"><span data-stu-id="de5ab-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="de5ab-109">Vous pouvez utiliser la Skype pour Business Server Control Panel pour afficher un lien entre deux régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="de5ab-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="de5ab-110">Pour afficher un lien de région réseau dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="de5ab-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="de5ab-111">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="de5ab-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ab-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="de5ab-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ab-113">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="de5ab-114">Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="de5ab-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="de5ab-115">Vous ne pouvez afficher des informations sur un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="de5ab-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="de5ab-116">Dans le menu **Edition** , sélectionnez **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="de5ab-117">Afficher les informations de lien de région réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de5ab-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="de5ab-118">Vous pouvez afficher les liens de région réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkRegionLink** .</span><span class="sxs-lookup"><span data-stu-id="de5ab-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="de5ab-119">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de5ab-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="de5ab-120">Pour afficher les informations de lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-120">To view network region link information</span></span>

  - <span data-ttu-id="de5ab-121">Pour afficher des informations sur tous les liens de région réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="de5ab-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="de5ab-122">Cette commande renvoie le type d’informations suivant :</span><span class="sxs-lookup"><span data-stu-id="de5ab-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="de5ab-123">Pour plus d’informations, voir [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="de5ab-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="de5ab-124">Configurer les liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-124">Configure network region links</span></span> 

<span data-ttu-id="de5ab-125">Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="de5ab-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="de5ab-126">Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique.</span><span class="sxs-lookup"><span data-stu-id="de5ab-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="de5ab-127">Vous pouvez utiliser la Skype pour Business Server Control Panel pour définir un lien entre deux régions de réseau et les limitations de bande passante sur les connexions audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="de5ab-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="de5ab-128">Pour créer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-128">To create a network region link</span></span>

1.  <span data-ttu-id="de5ab-129">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="de5ab-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ab-130">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="de5ab-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ab-131">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="de5ab-132">Dans la page **Lien de région** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="de5ab-133">Dans le **Nouveau lien de région**, tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="de5ab-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="de5ab-134">Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="de5ab-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="de5ab-135">À partir de la **région réseau \#1** liste déroulante, sélectionnez une des deux régions à lier.</span><span class="sxs-lookup"><span data-stu-id="de5ab-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="de5ab-136">À partir de la **région réseau \#2** liste déroulante, sélectionnez l’autre région à lier.</span><span class="sxs-lookup"><span data-stu-id="de5ab-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="de5ab-137">Cette zone doit être différente de la région sélectionnée pour la région de réseau \#1.</span><span class="sxs-lookup"><span data-stu-id="de5ab-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="de5ab-138">(Facultatif) Si vous souhaitez placer des restrictions de bande passante pour les appels audio ou vidéos entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **stratégie de bande passante** .</span><span class="sxs-lookup"><span data-stu-id="de5ab-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="de5ab-139">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="de5ab-140">Pour modifier un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-140">To modify a network region link</span></span>

1.  <span data-ttu-id="de5ab-141">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="de5ab-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ab-142">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="de5ab-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ab-143">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="de5ab-144">Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="de5ab-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="de5ab-145">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="de5ab-146">Dans **Modifier un lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.</span><span class="sxs-lookup"><span data-stu-id="de5ab-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="de5ab-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="de5ab-148">Supprimer les liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-148">Delete network region links</span></span>

<span data-ttu-id="de5ab-149">Vous pouvez configurer des liens entre deux régions de réseau dans le cadre du contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="de5ab-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="de5ab-150">Régions au sein d’un réseau sont liées par le biais de connectivité de réseau (étendu WAN) étendu physique.</span><span class="sxs-lookup"><span data-stu-id="de5ab-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="de5ab-151">Vous pouvez utiliser la Skype pour Business Server Control Panel pour supprimer un lien entre deux régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="de5ab-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="de5ab-152">Pour supprimer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="de5ab-152">To delete a network region link</span></span>

1.  <span data-ttu-id="de5ab-153">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="de5ab-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="de5ab-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="de5ab-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="de5ab-155">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur le **Lien de région**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="de5ab-156">Dans la page **Lien de région** , cliquez sur le lien de région que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="de5ab-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="de5ab-157">Vous pouvez supprimer plus d’un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="de5ab-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="de5ab-158">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs liens de région tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="de5ab-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="de5ab-159">Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="de5ab-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="de5ab-160">Dans le menu **Edition** , sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="de5ab-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="de5ab-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="de5ab-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de5ab-162">See Also</span></span>

[<span data-ttu-id="de5ab-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="de5ab-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="de5ab-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="de5ab-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="de5ab-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="de5ab-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="de5ab-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="de5ab-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
