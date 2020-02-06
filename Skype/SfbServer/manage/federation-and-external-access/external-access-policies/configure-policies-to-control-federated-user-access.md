---
title: Configuration des stratégies de contrôler d’accès des utilisateurs fédérés
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés. '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818315"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="a6c7b-103">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a6c7b-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="a6c7b-104">Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="a6c7b-105">Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="a6c7b-106">Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies aux niveaux global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="a6c7b-107">Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="a6c7b-108">Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant : la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence).</span><span class="sxs-lookup"><span data-stu-id="a6c7b-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="a6c7b-109">Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="a6c7b-110">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="a6c7b-111">Toutefois, les stratégies que vous configurez ne s’appliquent que lorsque la Fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="a6c7b-112">Pour plus d’informations sur l’activation de la Fédération, voir [activation ou désactivation de l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a6c7b-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="a6c7b-113">Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype entreprise Server et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a6c7b-114">Pour configurer une stratégie afin de prendre en charge l’accès par des utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="a6c7b-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a6c7b-115">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6c7b-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="a6c7b-117">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="a6c7b-118">Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a6c7b-119">Pour configurer la stratégie globale de manière à prendre en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="a6c7b-120">Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-120">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="a6c7b-121">Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-121">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="a6c7b-122">Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="a6c7b-123">Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie de l’utilisateur qui autorise les communications pour les utilisateurs fédérés du domaine).</span><span class="sxs-lookup"><span data-stu-id="a6c7b-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="a6c7b-124">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a6c7b-125">Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="a6c7b-126">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="a6c7b-127">Pour autoriser l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="a6c7b-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="a6c7b-128">Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, décochez la case **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="a6c7b-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="a6c7b-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-129">Click **Commit**.</span></span>

<span data-ttu-id="a6c7b-130">Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la Fédération au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="a6c7b-131">Pour plus d’informations, voir [activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="a6c7b-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="a6c7b-132">S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="a6c7b-133">Pour plus d’informations, voir [affecter une stratégie d’accès utilisateur externe](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="a6c7b-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a6c7b-134">Pour configurer une stratégie existante à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="a6c7b-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a6c7b-135">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6c7b-136">Démarrez Skype pour entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="a6c7b-137">Dans Skype entreprise Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="a6c7b-138">Le paramètre « EnablePublicCloudAudioVideoAccess » ne possède pas de sélection correspondante dans le panneau de configuration Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a6c7b-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a6c7b-139">Pour créer une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="a6c7b-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a6c7b-140">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6c7b-141">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="a6c7b-142">Dans Skype entreprise Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="a6c7b-143">Exemple de création d’une nouvelle stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="a6c7b-144">Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="a6c7b-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="a6c7b-145">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6c7b-146">Tapez les informations suivantes dans Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a6c7b-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="a6c7b-147">Voici un exemple de réinitialisation de la stratégie globale (la stratégie globale peut uniquement avoir supprimé son paramètre.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="a6c7b-148">La stratégie ne peut pas être supprimée) :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="a6c7b-149">Pour supprimer une stratégie de site, tapez :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="a6c7b-150">Supprime la stratégie de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="a6c7b-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="a6c7b-151">Pour supprimer une stratégie d’utilisateur nommée UserEAPPolicy, tapez :</span><span class="sxs-lookup"><span data-stu-id="a6c7b-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="a6c7b-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6c7b-152">See Also</span></span>


[<span data-ttu-id="a6c7b-153">Activation ou désactivation de la fédération et de la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="a6c7b-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="a6c7b-154">Attribution d’une stratégie d’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="a6c7b-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="a6c7b-155">Gestion des domaines fédérés SIP pour l’organisation</span><span class="sxs-lookup"><span data-stu-id="a6c7b-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="a6c7b-156">Gestion des fournisseurs fédérés SIP pour l’organisation</span><span class="sxs-lookup"><span data-stu-id="a6c7b-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="a6c7b-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a6c7b-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="a6c7b-158">Nouveau-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a6c7b-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="a6c7b-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a6c7b-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="a6c7b-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a6c7b-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="a6c7b-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="a6c7b-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

