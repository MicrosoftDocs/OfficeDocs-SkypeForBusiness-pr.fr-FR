---
title: Gestion des régions réseau
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Région réseau * sont les concentrateurs réseau ou des dorsales principales utilisées dans la configuration de contournement des médias, E9-1-1 et contrôle d’admission des appels appel.
ms.openlocfilehash: ea574fe981af679e4d841d786daf04460d1fb7c3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877628"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a><span data-ttu-id="ff72c-103">Gestion des régions réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ff72c-103">Managing network regions in Skype for Business Server</span></span>

<span data-ttu-id="ff72c-104">*Régions réseau* sont les concentrateurs réseau ou des dorsales principales utilisées dans la configuration de contournement des médias, E9-1-1 et contrôle d’admission des appels appel.</span><span class="sxs-lookup"><span data-stu-id="ff72c-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ff72c-105">Utilisez les procédures suivantes pour afficher, créer ou modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="ff72c-106">Par exemple, si vous avez déjà créé des régions réseau pour une fonctionnalité de voix, il est inutile créer de nouvelles régions de réseau ; autres fonctionnalités voix entreprise utilisera ces mêmes zones réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ff72c-107">Toutefois, il est possible que vous soyez obligé de modifier la définition d’une région réseau existante pour appliquer des paramètres spécifiques à une fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="ff72c-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ff72c-108">Par exemple, si vous avez créé des régions réseau pour le service E9-1-1 (régions n’exigeant aucun site central associé), puis que vous déployez le contrôle d’admission des appels, vous devez modifier les définitions des régions réseau afin de spécifier un site central.</span><span class="sxs-lookup"><span data-stu-id="ff72c-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> 

<span data-ttu-id="ff72c-109">Utilisez les procédures dans cet article pour afficher les informations de région de réseau ou créer, modifier ou supprimer des régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-109">Use the procedures in this article to view network region information or create, modify, or delete network regions.</span></span> 

## <a name="view-network-region-information"></a><span data-ttu-id="ff72c-110">Afficher les informations de région réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-110">View network region information</span></span> 


<span data-ttu-id="ff72c-111">Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ff72c-111">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ff72c-112">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ff72c-112">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ff72c-113">Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ff72c-113">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ff72c-114">Vous pouvez utiliser Skype pour Business Server Control Panel pour afficher les régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-114">You can use Skype for Business Server Control Panel to view network regions.</span></span> <span data-ttu-id="ff72c-115">Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos.</span><span class="sxs-lookup"><span data-stu-id="ff72c-115">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ff72c-116">Utilisez cette rubrique pour afficher des régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="ff72c-116">Use this topic to view existing network regions.</span></span> 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a><span data-ttu-id="ff72c-117">Pour afficher des informations sur une région de réseau avec Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="ff72c-117">To view information about a network region with Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ff72c-118">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ff72c-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff72c-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ff72c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff72c-120">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-120">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ff72c-121">Dans la page **région** , cliquez sur la région que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="ff72c-121">On the **Region** page, click the region you want to view.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ff72c-122">Vous ne pouvez afficher qu’une région à la fois.</span><span class="sxs-lookup"><span data-stu-id="ff72c-122">You can only view one region at a time.</span></span>

5.  <span data-ttu-id="ff72c-123">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-123">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ff72c-124">Affichage des informations de région réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ff72c-124">Viewing network region information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ff72c-125">Vous pouvez afficher les informations de région réseau à l’aide de Windows PowerShell et l’applet de commande **Get-CsNetworkRegion** .</span><span class="sxs-lookup"><span data-stu-id="ff72c-125">You can view network region information by using Windows PowerShell and the **Get-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ff72c-126">Vous pouvez exécuter cette applet de commande à partir de la Skype pour Business Server Management Shell ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff72c-126">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-region-information"></a><span data-ttu-id="ff72c-127">Pour afficher les informations de région réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-127">To view network region information</span></span>

  - <span data-ttu-id="ff72c-128">Pour afficher des informations sur toutes les régions de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="ff72c-128">To view information about all your network regions, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegion
    
    <span data-ttu-id="ff72c-129">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="ff72c-129">That will return information similar to this:</span></span>
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

