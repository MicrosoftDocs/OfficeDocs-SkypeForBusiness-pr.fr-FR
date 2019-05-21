---
title: Gestion des régions réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Région du réseau * sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média.
ms.openlocfilehash: 8d1d60389fe910e2b5c2b8b1c357520aad30db96
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279528"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="07ac5-103">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="07ac5-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="07ac5-104">Les *régions réseau* sont les concentrateurs réseau ou les dorsales utilisés dans la configuration de contrôle d’admission des appels, de E9-1-1 et de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="07ac5-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="07ac5-105">Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="07ac5-106">Par exemple, si vous avez déjà créé des régions réseau pour une seule fonctionnalité vocale, vous n’avez pas besoin de créer de nouvelles régions réseau. d’autres fonctionnalités avancées de voix entreprise utiliseront les mêmes régions réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="07ac5-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="07ac5-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="07ac5-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="07ac5-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="07ac5-109">Suivez les procédures décrites dans cet article pour afficher des informations sur la région du réseau ou créer, modifier ou supprimer des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="07ac5-110">Afficher les informations relatives à la région du réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-110">View network region information</span></span> 


<span data-ttu-id="07ac5-111">Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="07ac5-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="07ac5-112">Chaque région du réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="07ac5-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="07ac5-113">Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="07ac5-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="07ac5-114">Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour afficher les régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="07ac5-115">Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="07ac5-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="07ac5-116">Utilisez cette rubrique pour afficher les régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="07ac5-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="07ac5-117">Pour afficher des informations sur une région de réseau avec le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="07ac5-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="07ac5-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="07ac5-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07ac5-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07ac5-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07ac5-120">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="07ac5-121">Dans la page **zone** , cliquez sur la zone que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="07ac5-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="07ac5-122">Vous ne pouvez afficher qu’une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="07ac5-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="07ac5-123">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="07ac5-124">Affichage des informations de région du réseau à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07ac5-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="07ac5-125">Vous pouvez afficher les informations relatives à la région du réseau à l’aide de Windows PowerShell et de l’applet **de requête get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="07ac5-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="07ac5-126">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07ac5-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="07ac5-127">Pour afficher les informations relatives aux régions du réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-127">To view network region information</span></span>

  - <span data-ttu-id="07ac5-128">Pour afficher des informations sur toutes les régions de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="07ac5-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="07ac5-129">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="07ac5-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="07ac5-130">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="07ac5-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="07ac5-131">Créer ou modifier des régions réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-131">Create or modify network regions</span></span> 

<span data-ttu-id="07ac5-132">Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="07ac5-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="07ac5-133">Chaque région du réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="07ac5-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="07ac5-134">Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="07ac5-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="07ac5-135">Le panneau de configuration Skype entreprise Server vous permet de configurer des régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="07ac5-136">Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="07ac5-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="07ac5-137">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="07ac5-138">Utilisez cette rubrique pour créer et modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="07ac5-139">Pour créer une zone réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-139">To create a network region</span></span>

1.  <span data-ttu-id="07ac5-140">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="07ac5-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07ac5-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07ac5-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07ac5-142">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="07ac5-143">Dans la page **région** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="07ac5-144">Dans la page **nouvelle région** , tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="07ac5-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="07ac5-145">Cette valeur doit être unique dans le cadre de votre déploiement Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07ac5-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="07ac5-146">Dans la liste déroulante **site central** , sélectionnez le site central pour cette région réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="07ac5-147">La case à cocher **activer le chemin audio alternatif** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="07ac5-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="07ac5-148">Ce champ détermine si les appels audio seront routés par le biais d’un autre chemin si la bande passante suffisante n’existe pas dans le chemin principal.</span><span class="sxs-lookup"><span data-stu-id="07ac5-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="07ac5-149">Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet.</span><span class="sxs-lookup"><span data-stu-id="07ac5-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="07ac5-150">Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="07ac5-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="07ac5-151">La case à cocher **activer le chemin vidéo alternatif** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="07ac5-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="07ac5-152">Ce champ détermine si les appels vidéo sont routés par le biais d’une autre trajectoire si la bande passante suffisante n’existe pas dans le chemin principal.</span><span class="sxs-lookup"><span data-stu-id="07ac5-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="07ac5-153">Désactivez cette case à cocher uniquement si vous avez besoin de désactiver le déchargement sur Internet.</span><span class="sxs-lookup"><span data-stu-id="07ac5-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="07ac5-154">Si l’un de vos appels sera appelé appels Internet, cette case doit être cochée, quels que soient les paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="07ac5-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="07ac5-155">Facultatif Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région qui ne peut pas être exprimée à l’aide du nom seul.</span><span class="sxs-lookup"><span data-stu-id="07ac5-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="07ac5-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-156">Click **Commit**.</span></span>

