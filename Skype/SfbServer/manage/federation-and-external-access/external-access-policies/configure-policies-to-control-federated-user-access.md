---
title: Configuration des stratégies de contrôler d’accès des utilisateurs fédérés
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés. '
ms.openlocfilehash: df5702fb217d238a26a8a9975e7e4a0792787399
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199897"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="00ec1-103">Configurer des stratégies de contrôle d’accès des utilisateurs fédérés dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="00ec1-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="00ec1-104">Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="00ec1-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="00ec1-105">Vous pouvez configurer un ou plusieurs stratégies d’accès utilisateur externe au contrôle si les utilisateurs des domaines fédérés peuvent collaborer avec vos Skype pour les utilisateurs Business Server.</span><span class="sxs-lookup"><span data-stu-id="00ec1-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="00ec1-106">Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, site et au niveau utilisateur.</span><span class="sxs-lookup"><span data-stu-id="00ec1-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="00ec1-107">Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre.</span><span class="sxs-lookup"><span data-stu-id="00ec1-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="00ec1-108">Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins).</span><span class="sxs-lookup"><span data-stu-id="00ec1-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="00ec1-109">Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="00ec1-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="00ec1-110">Vous pouvez configurer des stratégies de contrôle d’accès des utilisateurs fédérés, même si vous n’avez pas activé la fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="00ec1-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="00ec1-111">Toutefois, les stratégies que vous configurez sont en effet que lorsque vous avez activée pour votre organisation de fédération.</span><span class="sxs-lookup"><span data-stu-id="00ec1-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="00ec1-112">Pour plus d’informations sur l’activation de la fédération, voir [Activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="00ec1-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="00ec1-113">En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype pour Business Server et configurés pour utiliser la stratégie.</span><span class="sxs-lookup"><span data-stu-id="00ec1-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="00ec1-114">Pour configurer une stratégie pour prendre en charge l’accès par les utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="00ec1-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="00ec1-115">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="00ec1-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00ec1-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="00ec1-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="00ec1-117">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="00ec1-118">Dans la page **Stratégie d’accès externe** , effectuez l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="00ec1-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="00ec1-119">Pour configurer la stratégie globale pour prendre en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="00ec1-120">Pour créer une stratégie de site, cliquez sur **Nouveau**, puis cliquez sur **stratégie de Site**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="00ec1-121">Dans **Sélectionner un Site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="00ec1-122">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="00ec1-123">Dans la **Nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique quel utilisateur concernés par cette stratégie (par exemple, **EnableFederatedUsers** pour une stratégie d’utilisateur qui permet de communications pour les utilisateurs du domaine fédéré).</span><span class="sxs-lookup"><span data-stu-id="00ec1-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="00ec1-124">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="00ec1-125">(Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations de la stratégie dans la zone **Description**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="00ec1-126">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="00ec1-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="00ec1-127">Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **Activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="00ec1-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="00ec1-128">Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **Activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="00ec1-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="00ec1-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-129">Click **Commit**.</span></span>

<span data-ttu-id="00ec1-130">Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge pour la fédération dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="00ec1-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="00ec1-131">Pour plus d’informations, voir [Activer ou désactiver la fédération et la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="00ec1-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="00ec1-132">S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez être en mesure de collaborer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="00ec1-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="00ec1-133">Pour plus d’informations, voir [attribuer une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="00ec1-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="00ec1-134">Pour configurer une stratégie existante à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="00ec1-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="00ec1-135">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="00ec1-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00ec1-136">Démarrez le Skype pour Busines Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="00ec1-137">Tapez ce qui suit dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="00ec1-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="00ec1-138">Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="00ec1-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="00ec1-139">Pour créer une nouvelle stratégie à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="00ec1-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="00ec1-140">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="00ec1-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00ec1-141">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Microsoft Skype pour Business Server**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="00ec1-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="00ec1-142">Tapez ce qui suit dans le Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="00ec1-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="00ec1-143">Exemple de création d’une stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="00ec1-143">An example of creating a new site policy:</span></span>
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="00ec1-144">Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="00ec1-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="00ec1-145">À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="00ec1-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="00ec1-146">Tapez ce qui suit dans le Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="00ec1-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="00ec1-147">Un exemple de la réinitialisation de la stratégie globale (la stratégie globale ne peut avoir le paramètre supprimé.</span><span class="sxs-lookup"><span data-stu-id="00ec1-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="00ec1-148">La stratégie ne peut pas être supprimée) :</span><span class="sxs-lookup"><span data-stu-id="00ec1-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="00ec1-149">Pour supprimer une stratégie de site, tapez :</span><span class="sxs-lookup"><span data-stu-id="00ec1-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="00ec1-150">Supprime la stratégie de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="00ec1-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="00ec1-151">Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :</span><span class="sxs-lookup"><span data-stu-id="00ec1-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="00ec1-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00ec1-152">See Also</span></span>


[<span data-ttu-id="00ec1-153">Activation ou désactivation de la fédération et de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="00ec1-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="00ec1-154">Attribution d’une stratégie d’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="00ec1-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="00ec1-155">Gestion des domaines fédérés SIP pour l’organisation</span><span class="sxs-lookup"><span data-stu-id="00ec1-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="00ec1-156">Gestion des fournisseurs fédérés SIP pour l’organisation</span><span class="sxs-lookup"><span data-stu-id="00ec1-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="00ec1-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="00ec1-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="00ec1-158">Nouvelle-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="00ec1-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="00ec1-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="00ec1-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="00ec1-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="00ec1-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="00ec1-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="00ec1-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

