---
title: Gestion du contrôle d’admission des appels pour les sites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les sites réseau sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média.
ms.openlocfilehash: ec2a3dda70bdd4b952169ca663ca271b76f98481
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817513"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="ba084-103">Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ba084-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="ba084-104">Les sites réseau sont les bureaux ou les emplacements dans chaque région du réseau de déploiement d’admission des appels (CAC), de E9-1-1 et de contournement de média.</span><span class="sxs-lookup"><span data-stu-id="ba084-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="ba084-105">Suivez les procédures décrites dans cet article pour configurer le contrôle d’admission des appels pour les sites réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="ba084-106">Configurer les liens du site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-106">Configure network site links</span></span>

<span data-ttu-id="ba084-107">Dans le cadre d’une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies entre site réseau qui définissent les limitations de bande passante entre les sites qui sont directement liés.</span><span class="sxs-lookup"><span data-stu-id="ba084-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="ba084-108">Lorsque les sites réseau partagent un lien direct, les limites de bande passante pour les connexions audio et vidéo peuvent être définies entre ces deux sites.</span><span class="sxs-lookup"><span data-stu-id="ba084-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="ba084-109">Vous ne pouvez pas utiliser le panneau de configuration Skype entreprise Server pour configurer des stratégies de site réseau, et ce n’est possible qu’en utilisant des applets de commande de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba084-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="ba084-110">Vous pouvez créer, modifier et supprimer un lien de site réseau (également connu sous le nom de stratégie intersite réseau) dans Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba084-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="ba084-111">Pour créer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-111">To create a network site link</span></span>

