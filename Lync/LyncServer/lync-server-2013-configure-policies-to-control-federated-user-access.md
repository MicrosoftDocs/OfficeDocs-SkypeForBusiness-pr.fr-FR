---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs fédérés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fb009561c36395ee31a49986f2db0103cbe096b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="e74b9-102">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74b9-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74b9-103">_**Dernière modification de la rubrique:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="e74b9-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e74b9-104">Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="e74b9-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="e74b9-105">Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e74b9-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="e74b9-106">Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies aux niveaux global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e74b9-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="e74b9-107">Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="e74b9-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="e74b9-108">Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence).</span><span class="sxs-lookup"><span data-stu-id="e74b9-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="e74b9-109">Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="e74b9-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e74b9-110">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e74b9-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="e74b9-111">Toutefois, les stratégies que vous configurez ne s’appliquent que lorsque la Fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e74b9-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="e74b9-112">Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="e74b9-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="e74b9-113">Par ailleurs, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="e74b9-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="e74b9-114">Pour configurer une stratégie afin de prendre en charge l’accès par des utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="e74b9-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="e74b9-115">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e74b9-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e74b9-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e74b9-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e74b9-117">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e74b9-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e74b9-118">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="e74b9-119">Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="e74b9-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e74b9-120">Pour configurer la stratégie globale de manière à prendre en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="e74b9-121">Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-121">To create a new site policy, click **New**, and then click **Site policy**.</span></span> <span data-ttu-id="e74b9-122">Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-122">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="e74b9-123">Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="e74b9-124">Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie de l’utilisateur qui autorise les communications pour les utilisateurs fédérés du domaine).</span><span class="sxs-lookup"><span data-stu-id="e74b9-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="e74b9-125">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e74b9-126">Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="e74b9-127">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="e74b9-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="e74b9-128">Pour autoriser l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="e74b9-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="e74b9-129">Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, décochez la case **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="e74b9-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="e74b9-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-130">Click **Commit**.</span></span>

<span data-ttu-id="e74b9-131">Pour autoriser l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la Fédération au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e74b9-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="e74b9-132">Pour plus d’informations, reportez-vous à [activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="e74b9-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="e74b9-133">S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous souhaitez pouvoir collaborer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="e74b9-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="e74b9-134">Pour plus d’informations, voir [affecter une stratégie d’accès d’utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="e74b9-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="e74b9-135">Pour configurer une stratégie existante à l’aide de Windows PowerShell pour prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="e74b9-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="e74b9-136">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e74b9-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e74b9-137">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e74b9-138">Dans Lync Server Management Shell, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="e74b9-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="e74b9-139">Un exemple de commande qui définit la stratégie globale pour l’accès utilisateur fédéré à activé, l’accès au domaine de XMPP à activé, l’accès des utilisateurs distants à activé, l’accès du fournisseur public à activé, et autorise l’utilisation de l’audio et de la vidéo pour les fournisseurs publics qui le prennent en charge:</span><span class="sxs-lookup"><span data-stu-id="e74b9-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e74b9-140">Le paramètre «EnablePublicCloudAudioVideoAccess» ne possède pas de sélection correspondante dans le panneau de configuration de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e74b9-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="e74b9-141">Pour créer une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="e74b9-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="e74b9-142">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e74b9-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e74b9-143">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e74b9-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e74b9-144">Dans Lync Server Management Shell, tapez ce qui suit:</span><span class="sxs-lookup"><span data-stu-id="e74b9-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="e74b9-145">Exemple de création d’une nouvelle stratégie de site:</span><span class="sxs-lookup"><span data-stu-id="e74b9-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="e74b9-146">Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès par les utilisateurs de domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="e74b9-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="e74b9-147">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="e74b9-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e74b9-148">Tapez les informations suivantes dans Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="e74b9-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="e74b9-149">Voici un exemple de réinitialisation de la stratégie globale (la stratégie globale peut uniquement avoir supprimé son paramètre.</span><span class="sxs-lookup"><span data-stu-id="e74b9-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="e74b9-150">La stratégie ne peut pas être supprimée):</span><span class="sxs-lookup"><span data-stu-id="e74b9-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="e74b9-151">Pour supprimer une stratégie de site, tapez:</span><span class="sxs-lookup"><span data-stu-id="e74b9-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="e74b9-152">Supprime la stratégie de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="e74b9-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="e74b9-153">Pour supprimer une stratégie d’utilisateur nommée UserEAPPolicy, tapez:</span><span class="sxs-lookup"><span data-stu-id="e74b9-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e74b9-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e74b9-154">See Also</span></span>


[<span data-ttu-id="e74b9-155">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74b9-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="e74b9-156">Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74b9-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="e74b9-157">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74b9-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="e74b9-158">Gestion des fournisseurs fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74b9-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="e74b9-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e74b9-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="e74b9-160">Nouveau-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e74b9-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="e74b9-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e74b9-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="e74b9-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e74b9-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="e74b9-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="e74b9-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

