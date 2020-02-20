---
title: 'Lync Server 2013 : configuration des stratégies de contrôle d’accès des utilisateurs fédérés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2395efc4351f7ec91e489eaae3dd57a973e77e86
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="1a082-102">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a082-102">Configure policies to control federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a082-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="1a082-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="1a082-104">Lorsque vous configurez des stratégies pour prendre en charge les communications avec les partenaires fédérés, les stratégies s’appliquent aux utilisateurs de domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="1a082-104">When you configure policies to support communications with federated partners, the policies apply to users of federated domains.</span></span> <span data-ttu-id="1a082-105">Vous pouvez configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs de domaines fédérés peuvent collaborer avec vos utilisateurs Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a082-105">You can configure one or more external user access policies to control whether users of federated domains can collaborate with your Lync Server 2013 users.</span></span> <span data-ttu-id="1a082-106">Pour contrôler l’accès des utilisateurs fédérés, vous pouvez configurer des stratégies au niveau global, site et utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1a082-106">To control federated user access, you can configure policies at the global, site, and user level.</span></span> <span data-ttu-id="1a082-107">Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie.</span><span class="sxs-lookup"><span data-stu-id="1a082-107">Lync Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="1a082-108">La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente).</span><span class="sxs-lookup"><span data-stu-id="1a082-108">Lync Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="1a082-109">Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.</span><span class="sxs-lookup"><span data-stu-id="1a082-109">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1a082-110">Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, même si vous n’avez pas activé la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a082-110">You can configure policies to control federated user access, even if you have not enabled federation for your organization.</span></span> <span data-ttu-id="1a082-111">Toutefois, les stratégies que vous configurez s’appliquent uniquement si la fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a082-111">However, the policies that you configure are in effect only when you have federation enabled for your organization.</span></span> <span data-ttu-id="1a082-112">Pour plus d’informations sur l’activation de la Fédération, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A> dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1a082-112">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="1a082-113">En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs fédérés, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="1a082-113">Additionally, if you specify a user policy to control federated user access, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="1a082-114">Pour configurer une stratégie afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="1a082-114">To configure a policy to support access by users of federated domains</span></span>