1.  <span data-ttu-id="ba084-112">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ba084-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ba084-113">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba084-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba084-114">À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration :</span><span class="sxs-lookup"><span data-stu-id="ba084-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="ba084-115">Cet exemple crée un lien de site réseau intitulé Reno\_Portland qui définit les limites de bande passante entre les sites réseau Reno et Portland.</span><span class="sxs-lookup"><span data-stu-id="ba084-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="ba084-116">Les sites réseau et le profil de la stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="ba084-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="ba084-117">Pour obtenir une description détaillée des paramètres, consultez la rubrique [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ba084-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="ba084-118">Pour récupérer la liste des profils de stratégie de bande passante qui peuvent être appliqués au lien site réseau, appelez l’applet **de passe Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="ba084-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="ba084-119">Pour plus d’informations, consultez la rubrique [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="ba084-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="ba084-120">Pour modifier un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-120">To modify a network site link</span></span>

1.  <span data-ttu-id="ba084-121">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ba084-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ba084-122">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba084-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba084-123">Utilisez l’applet de connexion **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné.</span><span class="sxs-lookup"><span data-stu-id="ba084-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="ba084-124">Vous pouvez modifier l’un ou l’autre des sites connectés, et vous pouvez modifier le profil de la stratégie de bande passante associé au lien.</span><span class="sxs-lookup"><span data-stu-id="ba084-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="ba084-125">Voici un exemple de modification du profil de la stratégie de bande passante d’un lien\_de site nommé Reno Portland :</span><span class="sxs-lookup"><span data-stu-id="ba084-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="ba084-126">Pour obtenir une description détaillée des paramètres, consultez la rubrique [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ba084-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="ba084-127">Pour supprimer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-127">To delete a network site link</span></span>

1.  <span data-ttu-id="ba084-128">Ouvrez une session sur l’ordinateur sur lequel Skype entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="ba084-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="ba084-129">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="ba084-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="ba084-130">Utilisez l’applet de connexion **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="ba084-131">Dans l’exemple suivant, le lien\_vers le site réseau de Portland de Reno est supprimé :</span><span class="sxs-lookup"><span data-stu-id="ba084-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="ba084-132">Pour obtenir une description détaillée des paramètres, consultez la rubrique [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="ba084-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="ba084-133">Afficher les informations relatives au site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-133">View network site information</span></span>

<span data-ttu-id="ba084-134">Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré.</span><span class="sxs-lookup"><span data-stu-id="ba084-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ba084-135">Vous pouvez afficher les informations relatives à un site réseau dans le panneau de configuration Skype entreprise Server ou dans Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ba084-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="ba084-136">Pour afficher les informations sur le site réseau dans Skype entreprise Server panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="ba084-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="ba084-137">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ba084-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba084-138">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba084-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba084-139">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.</span><span class="sxs-lookup"><span data-stu-id="ba084-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ba084-140">Sur la page du **site** , cliquez sur le site que vous voulez afficher.</span><span class="sxs-lookup"><span data-stu-id="ba084-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ba084-141">Vous ne pouvez afficher que les informations relatives à un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="ba084-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="ba084-142">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ba084-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ba084-143">Affichage des informations sur le site réseau à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba084-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="ba084-144">Vous pouvez afficher les informations de site réseau en utilisant Windows PowerShell et l’applet de connexion Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="ba084-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="ba084-145">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba084-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="ba084-146">Pour afficher les informations relatives au site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-146">To view network site information</span></span>

  - <span data-ttu-id="ba084-147">Pour afficher des informations sur tous les sites de votre réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="ba084-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="ba084-148">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="ba084-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="ba084-149">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="ba084-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="ba084-150">Créer ou modifier des sites réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-150">Create or modify network sites</span></span> 

<span data-ttu-id="ba084-151">Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré.</span><span class="sxs-lookup"><span data-stu-id="ba084-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ba084-152">Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour configurer les sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="ba084-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="ba084-153">Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="ba084-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="ba084-154">Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ba084-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="ba084-155">Le panneau de configuration Skype entreprise Server vous permet de créer, de modifier et de supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="ba084-156">Pour créer ou modifier un site réseau, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="ba084-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="ba084-157">Pour créer un site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-157">To create a network site</span></span>

1.  <span data-ttu-id="ba084-158">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ba084-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba084-159">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba084-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba084-160">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.</span><span class="sxs-lookup"><span data-stu-id="ba084-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ba084-161">Sur la page du **site** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ba084-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="ba084-162">Dans **nouveau site**, tapez un nom pour ce site dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="ba084-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ba084-163">Les noms de site doivent être uniques dans le déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba084-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="ba084-164">Dans la liste déroulante **région** , sélectionnez une région réseau à associer à ce site.</span><span class="sxs-lookup"><span data-stu-id="ba084-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="ba084-165">Facultatif Si vous voulez appliquer des limitations de bande passante pour les appels audio ou vidéo vers ce site, sélectionnez le profil de la stratégie de bande passante avec les paramètres appropriés dans la liste déroulante **stratégie de bande passante** .</span><span class="sxs-lookup"><span data-stu-id="ba084-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="ba084-166">Vous pouvez afficher les détails des profils de stratégie de bande passante disponibles ou créer un nouveau profil de stratégie de bande passante dans la page profil de la **stratégie** du groupe de **Configuration réseau** .</span><span class="sxs-lookup"><span data-stu-id="ba084-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="ba084-167">Pour plus d’informations, consultez [gestion des profils de stratégie de bande passante réseau](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ba084-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="ba084-168">Facultatif Si vous voulez fournir des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** .</span><span class="sxs-lookup"><span data-stu-id="ba084-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ba084-169">La stratégie d’emplacement attribue des paramètres de 9-1-1 et d’emplacement client spécifiques au site.</span><span class="sxs-lookup"><span data-stu-id="ba084-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="ba084-170">Vous pouvez afficher les détails des stratégies d’emplacement disponibles ou créer une nouvelle stratégie d’emplacement à partir de la page **stratégie d’emplacement** du groupe de **Configuration réseau** .</span><span class="sxs-lookup"><span data-stu-id="ba084-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="ba084-171">Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur ce site qui ne peut pas être exprimé uniquement par le nom.</span><span class="sxs-lookup"><span data-stu-id="ba084-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="ba084-172">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ba084-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ba084-173">Vous n’utilisez pas la table de **sous-réseaux associés** lorsque vous créez un site réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="ba084-174">Vous associez un sous-réseau à un site lors de la création ou de la modification du sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="ba084-175">Pour plus d’informations, reportez-vous à [gestion des sous-réseaux réseau](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="ba084-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="ba084-176">Pour modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-176">To modify a network site</span></span>

1.  <span data-ttu-id="ba084-177">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ba084-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba084-178">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba084-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba084-179">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.</span><span class="sxs-lookup"><span data-stu-id="ba084-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ba084-180">Sur la page du **site** , cliquez sur le site que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="ba084-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="ba084-181">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="ba084-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="ba084-182">Dans la page **modifier le site** , vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associées au site.</span><span class="sxs-lookup"><span data-stu-id="ba084-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="ba084-183">Pour plus d’informations, reportez-vous [à créer un site réseau](#to-create-a-network-site) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="ba084-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="ba084-184">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="ba084-184">Click **Commit**.</span></span>

<span data-ttu-id="ba084-185">Vous ne pouvez pas modifier le tableau sous- **réseaux associés** sur cette page.</span><span class="sxs-lookup"><span data-stu-id="ba084-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="ba084-186">La liste des sous-réseaux associés est fournie à des fins de référence afin de savoir quels sous-réseaux seront affectés lorsque vous modifiez les paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="ba084-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="ba084-187">Supprimer un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="ba084-187">Delete an existing network site</span></span>

<span data-ttu-id="ba084-188">Les sites réseau sont les bureaux ou les emplacements configurés dans chaque région d’un contrôle d’admission des appels (CAC) ou un déploiement 9-1-1 amélioré.</span><span class="sxs-lookup"><span data-stu-id="ba084-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="ba084-189">Vous pouvez utiliser le panneau de configuration Skype entreprise Server pour configurer les sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="ba084-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="ba084-190">Par exemple, une région réseau pour l’Amérique du Nord peut être associée à des sites réseaux tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="ba084-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="ba084-191">Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a pas de limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="ba084-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="ba084-192">Le panneau de configuration Skype entreprise Server vous permet de créer, de modifier et de supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="ba084-193">Utilisez la procédure suivante pour supprimer un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="ba084-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="ba084-194">Pour plus d’informations sur la création ou la modification de sites réseau, voir [gestion du contrôle d’admission des appels pour les sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="ba084-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="ba084-195">Pour supprimer un site réseau</span><span class="sxs-lookup"><span data-stu-id="ba084-195">To delete a network site</span></span>

1.  <span data-ttu-id="ba084-196">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="ba084-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ba084-197">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ba084-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="ba084-198">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis cliquez sur **site**.</span><span class="sxs-lookup"><span data-stu-id="ba084-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="ba084-199">Sur la page du **site** , cliquez sur le site que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="ba084-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="ba084-200">Vous pouvez supprimer plusieurs sites à la fois.</span><span class="sxs-lookup"><span data-stu-id="ba084-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="ba084-201">Pour cela, appuyez sur CTRL et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="ba084-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="ba084-202">Pour sélectionner tous les sites, dans le menu **Edition** , cliquez sur **Sélectionner tout** .</span><span class="sxs-lookup"><span data-stu-id="ba084-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="ba084-203">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="ba084-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="ba084-204">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba084-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="ba084-205">Vous ne pouvez pas supprimer un site réseau s’il est associé à un sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="ba084-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="ba084-206">Si vous tentez de supprimer un site associé à un sous-réseau, vous recevez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="ba084-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="ba084-207">Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur **afficher les détails** dans le menu **modifier** .</span><span class="sxs-lookup"><span data-stu-id="ba084-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="ba084-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ba084-208">See Also</span></span>


[<span data-ttu-id="ba084-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ba084-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="ba084-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ba084-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ba084-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ba084-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ba084-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ba084-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="ba084-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ba084-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="ba084-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ba084-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="ba084-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ba084-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="ba084-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ba084-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="ba084-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="ba084-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