<span data-ttu-id="07ac5-157">La table **site associée** n’est pas utilisée pour créer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="07ac5-158">Vous associez un site à une région lorsque vous créez ou modifiez le site.</span><span class="sxs-lookup"><span data-stu-id="07ac5-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="07ac5-159">Pour plus d’informations, consultez [gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="07ac5-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="07ac5-160">Pour modifier une zone réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-160">To modify a network region</span></span>

1.  <span data-ttu-id="07ac5-161">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="07ac5-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07ac5-162">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07ac5-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07ac5-163">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="07ac5-164">Dans la page **zone** , cliquez sur la zone que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="07ac5-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="07ac5-165">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="07ac5-166">Dans la page **modifier la région** , vous pouvez modifier les paramètres d’activation et de désactivation des chemins audio et vidéo, et modifier la description (pour plus de détails, reportez-vous à la section «créer une région réseau» plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="07ac5-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="07ac5-167">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-167">Click **Commit**.</span></span>

<span data-ttu-id="07ac5-168">Vous ne pouvez pas modifier les **sites associés** sur cette page.</span><span class="sxs-lookup"><span data-stu-id="07ac5-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="07ac5-169">La liste des sites associés est fournie à des fins de référence, afin que vous soyez attentif aux sites qui seront affectés lors de la modification des paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="07ac5-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="07ac5-170">Supprimer des régions réseau existantes</span><span class="sxs-lookup"><span data-stu-id="07ac5-170">Delete existing network regions</span></span> 

<span data-ttu-id="07ac5-171">Une région réseau interconnecte diverses parties d’un réseau à plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="07ac5-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="07ac5-172">Chaque région du réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="07ac5-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="07ac5-173">Le site central est le site du centre de données sur lequel le service de stratégie de bande passante de contrôle d’admission des appels (CAC) est en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="07ac5-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="07ac5-174">Le panneau de configuration Skype entreprise Server vous permet de configurer des régions du réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="07ac5-175">Les régions réseau incluent des paramètres qui déterminent si d’autres chemins d’accès via Internet sont autorisés pour les connexions audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="07ac5-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="07ac5-176">Dans le panneau de configuration Skype entreprise Server, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="07ac5-177">Utilisez cette rubrique pour supprimer des régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="07ac5-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="07ac5-178">Pour supprimer une zone réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-178">To delete a network region</span></span>

1.  <span data-ttu-id="07ac5-179">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="07ac5-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="07ac5-180">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="07ac5-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="07ac5-181">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="07ac5-182">Dans la page **zone** , cliquez sur la zone que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="07ac5-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="07ac5-183">Vous pouvez supprimer plusieurs régions à la fois.</span><span class="sxs-lookup"><span data-stu-id="07ac5-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="07ac5-184">Pour cela, appuyez sur CTRL et sélectionnez plusieurs régions tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="07ac5-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="07ac5-185">Vous pouvez sélectionner toutes les régions dans le \*\*\*\* menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="07ac5-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="07ac5-186">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="07ac5-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="07ac5-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="07ac5-188">Une région réseau ne peut pas être supprimée si elle est associée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="07ac5-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="07ac5-189">Si vous tentez de supprimer une région associée à un site, un message d’erreur s’affiche.</span><span class="sxs-lookup"><span data-stu-id="07ac5-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="07ac5-190">Pour déterminer si une région est associée à des sites, sélectionnez la région, puis cliquez sur **afficher les détails** dans le menu **modifier** .</span><span class="sxs-lookup"><span data-stu-id="07ac5-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="07ac5-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="07ac5-191">See Also</span></span>

[<span data-ttu-id="07ac5-192">Gestion des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="07ac5-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="07ac5-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="07ac5-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="07ac5-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="07ac5-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="07ac5-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="07ac5-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="07ac5-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="07ac5-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
