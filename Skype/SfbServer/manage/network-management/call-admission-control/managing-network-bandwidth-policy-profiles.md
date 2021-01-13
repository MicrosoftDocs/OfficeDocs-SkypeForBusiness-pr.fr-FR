---
title: Gestion des profils de stratégie de bande passante réseau
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
description: Utilisez les procédures de cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816444"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="33c24-103">Gestion de profils de stratégie de bande passante réseau dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="33c24-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="33c24-104">Utilisez les procédures de cet article pour afficher, créer, modifier ou supprimer des profils de stratégie de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="33c24-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="33c24-105">Afficher les informations de profil de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="33c24-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="33c24-106">La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="33c24-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="33c24-107">Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="33c24-108">Vous pouvez définir des restrictions de bande passante et de session globales.</span><span class="sxs-lookup"><span data-stu-id="33c24-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="33c24-109">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="33c24-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="33c24-110">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="33c24-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="33c24-111">Utilisez les procédures suivantes pour afficher un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="33c24-112">Pour afficher un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="33c24-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="33c24-113">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33c24-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33c24-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33c24-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33c24-115">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.</span><span class="sxs-lookup"><span data-stu-id="33c24-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="33c24-116">Dans la page **Stratégie de bande** passante, cliquez sur le profil de stratégie de bande passante à afficher.</span><span class="sxs-lookup"><span data-stu-id="33c24-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="33c24-117">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="33c24-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="33c24-118">Affichage des informations de profil de stratégie de bande passante réseau à l’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="33c24-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="33c24-119">Les profils de bande passante réseau peuvent être Windows PowerShell l'Get-CsNetworkBandwidthPolicyProfile cmdlet.</span><span class="sxs-lookup"><span data-stu-id="33c24-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="33c24-120">Cette cmdlet peut être exécuté à partir de Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33c24-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="33c24-121">Pour afficher les informations de profil de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="33c24-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="33c24-122">Pour afficher des informations sur tous vos profils de stratégie de bande passante réseau, tapez la commande suivante dans Skype Entreprise Server Management Shell, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="33c24-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="33c24-123">Cette action a pour effet de renvoyer des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="33c24-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="33c24-124">Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Get-CsNetworkBandwidthPolicyProfile.](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)</span><span class="sxs-lookup"><span data-stu-id="33c24-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="33c24-125">Créer ou modifier des profils de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="33c24-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="33c24-126">La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="33c24-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="33c24-127">Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="33c24-128">Vous pouvez définir des restrictions de bande passante et de session globales.</span><span class="sxs-lookup"><span data-stu-id="33c24-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="33c24-129">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="33c24-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="33c24-130">Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau.</span><span class="sxs-lookup"><span data-stu-id="33c24-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="33c24-131">Effectuez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="33c24-132">Pour créer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="33c24-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="33c24-133">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33c24-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33c24-134">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33c24-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33c24-135">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**</span><span class="sxs-lookup"><span data-stu-id="33c24-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="33c24-136">Dans la page **Stratégie de bande passante**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="33c24-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="33c24-p104">Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **Nom**. Ce nom doit être unique parmi tous les profils de stratégie de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-p104">In **New Bandwidth Policy Profile**, type a name in the **Name** field. This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="33c24-p105">Dans le champ **Limite audio**, tapez une valeur numérique. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions audio.</span><span class="sxs-lookup"><span data-stu-id="33c24-p105">In the **Audio limit** field, type a numeric value. This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="33c24-p106">Entrez une valeur numérique dans le champ **Limite de session audio**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion audio. Cette valeur doit être égale ou supérieure à 40.</span><span class="sxs-lookup"><span data-stu-id="33c24-p106">Enter a numeric value in the **Audio session limit** field. This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps. This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="33c24-p107">Entrez une valeur numérique dans le champ **Limite vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions vidéo.</span><span class="sxs-lookup"><span data-stu-id="33c24-p107">Enter a numeric value in the **Video limit** field. This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="33c24-p108">Entrez une valeur numérique dans le champ **Limite de session vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion vidéo. Cette valeur doit être égale ou supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="33c24-p108">Enter a numeric value in the **Video session limit** field. This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps. This value must be 100 or higher.</span></span>