<span data-ttu-id="ff72c-130">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) .</span><span class="sxs-lookup"><span data-stu-id="ff72c-130">For more information, see the help topic for the [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) cmdlet.</span></span>


## <a name="create-or-modify-network-regions"></a><span data-ttu-id="ff72c-131">Créer ou modifier des régions réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-131">Create or modify network regions</span></span> 

<span data-ttu-id="ff72c-132">Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ff72c-132">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ff72c-133">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ff72c-133">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ff72c-134">Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ff72c-134">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ff72c-135">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-135">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ff72c-136">Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos.</span><span class="sxs-lookup"><span data-stu-id="ff72c-136">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ff72c-137">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-137">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ff72c-138">Utilisez cette rubrique pour créer et modifier des régions réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-138">Use this topic to create and modify network regions.</span></span> 

### <a name="to-create-a-network-region"></a><span data-ttu-id="ff72c-139">Pour créer une région de réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-139">To create a network region</span></span>

1.  <span data-ttu-id="ff72c-140">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ff72c-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff72c-141">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ff72c-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff72c-142">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-142">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ff72c-143">Dans la page **région** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-143">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="ff72c-144">Dans la page **Nouvelle région** , tapez une valeur dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="ff72c-144">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="ff72c-145">Cette valeur doit être unique au sein de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="ff72c-145">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ff72c-146">Dans la liste déroulante **site Central** , sélectionnez le site central pour cette région réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-146">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="ff72c-147">La case à cocher **Activer le chemin d’accès de substitution audio** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ff72c-147">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="ff72c-148">Ce champ détermine si les appels audio seront acheminés via un chemin alternatif si la bande passante adéquate n’existe pas dans le chemin principal.</span><span class="sxs-lookup"><span data-stu-id="ff72c-148">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="ff72c-149">Désactivez cette case à cocher uniquement si vous avez besoin désactiver le déchargement vers Internet.</span><span class="sxs-lookup"><span data-stu-id="ff72c-149">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="ff72c-150">Si certains de vos appels seront des appels Internet, cette case à cocher doit être activée, quel que soit les paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ff72c-150">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="ff72c-151">La case à cocher **Activer le chemin d’accès de substitution vidéo** est activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ff72c-151">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="ff72c-152">Ce champ détermine si les appels vidéo seront acheminés via un chemin alternatif si la bande passante adéquate n’existe pas dans le chemin principal.</span><span class="sxs-lookup"><span data-stu-id="ff72c-152">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="ff72c-153">Désactivez cette case à cocher uniquement si vous avez besoin désactiver le déchargement vers Internet.</span><span class="sxs-lookup"><span data-stu-id="ff72c-153">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="ff72c-154">Si certains de vos appels seront des appels Internet, cette case à cocher doit être activée, quel que soit les paramètres de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ff72c-154">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="ff72c-155">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur cette région ne suffit pas au nom seul.</span><span class="sxs-lookup"><span data-stu-id="ff72c-155">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ff72c-156">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-156">Click **Commit**.</span></span>

<span data-ttu-id="ff72c-157">La table **sites associés** n’est pas utilisée pour la création d’une région de réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-157">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="ff72c-158">Vous associez un site à une région lorsque vous créez ou modifiez le site.</span><span class="sxs-lookup"><span data-stu-id="ff72c-158">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="ff72c-159">Pour plus d’informations, voir [Managing le contrôle d’admission des appels d’appel pour les sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="ff72c-159">For details, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>

### <a name="to-modify-a-network-region"></a><span data-ttu-id="ff72c-160">Pour modifier une région réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-160">To modify a network region</span></span>

