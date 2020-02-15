---
title: Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés
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
description: 'Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037404"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a><span data-ttu-id="54b1f-103">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="54b1f-103">Configure policies to control federated user access in Skype for Business Server</span></span>

<span data-ttu-id="54b1f-104">Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="54b1f-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="54b1f-105">Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="54b1f-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Skype for Business Server users.</span></span> <span data-ttu-id="54b1f-106">Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="54b1f-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="54b1f-107">Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="54b1f-107">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="54b1f-108">La priorité de la stratégie de Skype entreprise Server est la suivante : la stratégie utilisateur (la plus grande influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (la moins influencée).</span><span class="sxs-lookup"><span data-stu-id="54b1f-108">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="54b1f-109">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="54b1f-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>


> [!NOTE]  
> <span data-ttu-id="54b1f-110">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="54b1f-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="54b1f-111">Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="54b1f-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="54b1f-112">Pour plus d’informations sur l’activation de la Fédération, consultez la rubrique [activer ou désactiver l’accès des utilisateurs distants](../access-edge/enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="54b1f-112">For details about enabling federation, see [Enable or disable remote user access](../access-edge/enable-or-disable-remote-user-access.md).</span></span>  <span data-ttu-id="54b1f-113">De plus, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Skype entreprise Server et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="54b1f-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Skype for Business Server and configured to use the policy.</span></span>


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="54b1f-114">Pour configurer une stratégie afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="54b1f-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="54b1f-115">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="54b1f-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54b1f-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="54b1f-116">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="54b1f-117">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-117">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="54b1f-118">Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="54b1f-118">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="54b1f-119">Pour configurer la stratégie globale afin qu’elle prenne en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-119">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="54b1f-p103">Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-p103">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="54b1f-122">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-122">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="54b1f-123">Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui active les communications pour les utilisateurs de domaine fédéré).</span><span class="sxs-lookup"><span data-stu-id="54b1f-123">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="54b1f-124">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-124">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="54b1f-125">(Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-125">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="54b1f-126">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="54b1f-126">Do one of the following:</span></span>
    
      - <span data-ttu-id="54b1f-127">Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="54b1f-127">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="54b1f-128">Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="54b1f-128">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="54b1f-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-129">Click **Commit**.</span></span>

<span data-ttu-id="54b1f-130">Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la Fédération dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="54b1f-130">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="54b1f-131">Pour plus d’informations, consultez la rubrique [activation ou désactivation de la Fédération et de la connectivité PIC](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="54b1f-131">For details, see [Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="54b1f-132">S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous voulez être en mesure de collaborer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="54b1f-132">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="54b1f-133">Pour plus d’informations, consultez la rubrique [assigner une stratégie d’accès des utilisateurs externes](assign-an-external-user-access-policy.md).</span><span class="sxs-lookup"><span data-stu-id="54b1f-133">For details, see [Assign an external user access policy](assign-an-external-user-access-policy.md).</span></span>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="54b1f-134">Pour configurer une stratégie existante à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="54b1f-134">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="54b1f-135">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="54b1f-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54b1f-136">Démarrez Skype outil Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-136">Start the Skype for Busines Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="54b1f-137">Tapez ce qui suit dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="54b1f-137">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > <span data-ttu-id="54b1f-138">Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le panneau de configuration de Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="54b1f-138">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Skype for Business Server Control Panel</span></span>


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="54b1f-139">Pour créer une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="54b1f-139">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="54b1f-140">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="54b1f-140">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54b1f-141">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Skype entreprise Server**, puis sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="54b1f-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server**, and then click **Skype for Business Server Management Shell**.</span></span>

3.  <span data-ttu-id="54b1f-142">Tapez ce qui suit dans Skype entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="54b1f-142">Type the following in the Skype for Business Server Management Shell:</span></span>
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    <span data-ttu-id="54b1f-143">Exemple de création d’une nouvelle stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="54b1f-143">An example of creating a new site policy:</span></span>
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="54b1f-144">Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="54b1f-144">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="54b1f-145">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="54b1f-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="54b1f-146">Tapez ce qui suit dans Skype entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="54b1f-146">Type the following in the Skype for Business Server Management Shell</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    <span data-ttu-id="54b1f-147">Exemple de réinitialisation de la stratégie globale (la stratégie globale peut uniquement avoir son paramètre supprimé.</span><span class="sxs-lookup"><span data-stu-id="54b1f-147">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="54b1f-148">La stratégie ne peut pas être supprimée) :</span><span class="sxs-lookup"><span data-stu-id="54b1f-148">The policy cannot be deleted):</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    <span data-ttu-id="54b1f-149">Pour supprimer une stratégie de site, tapez :</span><span class="sxs-lookup"><span data-stu-id="54b1f-149">To remove a site policy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    <span data-ttu-id="54b1f-150">Supprime la stratégie de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="54b1f-150">Deletes the site policy Redmond.</span></span> <span data-ttu-id="54b1f-151">Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :</span><span class="sxs-lookup"><span data-stu-id="54b1f-151">To delete a user policy named UserEAPPolicy, type:</span></span>
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a><span data-ttu-id="54b1f-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="54b1f-152">See Also</span></span>


[<span data-ttu-id="54b1f-153">Activer ou désactiver la Fédération et la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="54b1f-153">Enable or disable federation and public IM connectivity</span></span>](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[<span data-ttu-id="54b1f-154">Affecter une stratégie d’accès des utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="54b1f-154">Assign an external user access policy</span></span>](assign-an-external-user-access-policy.md)

[<span data-ttu-id="54b1f-155">Gérer les domaines fédérés SIP pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="54b1f-155">Manage SIP federated domains for your organization</span></span>](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[<span data-ttu-id="54b1f-156">Gestion des fournisseurs fédérés SIP pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="54b1f-156">Manage SIP federated providers for your organization</span></span>](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[<span data-ttu-id="54b1f-157">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="54b1f-157">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="54b1f-158">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="54b1f-158">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="54b1f-159">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="54b1f-159">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="54b1f-160">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="54b1f-160">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="54b1f-161">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="54b1f-161">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