10. <span data-ttu-id="33c24-149">(Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante, car son nom ne suffit pas à le décrire.</span><span class="sxs-lookup"><span data-stu-id="33c24-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="33c24-150">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="33c24-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33c24-151">La création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="33c24-152">Vous devez d’abord associer le profil de stratégie à un site.</span><span class="sxs-lookup"><span data-stu-id="33c24-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="33c24-153">Pour modifier un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="33c24-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="33c24-154">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33c24-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33c24-155">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33c24-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33c24-156">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**</span><span class="sxs-lookup"><span data-stu-id="33c24-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="33c24-157">Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="33c24-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="33c24-158">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="33c24-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="33c24-159">Dans la page **Modifier le profil de stratégie de** bande passante, modifiez les champs si nécessaire (pour plus d’informations, voir Pour créer un profil de stratégie de bande [passante).](#to-create-a-new-bandwidth-policy-profile)</span><span class="sxs-lookup"><span data-stu-id="33c24-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="33c24-160">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="33c24-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33c24-161">Lorsque vous modifiez le profil de stratégie de bande passante, celui-ci met immédiatement à jour les restrictions de bande passante de tous les sites réseau qui lui sont associés.</span><span class="sxs-lookup"><span data-stu-id="33c24-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="33c24-162">Supprimer les profils de stratégie de bande passante réseau</span><span class="sxs-lookup"><span data-stu-id="33c24-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="33c24-163">La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis.</span><span class="sxs-lookup"><span data-stu-id="33c24-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="33c24-164">Dans Skype Entreprise Server, seules les modalités audio et vidéo peuvent être affectées à des restrictions de bande passante.</span><span class="sxs-lookup"><span data-stu-id="33c24-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="33c24-165">Vous pouvez définir des restrictions de bande passante et de session globales.</span><span class="sxs-lookup"><span data-stu-id="33c24-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="33c24-166">Vous pouvez utiliser le Panneau de contrôle Skype Entreprise Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies.</span><span class="sxs-lookup"><span data-stu-id="33c24-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="33c24-167">Utilisez les procédures suivantes pour supprimer des profils de stratégies de bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="33c24-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="33c24-168">Pour supprimer un profil de stratégie de bande passante</span><span class="sxs-lookup"><span data-stu-id="33c24-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="33c24-169">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="33c24-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="33c24-170">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="33c24-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="33c24-171">Dans la barre de navigation de gauche, cliquez sur **Configuration réseau,** puis sur Stratégie de bande **passante.**</span><span class="sxs-lookup"><span data-stu-id="33c24-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="33c24-172">Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez supprimer.</span><span class="sxs-lookup"><span data-stu-id="33c24-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="33c24-p111">Vous pouvez supprimer plusieurs profils à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs profils. Pour sélectionner tous les profils, cliquez sur **Sélectionner tout** dans le menu **Edition**.</span><span class="sxs-lookup"><span data-stu-id="33c24-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="33c24-176">Dans le menu **Edition**, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="33c24-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="33c24-177">Vous ne pouvez pas supprimer un profil de stratégie de bande passante associé à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="33c24-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="33c24-178">Vous devez d’abord supprimer l’association au site réseau avant de supprimer le profil.</span><span class="sxs-lookup"><span data-stu-id="33c24-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="33c24-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33c24-179">See Also</span></span>

[<span data-ttu-id="33c24-180">Gestion du contrôle d’admission des appels pour les sites</span><span class="sxs-lookup"><span data-stu-id="33c24-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="33c24-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="33c24-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="33c24-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="33c24-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="33c24-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="33c24-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="33c24-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="33c24-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