1.  <span data-ttu-id="ff72c-161">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ff72c-161">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff72c-162">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ff72c-162">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff72c-163">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-163">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ff72c-164">Dans la page **région** , cliquez sur la région que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="ff72c-164">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="ff72c-165">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-165">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ff72c-166">Dans la page **Modifier la région** , vous pouvez modifier les paramètres d’activation et désactivation des paramètres audio / vidéo des chemins d’accès de substitution et modifier la description (pour plus d’informations, consultez la section « pour créer une région réseau » plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ff72c-166">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="ff72c-167">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-167">Click **Commit**.</span></span>

<span data-ttu-id="ff72c-168">Vous ne pouvez pas modifier les **sites associés** sur cette page.</span><span class="sxs-lookup"><span data-stu-id="ff72c-168">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="ff72c-169">La liste des sites associés est fournie pour référence et vous connaissez les sites qui seront affectés lorsque vous modifiez les paramètres de zone.</span><span class="sxs-lookup"><span data-stu-id="ff72c-169">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>


## <a name="delete-existing-network-regions"></a><span data-ttu-id="ff72c-170">Supprimer des régions réseau existantes</span><span class="sxs-lookup"><span data-stu-id="ff72c-170">Delete existing network regions</span></span> 

<span data-ttu-id="ff72c-171">Une région réseau relie des différentes parties d’un réseau entre plusieurs zones géographiques.</span><span class="sxs-lookup"><span data-stu-id="ff72c-171">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="ff72c-172">Chaque région réseau doit être associée à un site central.</span><span class="sxs-lookup"><span data-stu-id="ff72c-172">Every network region must be associated with a central site.</span></span> <span data-ttu-id="ff72c-173">Le site central est le site du centre de données sur lequel s’exécute le service de stratégie de bande passante appel d’admission des appels (CAC) de contrôle.</span><span class="sxs-lookup"><span data-stu-id="ff72c-173">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="ff72c-174">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer les régions de réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-174">You can use the Skype for Business Server Control Panel to configure network regions.</span></span> <span data-ttu-id="ff72c-175">Régions de réseau incluent les paramètres qui déterminent si les autres chemins via Internet sont autorisés pour les connexions audio et vidéos.</span><span class="sxs-lookup"><span data-stu-id="ff72c-175">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="ff72c-176">À partir de Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier ou supprimer une région réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-176">From the Skype for Business Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="ff72c-177">Utilisez cette rubrique pour supprimer des régions réseau existantes.</span><span class="sxs-lookup"><span data-stu-id="ff72c-177">Use this topic to delete existing network regions.</span></span> 

### <a name="to-delete-a-network-region"></a><span data-ttu-id="ff72c-178">Pour supprimer une région réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-178">To delete a network region</span></span>

1.  <span data-ttu-id="ff72c-179">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ff72c-179">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ff72c-180">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="ff72c-180">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ff72c-181">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **région**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-181">In the left navigation bar, click **Network Configuration**, and then click **Region**.</span></span>

4.  <span data-ttu-id="ff72c-182">Dans la page **région** , cliquez sur la région que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="ff72c-182">On the **Region** page, click the region you want to delete.</span></span>
  
    > [!NOTE]  
    > <span data-ttu-id="ff72c-183">Vous pouvez supprimer plusieurs régions à la fois.</span><span class="sxs-lookup"><span data-stu-id="ff72c-183">You can delete more than one region at a time.</span></span> <span data-ttu-id="ff72c-184">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs régions tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="ff72c-184">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="ff72c-185">Ou, pour sélectionner toutes les régions, cliquez sur **Sélectionner tout** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="ff72c-185">Or, to select all regions, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ff72c-186">Dans le menu **Edition** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-186">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ff72c-187">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff72c-187">Click **OK**.</span></span>


    > [!WARNING]  
    > <span data-ttu-id="ff72c-188">Une région de réseau ne peut pas être supprimée si elle est associée à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="ff72c-188">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="ff72c-189">Si vous tentez de supprimer une région associée à un site, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="ff72c-189">If you attempt to remove a region associated with a site, you will receive an error message.</span></span> <span data-ttu-id="ff72c-190">Pour voir si une région est associée à tous les sites, sélectionnez la région, puis sur **Afficher les détails** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="ff72c-190">To see if a region is associated with any sites, select the region and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="ff72c-191">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff72c-191">See Also</span></span>

[<span data-ttu-id="ff72c-192">Gestion des itinéraires de région réseau</span><span class="sxs-lookup"><span data-stu-id="ff72c-192">Managing network region routes</span></span>](managing-network-region-routes.md)

[<span data-ttu-id="ff72c-193">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ff72c-193">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[<span data-ttu-id="ff72c-194">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ff72c-194">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[<span data-ttu-id="ff72c-195">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ff72c-195">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[<span data-ttu-id="ff72c-196">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ff72c-196">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