1.  <span data-ttu-id="1a082-115">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1a082-115">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a082-116">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a082-116">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a082-117">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a082-117">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a082-118">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="1a082-118">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="1a082-119">Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a082-119">On the **External Access Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1a082-120">Pour configurer la stratégie globale afin qu’elle prenne en charge l’accès des utilisateurs fédérés, cliquez sur la stratégie globale, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1a082-120">To configure the global policy to support federated user access, click the global policy, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="1a082-p104">Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a082-p104">To create a new site policy, click **New**, and then click **Site policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>
    
      - <span data-ttu-id="1a082-123">Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1a082-123">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="1a082-124">Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableFederatedUsers** pour une stratégie utilisateur qui active les communications pour les utilisateurs de domaine fédéré).</span><span class="sxs-lookup"><span data-stu-id="1a082-124">In **New External Access Policy**, create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableFederatedUsers** for a user policy that enables communications for federated domain users).</span></span>
    
      - <span data-ttu-id="1a082-125">Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1a082-125">To change an existing policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a082-126">(Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="1a082-126">(Optional) If you want to add or edit a description, specify the information for the policy in **Description**.</span></span>

6.  <span data-ttu-id="1a082-127">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1a082-127">Do one of the following:</span></span>
    
      - <span data-ttu-id="1a082-128">Pour activer l’accès des utilisateurs fédérés pour la stratégie, activez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="1a082-128">To enable federated user access for the policy, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="1a082-129">Pour désactiver l’accès des utilisateurs fédérés pour la stratégie, désactivez la case à cocher **autoriser les communications avec des utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="1a082-129">To disable federated user access for the policy, clear the **Enable communications with federated users** check box.</span></span>

7.  <span data-ttu-id="1a082-130">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1a082-130">Click **Commit**.</span></span>

<span data-ttu-id="1a082-131">Pour activer l’accès des utilisateurs fédérés, vous devez également activer la prise en charge de la Fédération dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="1a082-131">To enable federated user access, you must also enable support for federation in your organization.</span></span> <span data-ttu-id="1a082-132">Pour plus d’informations, consultez la rubrique [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="1a082-132">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).</span></span>

<span data-ttu-id="1a082-133">S’il s’agit d’une stratégie utilisateur, vous devez également appliquer la stratégie aux utilisateurs que vous voulez être en mesure de collaborer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="1a082-133">If this is a user policy, you must also apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="1a082-134">Pour plus d’informations, reportez-vous [à la rubrique attribuer une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span><span class="sxs-lookup"><span data-stu-id="1a082-134">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).</span></span>

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="1a082-135">Pour configurer une stratégie existante à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="1a082-135">To configure an existing policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="1a082-136">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1a082-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a082-137">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1a082-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1a082-138">Tapez ce qui suit dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1a082-138">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="1a082-139">Exemple de commande qui définit la stratégie globale pour l’accès des utilisateurs fédérés à activé, l’accès au domaine XMPP à activé, l’accès des utilisateurs distants à activé, l’accès des fournisseurs publics à activé et la possibilité d’utiliser l’audio et la vidéo pour les fournisseurs publics qui le prennent en charge :</span><span class="sxs-lookup"><span data-stu-id="1a082-139">An example command that will set the global policy for Federated user access to enabled, XMPP domain access to enabled, Remote user access to enabled, Public provider access to enabled, and grant the ability to use audio and video for public providers that support it:</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="1a082-140">Le paramètre « EnablePublicCloudAudioVideoAccess » n’a pas de sélection correspondante dans le panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="1a082-140">The parameter “EnablePublicCloudAudioVideoAccess” does not have a corresponding selection in the Lync Server Control Panel</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="1a082-141">Pour créer une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="1a082-141">To create a new policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="1a082-142">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1a082-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a082-143">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1a082-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1a082-144">Tapez ce qui suit dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="1a082-144">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    <span data-ttu-id="1a082-145">Exemple de création d’une nouvelle stratégie de site :</span><span class="sxs-lookup"><span data-stu-id="1a082-145">An example of creating a new site policy:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a><span data-ttu-id="1a082-146">Pour supprimer ou réinitialiser une stratégie à l’aide de Windows PowerShell afin de prendre en charge l’accès des utilisateurs des domaines fédérés</span><span class="sxs-lookup"><span data-stu-id="1a082-146">To delete or reset a policy using Windows PowerShell to support access by users of federated domains</span></span>

1.  <span data-ttu-id="1a082-147">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1a082-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1a082-148">Tapez ce qui suit dans Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1a082-148">Type the following in the Lync Server Management Shell</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    <span data-ttu-id="1a082-149">Exemple de réinitialisation de la stratégie globale (la stratégie globale peut uniquement avoir son paramètre supprimé.</span><span class="sxs-lookup"><span data-stu-id="1a082-149">An example of resetting the global policy (The global policy can only have its setting removed.</span></span> <span data-ttu-id="1a082-150">La stratégie ne peut pas être supprimée) :</span><span class="sxs-lookup"><span data-stu-id="1a082-150">The policy cannot be deleted):</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    <span data-ttu-id="1a082-151">Pour supprimer une stratégie de site, tapez :</span><span class="sxs-lookup"><span data-stu-id="1a082-151">To remove a site policy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    <span data-ttu-id="1a082-152">Supprime la stratégie de site Redmond.</span><span class="sxs-lookup"><span data-stu-id="1a082-152">Deletes the site policy Redmond.</span></span> <span data-ttu-id="1a082-153">Pour supprimer une stratégie utilisateur nommée UserEAPPolicy, tapez :</span><span class="sxs-lookup"><span data-stu-id="1a082-153">To delete a user policy named UserEAPPolicy, type:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a082-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a082-154">See Also</span></span>


[<span data-ttu-id="1a082-155">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a082-155">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[<span data-ttu-id="1a082-156">Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a082-156">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[<span data-ttu-id="1a082-157">Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a082-157">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="1a082-158">Gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a082-158">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[<span data-ttu-id="1a082-159">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a082-159">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="1a082-160">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a082-160">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="1a082-161">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a082-161">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="1a082-162">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a082-162">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="1a082-163">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="1a082-163">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

