---
title: Liaison de régions réseau
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC). '
ms.openlocfilehash: 163f214b05ba0dca3bc7dd4ec722f148cafe724e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096680"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="8fcd8-103">Liaison des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8fcd8-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="8fcd8-104">Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8fcd8-105">Utilisez les sections de cet article pour afficher les informations de lien de région de travail nouveau ou configurer ou supprimer des liens de région netwrok.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="8fcd8-106">Afficher les informations de lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-106">View network region link information</span></span> 

<span data-ttu-id="8fcd8-107">Vous pouvez afficher les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8fcd8-108">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8fcd8-109">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour afficher un lien existant entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="8fcd8-110">Pour afficher un lien de région réseau dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="8fcd8-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="8fcd8-111">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fcd8-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8fcd8-113">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Lien de région.**</span><span class="sxs-lookup"><span data-stu-id="8fcd8-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8fcd8-114">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="8fcd8-115">Vous ne pouvez afficher des informations que sur un lien de région à la fois.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="8fcd8-116">Dans le menu **Edition**, sélectionnez **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8fcd8-117">Afficher les informations de lien de région réseau à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="8fcd8-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8fcd8-118">Vous pouvez afficher les liens de région réseau à l’Windows PowerShell et à l’aide de l’cmdlet **Get-CsNetworkRegionLink.**</span><span class="sxs-lookup"><span data-stu-id="8fcd8-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="8fcd8-119">Vous pouvez exécuter cette applet de commande à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="8fcd8-120">Pour afficher les informations d’un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-120">To view network region link information</span></span>

  - <span data-ttu-id="8fcd8-121">Pour afficher des informations sur tous vos liens de région réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="8fcd8-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="8fcd8-122">Cette commande renvoie des informations comme celles-ci :</span><span class="sxs-lookup"><span data-stu-id="8fcd8-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="8fcd8-123">Pour plus d’informations, voir [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-123">For details, see [Get-CsNetworkRegionLink](/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="8fcd8-124">Configurer des liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-124">Configure network region links</span></span> 

<span data-ttu-id="8fcd8-125">Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8fcd8-126">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8fcd8-127">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour définir un lien entre deux régions réseau et définir les limites de bande passante sur les connexions audio et vidéo entre ces régions.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="8fcd8-128">Pour créer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-128">To create a network region link</span></span>

1.  <span data-ttu-id="8fcd8-129">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fcd8-130">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8fcd8-131">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**</span><span class="sxs-lookup"><span data-stu-id="8fcd8-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8fcd8-132">Dans la page **Lien de région**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="8fcd8-133">Dans **Nouveau lien de région**, tapez une valeur dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8fcd8-134">Cette valeur doit être unique dans votre déploiement Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="8fcd8-135">Dans la liste de listes listes de la région Réseau **\# 1,** sélectionnez l’une des deux régions à l lié.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="8fcd8-136">Dans la liste de listes bas Région réseau **\# 2,** sélectionnez l’autre région à l’l lié.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="8fcd8-137">Cette région doit être différente de la région sélectionnée pour la région \# réseau 1.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="8fcd8-138">(Facultatif) Si vous souhaitez ajouter des limites de bande passante sur les appels audio ou vidéo entre ces régions, sélectionnez un profil de stratégie de bande passante dans la liste déroulante **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="8fcd8-139">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="8fcd8-140">Pour modifier un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-140">To modify a network region link</span></span>

1.  <span data-ttu-id="8fcd8-141">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fcd8-142">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8fcd8-143">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis cliquez sur **Lien de région.**</span><span class="sxs-lookup"><span data-stu-id="8fcd8-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8fcd8-144">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="8fcd8-145">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8fcd8-146">Dans **Modifier le lien de région**, vous pouvez modifier les régions liées ou le profil de stratégie de bande passante pour ce lien.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="8fcd8-147">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="8fcd8-148">Supprimer des liens de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-148">Delete network region links</span></span>

<span data-ttu-id="8fcd8-149">Vous pouvez configurer les liens entre deux régions réseau dans le cadre du service Contrôle d’admission des appels (CAC).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8fcd8-150">Au sein d’un réseau, les régions sont liées par une connectivité physique au réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="8fcd8-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8fcd8-151">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour supprimer un lien existant entre deux régions réseau.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="8fcd8-152">Pour supprimer un lien de région réseau</span><span class="sxs-lookup"><span data-stu-id="8fcd8-152">To delete a network region link</span></span>

1.  <span data-ttu-id="8fcd8-153">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8fcd8-154">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8fcd8-155">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Lien de région.**</span><span class="sxs-lookup"><span data-stu-id="8fcd8-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8fcd8-156">Dans la page **Lien de région**, cliquez sur le lien de région que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8fcd8-p107">Vous pouvez supprimer plusieurs liens de région à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs liens de région. Ou, pour sélectionner tous les liens de région, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="8fcd8-160">Dans le menu **Edition**, sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="8fcd8-161">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fcd8-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="8fcd8-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fcd8-162">See Also</span></span>

[<span data-ttu-id="8fcd8-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8fcd8-163">New-CsNetworkRegionLink</span></span>](/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="8fcd8-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8fcd8-164">Set-CsNetworkRegionLink</span></span>](/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="8fcd8-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8fcd8-165">Remove-CsNetworkRegionLink</span></span>](/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="8fcd8-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8fcd8-166">Get-CsNetworkRegionLink</span></span>](/powershell/module/skype/Get-CsNetworkRegionLink)