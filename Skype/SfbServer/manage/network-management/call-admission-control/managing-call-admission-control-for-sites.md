---
title: Gestion du contrôle d’admission des appels pour les sites
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
description: Les sites réseau sont les bureaux ou emplacements au sein de chaque région réseau des déploiements du service Contrôle d’admission des appels, du service E9-1-1 ou du contournement de médias.
ms.openlocfilehash: 0b339f15e53dd94bda655884f70c041f9da9e5a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118563"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a><span data-ttu-id="1b433-103">Gestion du contrôle d’admission des appels pour les sites dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b433-103">Managing call admission control for sites in Skype for Business Server</span></span>

<span data-ttu-id="1b433-104">Les sites réseau sont les bureaux ou emplacements au sein de chaque région réseau des déploiements du service Contrôle d’admission des appels, du service E9-1-1 ou du contournement de médias.</span><span class="sxs-lookup"><span data-stu-id="1b433-104">Network sites are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="1b433-105">Utilisez les procédures de cet article pour configurer le contrôle d’admission des appels pour les sites réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-105">Use the procedures in this article to configure call admission control for network sites.</span></span>

## <a name="configure-network-site-links"></a><span data-ttu-id="1b433-106">Configurer des liens de sites réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-106">Configure network site links</span></span>

<span data-ttu-id="1b433-107">Dans une configuration de contrôle d’admission des appels (CAC), vous pouvez créer des stratégies réseau intersessant qui définissent des limites de bande passante entre les sites qui sont directement liés.</span><span class="sxs-lookup"><span data-stu-id="1b433-107">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="1b433-108">Quand des sites de réseau partagent un lien direct, des restrictions de bande passante pour les connexions audio et vidéo peuvent être définies pour lesdits sites.</span><span class="sxs-lookup"><span data-stu-id="1b433-108">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="1b433-109">Vous ne pouvez pas utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des stratégies de site réseau. Pour ce faire, vous pouvez uniquement utiliser les cmdlets de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b433-109">You cannot use the Skype for Business Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="1b433-110">Vous pouvez créer, modifier et supprimer un lien de site réseau (également appelé stratégie intersessant réseau) à partir de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b433-110">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Skype for Business Server Management Shell.</span></span>

### <a name="to-create-a-network-site-link"></a><span data-ttu-id="1b433-111">Pour créer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-111">To create a network site link</span></span>

