---
title: Gérer le contrôle d’admission des appels pour les sites d’appel
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sites de réseau sont les bureaux ou emplacements dans chaque région réseau de contrôle d’admission des appels (CAC), E9-1-1 et les déploiements de contournement de média d’appel.
ms.openlocfilehash: 53140cf03110991f2c757e5d52e30a6c7db1d7de
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199223"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="b7482-103">Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b7482-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="b7482-104">Sites de réseau sont les bureaux ou emplacements dans chaque région réseau de contrôle d’admission des appels (CAC), E9-1-1 et les déploiements de contournement de média d’appel.</span><span class="sxs-lookup"><span data-stu-id="b7482-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="b7482-105">Utilisez les procédures décrites dans cet article pour configurer le contrôle d’admission des appels d’appel pour les sites réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="b7482-106">Configurer les liens de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-106">Configure network site links</span></span>

<span data-ttu-id="b7482-107">Dans une configuration de contrôle (CAC) d’admission des appels, vous pouvez créer des stratégies inter-sites qui définissent les limitations de bande passante entre les sites qui sont directement liés réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="b7482-108">Lorsque les sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéos peuvent être définies entre ces deux sites.</span><span class="sxs-lookup"><span data-stu-id="b7482-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="b7482-109">Vous ne pouvez pas utiliser le Skype pour Business Server Control Panel pour configurer les stratégies de site réseau, cette opération peut être effectuée uniquement à l’aide des applets de commande de le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7482-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b7482-110">Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé une stratégie intersite réseau) de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7482-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="b7482-111">Pour créer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-111">To create a network site link</span></span>

