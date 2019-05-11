---
title: Gestion des profils de stratégie de bande passante réseau
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: bc76af70002cc1f5b59b754cd8b86fe0d4c5327f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888841"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="b2662-103">Gestion de profils de stratégie de bande passante réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b2662-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="b2662-104">Utilisez les procédures dans cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="b2662-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="b2662-105">Afficher les informations de profil de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="b2662-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="b2662-106">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="b2662-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="b2662-107">Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="b2662-108">Vous pouvez définir des restrictions de bande passante globale et les limitations de session.</span><span class="sxs-lookup"><span data-stu-id="b2662-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="b2662-109">Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="b2662-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="b2662-110">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites de réseau.</span><span class="sxs-lookup"><span data-stu-id="b2662-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="b2662-111">Utilisez les procédures suivantes pour afficher un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="b2662-112">Pour afficher un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="b2662-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="b2662-113">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b2662-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b2662-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b2662-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b2662-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau** , puis sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="b2662-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b2662-116">Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="b2662-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="b2662-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b2662-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b2662-118">Affichage des informations de profil de stratégie de bande passante réseau à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2662-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b2662-119">Profils de bande passante réseau peuvent être affichés à l’aide de Windows PowerShell et l’applet de commande Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="b2662-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="b2662-120">Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b2662-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="b2662-121">Pour afficher les informations de profil de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="b2662-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="b2662-122">Pour afficher des informations sur tous vos profils de stratégie de bande passante réseau, tapez la commande suivante dans le Skype pour Business Server Management Shell, puis appuyez sur ENTRÉE :</span><span class="sxs-lookup"><span data-stu-id="b2662-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="b2662-123">Vous obtiendrez des indications semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="b2662-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="b2662-124">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="b2662-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="b2662-125">Créer ou modifier des profils de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="b2662-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="b2662-126">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="b2662-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="b2662-127">Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="b2662-128">Vous pouvez définir des restrictions de bande passante globale et les limitations de session.</span><span class="sxs-lookup"><span data-stu-id="b2662-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="b2662-129">Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="b2662-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="b2662-130">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites de réseau.</span><span class="sxs-lookup"><span data-stu-id="b2662-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="b2662-131">Utilisez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="b2662-132">Pour créer un nouveau profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="b2662-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="b2662-133">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b2662-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b2662-134">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b2662-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b2662-135">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="b2662-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b2662-136">Dans la page **Stratégie de bande passante** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b2662-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="b2662-137">Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** .</span><span class="sxs-lookup"><span data-stu-id="b2662-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="b2662-138">Ce nom doit être unique parmi tous les profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="b2662-139">Dans le champ **limite Audio** , tapez une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="b2662-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="b2662-140">Cette valeur est la quantité maximale de bande passante à allouer pour toutes les connexions audio, exprimées en Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="b2662-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="b2662-141">Entrez une valeur numérique dans le champ de **limite de session Audio** .</span><span class="sxs-lookup"><span data-stu-id="b2662-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="b2662-142">Cette valeur est la quantité maximale de bande passante à allouer pour une connexion audio individuelle, exprimée en Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="b2662-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="b2662-143">Cette valeur doit être 40 ou supérieur.</span><span class="sxs-lookup"><span data-stu-id="b2662-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="b2662-144">Entrez une valeur numérique dans le champ **limite vidéo** .</span><span class="sxs-lookup"><span data-stu-id="b2662-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="b2662-145">Cette valeur est la quantité maximale de bande passante à allouer pour toutes les connexions vidéo, exprimées en Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="b2662-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="b2662-146">Entrez une valeur numérique dans le champ de **limite de session vidéo** .</span><span class="sxs-lookup"><span data-stu-id="b2662-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="b2662-147">Cette valeur est la quantité maximale de bande passante à allouer pour une connexion vidéo individuelle, exprimée en Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="b2662-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="b2662-148">Cette valeur doit être au moins 100.</span><span class="sxs-lookup"><span data-stu-id="b2662-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="b2662-149">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante ne suffit pas au nom seul.</span><span class="sxs-lookup"><span data-stu-id="b2662-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="b2662-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b2662-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b2662-151">Création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="b2662-152">Vous devez d’abord associer le profil de stratégie à un site.</span><span class="sxs-lookup"><span data-stu-id="b2662-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="b2662-153">Pour modifier un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="b2662-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="b2662-154">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b2662-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b2662-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b2662-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b2662-156">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="b2662-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b2662-157">Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="b2662-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="b2662-158">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="b2662-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="b2662-159">Dans la page **Modifier un profil de stratégie de bande passante** , modifiez les champs comme il convient (pour plus d’informations, voir [créer un nouveau profil de stratégie de bande passante](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="b2662-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="b2662-160">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b2662-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b2662-161">Lorsque vous modifiez le profil de stratégie de bande passante, il met immédiatement à jour les limitations de bande passante de tous les sites de réseau associés à ce profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="b2662-162">Supprimer des profils de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="b2662-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="b2662-163">Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="b2662-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="b2662-164">Dans Skype pour Business Server, modalités uniquement audio et vidéos peuvent être attribuées à des limitations de bande passante.</span><span class="sxs-lookup"><span data-stu-id="b2662-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="b2662-165">Vous pouvez définir des restrictions de bande passante globale et les limitations de session.</span><span class="sxs-lookup"><span data-stu-id="b2662-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="b2662-166">Vous pouvez utiliser la Skype pour Business Server Control Panel pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="b2662-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="b2662-167">Utilisez les procédures suivantes pour supprimer un profil de stratégie de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="b2662-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="b2662-168">Pour supprimer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="b2662-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="b2662-169">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b2662-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b2662-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="b2662-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b2662-171">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis cliquez sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="b2662-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="b2662-172">Dans la page **Stratégie de bande passante** , cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="b2662-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="b2662-173">Vous pouvez supprimer plusieurs profils à la fois.</span><span class="sxs-lookup"><span data-stu-id="b2662-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="b2662-174">Pour ce faire, appuyez sur la touche CTRL ENFONCÉE et sélectionnez plusieurs profils tout en maintenant la touche CTRL enfoncée.</span><span class="sxs-lookup"><span data-stu-id="b2662-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="b2662-175">Ou, pour sélectionner tous les profils, cliquez sur **Sélectionner tout** dans le menu **Edition** .</span><span class="sxs-lookup"><span data-stu-id="b2662-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="b2662-176">Dans le menu **Edition** , cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b2662-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="b2662-177">Vous ne pouvez pas supprimer un profil de stratégie de bande passante qui est associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="b2662-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="b2662-178">Vous devez d’abord supprimer l’association avec le site réseau avant de pouvoir supprimer le profil.</span><span class="sxs-lookup"><span data-stu-id="b2662-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b2662-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2662-179">See Also</span></span>

[<span data-ttu-id="b2662-180">Gérer le contrôle d’admission des appels pour les sites d’appel</span><span class="sxs-lookup"><span data-stu-id="b2662-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="b2662-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b2662-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="b2662-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b2662-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="b2662-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b2662-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="b2662-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b2662-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

