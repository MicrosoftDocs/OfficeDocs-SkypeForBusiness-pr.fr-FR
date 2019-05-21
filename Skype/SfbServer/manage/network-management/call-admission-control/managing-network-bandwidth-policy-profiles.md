---
title: Gestion des profils de stratégie de bande passante réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Les procédures décrites dans cet article vous permettent d’afficher, de créer, de modifier ou de supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279521"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="02938-103">Gestion de profils de stratégie de bande passante réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="02938-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="02938-104">Les procédures décrites dans cet article vous permettent d’afficher, de créer, de modifier ou de supprimer des profils de stratégie de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="02938-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="02938-105">Afficher les informations de profil de la stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="02938-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="02938-106">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités.</span><span class="sxs-lookup"><span data-stu-id="02938-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="02938-107">Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="02938-108">Vous pouvez définir les limites générales de bande passante et les limites de session.</span><span class="sxs-lookup"><span data-stu-id="02938-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="02938-109">Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="02938-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="02938-110">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="02938-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="02938-111">Pour afficher le profil d’une stratégie de bande passante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="02938-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="02938-112">Pour afficher un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="02938-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="02938-113">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="02938-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02938-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02938-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="02938-115">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="02938-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="02938-116">Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="02938-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="02938-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="02938-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="02938-118">Affichage des informations de profil de la stratégie de bande passante du réseau à l’aide des cmdlets Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="02938-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="02938-119">Les profils de bande passante réseau peuvent être affichés à l’aide de Windows PowerShell et de l’applet de connexion Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="02938-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="02938-120">Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="02938-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="02938-121">Pour afficher les informations de profil de la stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="02938-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="02938-122">Pour afficher des informations sur tous les profils de votre stratégie de bande passante réseau, tapez la commande suivante dans Skype entreprise Server Management Shell, puis appuyez sur entrée:</span><span class="sxs-lookup"><span data-stu-id="02938-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="02938-123">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="02938-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="02938-124">Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="02938-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="02938-125">Créer ou modifier des profils de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="02938-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="02938-126">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités.</span><span class="sxs-lookup"><span data-stu-id="02938-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="02938-127">Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="02938-128">Vous pouvez définir les limites générales de bande passante et les limites de session.</span><span class="sxs-lookup"><span data-stu-id="02938-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="02938-129">Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="02938-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="02938-130">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="02938-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="02938-131">Pour créer ou modifier un profil de stratégie de bande passante, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="02938-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="02938-132">Pour créer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="02938-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="02938-133">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="02938-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02938-134">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02938-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="02938-135">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="02938-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="02938-136">Dans la page **stratégie de bande passante** , cliquez sur **nouveau**.</span><span class="sxs-lookup"><span data-stu-id="02938-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="02938-137">Dans **nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="02938-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="02938-138">Ce nom doit être unique parmi tous les profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="02938-139">Dans le champ **limite audio** , entrez une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="02938-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="02938-140">Cette valeur correspond au nombre maximal de bande passante à allouer pour toutes les connexions audio, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="02938-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="02938-141">Entrez une valeur numérique dans le champ **limite de session audio** .</span><span class="sxs-lookup"><span data-stu-id="02938-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="02938-142">Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion audio individuelle, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="02938-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="02938-143">Cette valeur doit être 40 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="02938-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="02938-144">Entrez une valeur numérique dans le champ **limite vidéo** .</span><span class="sxs-lookup"><span data-stu-id="02938-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="02938-145">Cette valeur correspond au volume maximal de bande passante à allouer pour toutes les connexions vidéo, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="02938-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="02938-146">Entrez une valeur numérique dans le champ **limite de session vidéo** .</span><span class="sxs-lookup"><span data-stu-id="02938-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="02938-147">Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion vidéo individuelle, exprimée en kbps.</span><span class="sxs-lookup"><span data-stu-id="02938-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="02938-148">Cette valeur doit être 100 ou une version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="02938-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="02938-149">Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur le profil de la stratégie de bande passante qui ne peut pas être exprimé uniquement par le nom.</span><span class="sxs-lookup"><span data-stu-id="02938-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="02938-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="02938-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="02938-151">La création d’un profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="02938-152">Vous devez d’abord associer le profil de la stratégie à un site.</span><span class="sxs-lookup"><span data-stu-id="02938-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="02938-153">Pour modifier le profil d’une stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="02938-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="02938-154">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="02938-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02938-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02938-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="02938-156">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="02938-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="02938-157">Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez modifier.</span><span class="sxs-lookup"><span data-stu-id="02938-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="02938-158">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="02938-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="02938-159">Dans la page **modifier le profil de la stratégie de bande passante** , modifiez les champs si nécessaire (pour plus de détails, voir [créer un profil de stratégie de bande passante](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="02938-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="02938-160">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="02938-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="02938-161">Lorsque vous modifiez le profil de la stratégie de bande passante, il met à jour immédiatement les limites de bande passante pour tous les sites réseau associés à ce profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="02938-162">Supprimer les profils de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="02938-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="02938-163">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités.</span><span class="sxs-lookup"><span data-stu-id="02938-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="02938-164">Dans Skype entreprise Server, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="02938-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="02938-165">Vous pouvez définir les limites générales de bande passante et les limites de session.</span><span class="sxs-lookup"><span data-stu-id="02938-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="02938-166">Le panneau de configuration Skype entreprise Server vous permet de créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="02938-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="02938-167">Utilisez les procédures suivantes pour supprimer un profil de stratégie de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="02938-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="02938-168">Pour supprimer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="02938-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="02938-169">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="02938-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="02938-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="02938-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="02938-171">Dans la barre de navigation de gauche, cliquez sur **configuration du réseau**, puis sur **stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="02938-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="02938-172">Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez supprimer.</span><span class="sxs-lookup"><span data-stu-id="02938-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="02938-173">Vous pouvez supprimer plusieurs profils à la fois.</span><span class="sxs-lookup"><span data-stu-id="02938-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="02938-174">Pour cela, appuyez sur CTRL et sélectionnez plusieurs profils tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="02938-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="02938-175">Pour sélectionner tous les profils, dans le menu **Edition** , cliquez sur **Sélectionner tout** .</span><span class="sxs-lookup"><span data-stu-id="02938-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="02938-176">Dans le menu **modifier** , cliquez sur **supprimer**.</span><span class="sxs-lookup"><span data-stu-id="02938-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="02938-177">Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="02938-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="02938-178">Vous devez d’abord supprimer l’Association au site du réseau avant de pouvoir supprimer le profil.</span><span class="sxs-lookup"><span data-stu-id="02938-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="02938-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="02938-179">See Also</span></span>

[<span data-ttu-id="02938-180">Gestion du contrôle d’admission des appels pour les sites</span><span class="sxs-lookup"><span data-stu-id="02938-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="02938-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="02938-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="02938-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="02938-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="02938-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="02938-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="02938-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="02938-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