1.  <span data-ttu-id="1b433-112">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1b433-112">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1b433-113">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1b433-113">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1b433-114">À l’invite de commandes, tapez la commande suivante en spécifiant les valeurs valides pour votre configuration :</span><span class="sxs-lookup"><span data-stu-id="1b433-114">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="1b433-115">Cet exemple crée un lien de site réseau nommé Reno Portland qui définit des limites de bande passante entre les sites réseau \_ Reno et Portland.</span><span class="sxs-lookup"><span data-stu-id="1b433-115">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="1b433-116">Les sites réseau et le profil de stratégie de bande passante doivent être existants avant d’exécuter cette commande.</span><span class="sxs-lookup"><span data-stu-id="1b433-116">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="1b433-117">Pour obtenir des descriptions détaillées des paramètres, voir [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1b433-117">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](/powershell/module/skype/New-CsNetworkInterSitePolicy).</span></span> <span data-ttu-id="1b433-118">Pour récupérer une liste des profils de stratégie de bande passante pouvant être appliqués au lien de site réseau, appelez l’applet de commande **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="1b433-118">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="1b433-119">Pour plus d’informations, [voir Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="1b433-119">For details, see [Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span></span>

### <a name="to-modify-a-network-site-link"></a><span data-ttu-id="1b433-120">Pour modifier un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-120">To modify a network site link</span></span>

1.  <span data-ttu-id="1b433-121">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1b433-121">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1b433-122">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1b433-122">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1b433-123">Utilisez l’applet de commande **Set-CsNetworkInterSitePolicy** pour modifier les propriétés d’un lien de site réseau donné.</span><span class="sxs-lookup"><span data-stu-id="1b433-123">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="1b433-124">Vous pouvez modifier l’un ou l’autre des sites connectés, ou les deux, ainsi que le profil de stratégie de bande passante associé au lien.</span><span class="sxs-lookup"><span data-stu-id="1b433-124">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="1b433-125">Voici un exemple de modification du profil de stratégie de bande passante d’un lien de site nommé Reno \_ Portland :</span><span class="sxs-lookup"><span data-stu-id="1b433-125">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="1b433-126">Pour obtenir des descriptions détaillées des paramètres, voir [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1b433-126">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](/powershell/module/skype/Set-CsNetworkInterSitePolicy).</span></span>


### <a name="to-delete-a-network-site-link"></a><span data-ttu-id="1b433-127">Pour supprimer un lien de site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-127">To delete a network site link</span></span>

1.  <span data-ttu-id="1b433-128">Connectez-vous à l’ordinateur sur lequel Skype Entreprise Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires.</span><span class="sxs-lookup"><span data-stu-id="1b433-128">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights.</span></span>

2.  <span data-ttu-id="1b433-129">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **Server,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="1b433-129">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="1b433-130">Utilisez l’applet de commande **Remove-CsNetworkInterSitePolicy** pour supprimer un lien de site réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-130">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="1b433-131">L’exemple suivant supprime le lien de site réseau Reno \_ Portland :</span><span class="sxs-lookup"><span data-stu-id="1b433-131">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="1b433-132">Pour obtenir des descriptions détaillées des paramètres, voir [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span><span class="sxs-lookup"><span data-stu-id="1b433-132">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](/powershell/module/skype/Remove-CsNetworkInterSitePolicy).</span></span>


## <a name="view-network-site-information"></a><span data-ttu-id="1b433-133">Afficher les informations du site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-133">View network site information</span></span>

<span data-ttu-id="1b433-134">Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1b433-134">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1b433-135">Vous pouvez afficher les informations de site réseau dans le Panneau de contrôle Skype Entreprise Server ou dans Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="1b433-135">You can view network site information in either the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span> 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a><span data-ttu-id="1b433-136">Pour afficher les informations de site réseau dans le Panneau de contrôle Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1b433-136">To view network site information in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="1b433-137">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1b433-137">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b433-138">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b433-138">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1b433-139">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**</span><span class="sxs-lookup"><span data-stu-id="1b433-139">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1b433-140">Dans la page **Site**, cliquez sur le site que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="1b433-140">On the **Site** page, click the site that you want to view.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1b433-141">Vous ne pouvez afficher les informations que d’un site à la fois.</span><span class="sxs-lookup"><span data-stu-id="1b433-141">You can only view information for one site at a time.</span></span>

5.  <span data-ttu-id="1b433-142">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b433-142">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b433-143">Affichage des informations de site réseau à l’aide Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="1b433-143">Viewing network site information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1b433-144">Vous pouvez afficher les informations de site réseau à l’Windows PowerShell et à l'Get-CsNetworkSite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1b433-144">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="1b433-145">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b433-145">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

### <a name="to-view-network-site-information"></a><span data-ttu-id="1b433-146">Pour afficher des informations sur les sites réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-146">To view network site information</span></span>

  - <span data-ttu-id="1b433-147">Pour afficher des informations sur tous vos sites réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="1b433-147">To view information about all your network sites, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="1b433-148">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="1b433-148">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

<span data-ttu-id="1b433-149">Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite).</span><span class="sxs-lookup"><span data-stu-id="1b433-149">For more information, see the help topic for the [Get-CsNetworkSite](/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>


## <a name="create-or-modify-network-sites"></a><span data-ttu-id="1b433-150">Créer ou modifier des sites réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-150">Create or modify network sites</span></span> 

<span data-ttu-id="1b433-151">Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1b433-151">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1b433-152">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="1b433-152">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="1b433-153">Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="1b433-153">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="1b433-154">Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site.</span><span class="sxs-lookup"><span data-stu-id="1b433-154">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="1b433-155">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier et supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-155">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="1b433-156">Utilisez les procédures suivantes pour créer ou modifier un site réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-156">Use the following procedures to create or modify a network site.</span></span> 

### <a name="to-create-a-network-site"></a><span data-ttu-id="1b433-157">Pour créer un site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-157">To create a network site</span></span>

1.  <span data-ttu-id="1b433-158">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1b433-158">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b433-159">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b433-159">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1b433-160">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**</span><span class="sxs-lookup"><span data-stu-id="1b433-160">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1b433-161">Dans la page **Site**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="1b433-161">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="1b433-162">Dans **Nouveau site**, renseignez le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="1b433-162">In **New Site**, type a name for this site in the **Name** field.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1b433-163">Les noms de site doivent être uniques dans le déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b433-163">Site names must be unique within the Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="1b433-164">Dans la liste déroulante **Région**, sélectionnez une région réseau à associer au site.</span><span class="sxs-lookup"><span data-stu-id="1b433-164">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="1b433-165">(Facultatif) Si vous voulez imposer sur ce site des limitations de bande passante aux appels audio ou vidéo, sélectionnez le profil de stratégie de bande passante adéquat dans la liste déroulante **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="1b433-165">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="1b433-166">Vous pouvez afficher les détails des profils de stratégie de bande passante disponibles ou créer un profil de stratégie de bande passante dans la page **Profil** de stratégie du **groupe Configuration** du réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-166">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the **Policy Profil** page of the **Network Configuration** group.</span></span> <span data-ttu-id="1b433-167">Pour plus d’informations, voir [Gestion des profils de stratégie de bande passante réseau.](managing-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1b433-167">For details, see [Managing network bandwidth policy profiles](managing-network-bandwidth-policy-profiles.md).</span></span>

8.  <span data-ttu-id="1b433-168">(Facultatif) Si vous voulez spécifier des paramètres d’emplacement pour ce site, sélectionnez une stratégie d’emplacement dans la liste déroulante **Stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="1b433-168">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1b433-169">La stratégie d’emplacement affecte les paramètres Enhanced 9-1-1 (E9-1-1) et d’emplacement des clients au site.</span><span class="sxs-lookup"><span data-stu-id="1b433-169">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="1b433-170">Vous pouvez afficher les détails des stratégies d’emplacement ou créer une stratégie d’emplacement dans la page **Stratégie d’emplacement** du groupe **Configuration du réseau**.</span><span class="sxs-lookup"><span data-stu-id="1b433-170">You can view the details of the available location policies, or create a new location policy, from the **Location Policy** page of the **Network Configuration** group.</span></span> 

9.  <span data-ttu-id="1b433-171">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce site, car son nom ne suffit pas à le décrire.</span><span class="sxs-lookup"><span data-stu-id="1b433-171">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="1b433-172">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1b433-172">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1b433-173">Lors de la création d’un site réseau, vous n’utilisez pas la table **Sous-réseaux associés**.</span><span class="sxs-lookup"><span data-stu-id="1b433-173">You do not use the **Associated Subnets** table when you create a new network site.</span></span> <span data-ttu-id="1b433-174">Vous associez un sous-réseau à un site lorsque vous créez ou modifiez le sous-réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-174">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="1b433-175">Pour plus d’informations, voir [Gestion des sous-réseaux réseau.](managing-network-subnets.md)</span><span class="sxs-lookup"><span data-stu-id="1b433-175">For details, see [Managing network subnets](managing-network-subnets.md).</span></span>

### <a name="to-modify-a-network-site"></a><span data-ttu-id="1b433-176">Pour modifier un site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-176">To modify a network site</span></span>

1.  <span data-ttu-id="1b433-177">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1b433-177">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b433-178">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b433-178">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1b433-179">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**</span><span class="sxs-lookup"><span data-stu-id="1b433-179">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1b433-180">Dans la page **Site**, cliquez sur le site que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="1b433-180">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="1b433-181">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1b433-181">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="1b433-182">Dans la page **Modifier le site**, vous pouvez modifier la description, la région, le profil de la stratégie de bande passante et la stratégie d’emplacement associés au site.</span><span class="sxs-lookup"><span data-stu-id="1b433-182">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="1b433-183">Pour plus d’informations, voir [Pour créer un site réseau ci-dessus.](#to-create-a-network-site)</span><span class="sxs-lookup"><span data-stu-id="1b433-183">For details, see [To create a network site](#to-create-a-network-site) above.</span></span>

7.  <span data-ttu-id="1b433-184">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1b433-184">Click **Commit**.</span></span>

<span data-ttu-id="1b433-p114">Vous ne pouvez pas modifier la table **Sous-réseaux associés** de cette page. La liste de sous-réseaux associés est donnée à titre de référence de sorte que vous sachiez quels sous-réseaux seront affectés par les paramètres que vous modifiez.</span><span class="sxs-lookup"><span data-stu-id="1b433-p114">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>


## <a name="delete-an-existing-network-site"></a><span data-ttu-id="1b433-187">Supprimer un site réseau existant</span><span class="sxs-lookup"><span data-stu-id="1b433-187">Delete an existing network site</span></span>

<span data-ttu-id="1b433-188">Les sites réseau sont les bureaux ou emplacements configurés au sein de chaque région d’un contrôle d’admission des appels (Call Admission Control ou CAC) ou encore d’un déploiement Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="1b433-188">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="1b433-189">Vous pouvez utiliser le Panneau de configuration de Skype Entreprise Server pour configurer des sites et les associer à des régions.</span><span class="sxs-lookup"><span data-stu-id="1b433-189">You can use the Skype for Business Server Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="1b433-190">Par exemple, vous pouvez associer la région réseau Amérique du Nord à des sites réseau, tels que Chicago, Redmond et Vancouver.</span><span class="sxs-lookup"><span data-stu-id="1b433-190">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="1b433-191">Un site réseau CAC doit être créé pour chaque site dans l’organisation, même en l’absence de limitation de bande passante pour ce site.</span><span class="sxs-lookup"><span data-stu-id="1b433-191">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="1b433-192">À partir du Panneau de contrôle Skype Entreprise Server, vous pouvez créer, modifier et supprimer des sites réseau.</span><span class="sxs-lookup"><span data-stu-id="1b433-192">From the Skype for Business Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="1b433-193">Utilisez la procédure suivante pour supprimer un site réseau existant.</span><span class="sxs-lookup"><span data-stu-id="1b433-193">Use the following procedure to delete an existing network site.</span></span> <span data-ttu-id="1b433-194">Pour plus d’informations sur la création ou la modification de sites réseau, voir Gestion du contrôle [d’admission des appels pour les sites.](managing-call-admission-control-for-sites.md)</span><span class="sxs-lookup"><span data-stu-id="1b433-194">For details about creating or modifying network sites, see [Managing call admission control for sites](managing-call-admission-control-for-sites.md).</span></span>


### <a name="to-delete-a-network-site"></a><span data-ttu-id="1b433-195">Pour supprimer un site réseau</span><span class="sxs-lookup"><span data-stu-id="1b433-195">To delete a network site</span></span>

1.  <span data-ttu-id="1b433-196">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1b433-196">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b433-197">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1b433-197">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1b433-198">Dans la barre de navigation de gauche, cliquez **sur Configuration réseau,** puis sur **Site.**</span><span class="sxs-lookup"><span data-stu-id="1b433-198">In the left navigation bar, click **Network Configuration**, and then click **Site**.</span></span>

4.  <span data-ttu-id="1b433-199">Dans la page **Site**, cliquez sur le site que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="1b433-199">On the **Site** page, click the site that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="1b433-p116">Vous pouvez supprimer plusieurs sites à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs sites. Ou, pour sélectionner tous les sites, cliquez sur **Sélectionner tout** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="1b433-p116">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="1b433-203">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="1b433-203">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="1b433-204">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b433-204">Click **OK**.</span></span>
    

    > [!WARNING]  
    > <span data-ttu-id="1b433-p117">Vous ne pouvez pas supprimer un site réseau associé à un sous-réseau de réseau. Si vous essayez, vous recevrez un message d’erreur. Pour savoir si un site est associé à des sous-réseaux, cliquez sur le site, puis sur **Afficher les détails** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="1b433-p117">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click **Show details** on the **Edit** menu.</span></span>


## <a name="see-also"></a><span data-ttu-id="1b433-208">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b433-208">See Also</span></span>


[<span data-ttu-id="1b433-209">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1b433-209">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[<span data-ttu-id="1b433-210">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1b433-210">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1b433-211">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1b433-211">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1b433-212">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="1b433-212">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[<span data-ttu-id="1b433-213">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="1b433-213">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="1b433-214">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1b433-214">New-CsNetworkSite</span></span>](/powershell/module/skype/New-CsNetworkSite)

[<span data-ttu-id="1b433-215">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1b433-215">Set-CsNetworkSite</span></span>](/powershell/module/skype/Set-CsNetworkSite)

[<span data-ttu-id="1b433-216">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1b433-216">Remove-CsNetworkSite</span></span>](/powershell/module/skype/Remove-CsNetworkSite)  

[<span data-ttu-id="1b433-217">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="1b433-217">Get-CsNetworkSite</span></span>](/powershell/module/skype/Get-CsNetworkSite)