1.  <span data-ttu-id="b7482-112">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b7482-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="b7482-113">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b7482-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7482-114">À partir de l’invite de commandes, tapez la commande suivante, en remplaçant les valeurs valides pour votre configuration :</span><span class="sxs-lookup"><span data-stu-id="b7482-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="b7482-115">Cet exemple crée un nouveau lien de site réseau appelé Reno\_Portland qui définit les restrictions de bande passante entre les sites de réseau Reno et Portland.</span><span class="sxs-lookup"><span data-stu-id="b7482-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="b7482-116">Les sites réseau et le profil de stratégie de bande passante doivent déjà exister avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="b7482-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="b7482-117">Pour obtenir des descriptions détaillées de paramètre, voir [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="b7482-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="b7482-118">Pour récupérer une liste de profils de stratégie de bande passante qui peuvent être appliqués à la liaison de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="b7482-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="b7482-119">Pour plus d’informations, voir [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="b7482-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="b7482-120">Pour modifier un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-120">To modify a network site link</span></span>

1.  <span data-ttu-id="b7482-121">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b7482-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="b7482-122">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b7482-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7482-123">Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné.</span><span class="sxs-lookup"><span data-stu-id="b7482-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="b7482-124">Vous pouvez modifier un (ou les deux) ou les sites connectés et vous pouvez modifier le profil de stratégie de bande passante associé au lien.</span><span class="sxs-lookup"><span data-stu-id="b7482-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="b7482-125">Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno\_Portland :</span><span class="sxs-lookup"><span data-stu-id="b7482-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="b7482-126">Pour obtenir des descriptions détaillées de paramètre, voir [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="b7482-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="b7482-127">Pour supprimer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-127">To delete a network site link</span></span>

1.  <span data-ttu-id="b7482-128">Ouvrez une session l’ordinateur où Skype pour Business Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b7482-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="b7482-129">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b7482-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="b7482-130">Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="b7482-131">L’exemple suivant supprime le Reno\_lien de site réseau Portland :</span><span class="sxs-lookup"><span data-stu-id="b7482-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="b7482-132">Pour obtenir des descriptions détaillées de paramètre, voir [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="b7482-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="b7482-133">Afficher les informations de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-133">View network site information</span></span>

<span data-ttu-id="b7482-134">Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b7482-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b7482-135">Vous pouvez afficher des informations de site réseau dans le deux Skype pour le panneau de configuration serveur Business ou le Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b7482-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="b7482-136">Pour afficher les informations de site réseau dans Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="b7482-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="b7482-137">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b7482-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7482-138">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b7482-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7482-139">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="b7482-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="b7482-140">Dans la page du **Site** , cliquez sur le site que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="b7482-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b7482-141">Vous ne pouvez afficher des informations pour un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="b7482-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="b7482-142">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b7482-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b7482-143">Affichage des informations de site réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7482-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b7482-144">Vous pouvez afficher les informations de site réseau à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="b7482-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="b7482-145">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7482-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="b7482-146">Pour afficher les informations de site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-146">To view network site information</span></span>

  - <span data-ttu-id="b7482-147">Pour afficher des informations sur tous les sites de votre réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="b7482-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="b7482-148">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="b7482-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="b7482-149">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="b7482-149">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="b7482-150">Créer ou modifier des sites réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-150">Create or modify network sites</span></span> 

<span data-ttu-id="b7482-151">Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b7482-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b7482-152">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="b7482-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="b7482-153">Par exemple, une région de réseau pour l’Amérique du Nord peut être associée à des sites de réseaux tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="b7482-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="b7482-154">Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a aucune limitation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b7482-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="b7482-155">À partir de la Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier et supprimer les sites de réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="b7482-156">Utilisez les procédures suivantes pour créer ou modifier un site réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="b7482-157">Pour créer un site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-157">To create a network site</span></span>

1.  <span data-ttu-id="b7482-158">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b7482-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7482-159">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b7482-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7482-160">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="b7482-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="b7482-161">Dans la page du **Site** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b7482-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="b7482-162">Dans le **Nouveau Site**, tapez un nom pour ce site dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="b7482-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b7482-163">Les noms de site doivent être uniques dans le Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b7482-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="b7482-164">Dans la liste déroulante **région** , sélectionnez une région réseau à associer à ce site.</span><span class="sxs-lookup"><span data-stu-id="b7482-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="b7482-165">(Facultatif) Si vous souhaitez placer des restrictions de bande passante pour les appels audio ou vidéos à ce site, sélectionnez le profil de stratégie de bande passante avec les paramètres appropriés à partir de la liste déroulante **stratégie de bande passante** .</span><span class="sxs-lookup"><span data-stu-id="b7482-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="b7482-166">Vous pouvez afficher les détails des profils de stratégie de bande passante disponible, ou créer un nouveau profil de stratégie de bande passante, sur la page **Profil de stratégie** de groupe de la **Configuration réseau** .</span><span class="sxs-lookup"><span data-stu-id="b7482-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="b7482-167">Pour plus d’informations, voir [profils de stratégie de bande passante réseau Managing](managing-network-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b7482-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="b7482-168">(Facultatif) Si vous souhaitez fournir des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **stratégie d’emplacement** .</span><span class="sxs-lookup"><span data-stu-id="b7482-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b7482-169">La stratégie d’emplacement affecte spécifique Enhanced 9-1-1 (E9-1-1) et client paramètres d’emplacement pour le site.</span><span class="sxs-lookup"><span data-stu-id="b7482-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="b7482-170">Vous pouvez afficher les détails de stratégies d’emplacement disponibles, ou créer une nouvelle stratégie d’emplacement, à partir de la page **Stratégie d’emplacement** du groupe **Configuration réseau** .</span><span class="sxs-lookup"><span data-stu-id="b7482-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="b7482-171">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site ne suffit pas au nom seul.</span><span class="sxs-lookup"><span data-stu-id="b7482-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="b7482-172">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b7482-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b7482-173">Vous n’utilisez pas la table de **Sous-réseaux associés** lorsque vous créez un nouveau site réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="b7482-174">Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="b7482-175">Pour plus d’informations, voir [Gestion des sous-réseaux](managing-network-subnets.md).</span><span class="sxs-lookup"><span data-stu-id="b7482-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="b7482-176">Pour modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-176">To modify a network site</span></span>

1.  <span data-ttu-id="b7482-177">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b7482-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7482-178">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b7482-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7482-179">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="b7482-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="b7482-180">Dans la page du **Site** , cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="b7482-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="b7482-181">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b7482-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b7482-182">Dans la page **Modifier le Site** , vous pouvez modifier la description, la région, profil de stratégie de bande passante et stratégie d’emplacement associés au site.</span><span class="sxs-lookup"><span data-stu-id="b7482-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="b7482-183">Pour plus d’informations, voir [créer un site réseau](#to-create-a-network-site) ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="b7482-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="b7482-184">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b7482-184">Click **Commit**.</span></span>

<span data-ttu-id="b7482-185">Vous ne pouvez pas modifier la table de **Sous-réseaux associés** sur cette page.</span><span class="sxs-lookup"><span data-stu-id="b7482-185">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="b7482-186">La liste des sous-réseaux associés est fournie pour référence afin que vous connaissez les sous-réseaux seront affectés lorsque vous modifiez les paramètres du site.</span><span class="sxs-lookup"><span data-stu-id="b7482-186">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="b7482-187">Supprimer un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="b7482-187">Delete an existing network site</span></span>

<span data-ttu-id="b7482-188">Sites de réseau sont les bureaux et emplacements configurés au sein de chaque région du déploiement d’une le contrôle d’admission des appels (CAC) ou Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="b7482-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="b7482-189">Vous pouvez utiliser la Skype pour Business Server Control Panel pour configurer des sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="b7482-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="b7482-190">Par exemple, une région de réseau pour l’Amérique du Nord peut être associée à des sites de réseaux tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="b7482-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="b7482-191">Un site réseau CAC doit être créé pour chaque site au sein d’une organisation, même si ce site n’a aucune limitation de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b7482-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="b7482-192">À partir de la Skype pour le panneau de configuration serveur Business, vous pouvez créer, modifier et supprimer les sites de réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="b7482-193">Utilisez la procédure suivante pour supprimer un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="b7482-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="b7482-194">Pour plus d’informations sur la création ou modification des sites réseau, voir [Managing le contrôle d’admission des appels d’appel pour les sites](managing-call-admission-control-for-sites.md).</span><span class="sxs-lookup"><span data-stu-id="b7482-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="b7482-195">Pour supprimer un site réseau</span><span class="sxs-lookup"><span data-stu-id="b7482-195">To delete a network site</span></span>

1.  <span data-ttu-id="b7482-196">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b7482-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b7482-197">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b7482-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b7482-198">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **sites**.</span><span class="sxs-lookup"><span data-stu-id="b7482-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="b7482-199">Dans la page du **Site** , cliquez sur le site que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b7482-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b7482-200">Vous pouvez supprimer plusieurs sites à la fois.</span><span class="sxs-lookup"><span data-stu-id="b7482-200">You can delete more than one site at a time.</span></span> <span data-ttu-id="b7482-201">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs sites tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="b7482-201">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="b7482-202">Ou, pour sélectionner tous les sites, cliquez sur **Sélectionner tout** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="b7482-202">Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="b7482-203">Dans le menu **Edition** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b7482-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="b7482-204">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7482-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="b7482-205">Vous ne pouvez pas supprimer un site réseau si elle est associée à un sous-réseau de réseau.</span><span class="sxs-lookup"><span data-stu-id="b7482-205">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="b7482-206">Si vous tentez de supprimer un site associé à un sous-réseau, vous recevrez un message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="b7482-206">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="b7482-207">Pour voir si un site est associé à des sous-réseaux, cliquez sur le site, puis cliquez sur **Afficher les détails** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="b7482-207">To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="b7482-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7482-208">See Also</span></span>


[<span data-ttu-id="b7482-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b7482-209">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="b7482-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b7482-210">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="b7482-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b7482-211">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="b7482-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b7482-212">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="b7482-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b7482-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="b7482-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7482-214">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="b7482-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7482-215">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="b7482-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7482-216">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="b7482-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="b7482-217">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
