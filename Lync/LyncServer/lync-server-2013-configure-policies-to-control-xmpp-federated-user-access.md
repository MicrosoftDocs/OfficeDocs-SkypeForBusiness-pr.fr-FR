---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="aeb05-102">Configuration des stratégies de contrôle d’accès des utilisateurs fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb05-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aeb05-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="aeb05-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="aeb05-104">Il s’agit d’une documentation préliminaire susceptible d’être modifiée.</span><span class="sxs-lookup"><span data-stu-id="aeb05-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="aeb05-105">Des rubriques vides sont incluses sous forme d’espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="aeb05-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="aeb05-106">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="aeb05-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="aeb05-107">Vous configurez un **partenaire fédéré de XMPP** pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="aeb05-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="aeb05-108">Les stratégies des partenaires fédérés de XMPP ne sont disponibles qu’en une seule étendue, même si elle n’est pas définie en tant que stratégie globale, fait office de stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="aeb05-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="aeb05-109">Pour définir une stratégie globale de site ou d’utilisateur pour les partenaires de Fédération XMPP, vous devez configurer la portée de la stratégie en commençant par la création et la configuration de la stratégie d’accès externe dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="aeb05-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="aeb05-110">Pour plus d’informations sur les types de stratégies que vous pouvez configurer pour l’accès externe et la Fédération, voir gestion de la [Fédération et accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation sur les opérations.</span><span class="sxs-lookup"><span data-stu-id="aeb05-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aeb05-111">Toutes les stratégies de <STRONG>Fédération et d’accès externe</STRONG> sont appliquées via la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="aeb05-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="aeb05-112">Les politiques qui s’appliquent à l’utilisateur, qui font partie d’un site ou qui sont globales dans l’étendue, sont communiquées au client au moment de la connexion.</span><span class="sxs-lookup"><span data-stu-id="aeb05-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="aeb05-113">Vous pouvez configurer des stratégies pour contrôler l’accès par le partenaire fédéré de XMPP, même si vous n’avez pas activé la Fédération XMPP pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aeb05-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="aeb05-114">Toutefois, les stratégies que vous configurez prennent effet uniquement lorsque vous avez déployé la Fédération de partenaires XMPP, activée et configurée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="aeb05-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="aeb05-115">Pour plus d’informations sur le déploiement et la configuration de la Fédération de partenaire XMPP, voir Configuration de la Fédération <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP, de la Fédération et de la messagerie instantanée publique dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aeb05-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="aeb05-116">Par ailleurs, si vous spécifiez une stratégie d’utilisateur dans une stratégie d’accès externe pour contrôler les partenaires fédérés de XMPP, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser cette stratégie.</span><span class="sxs-lookup"><span data-stu-id="aeb05-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="aeb05-117">Pour modifier une stratégie globale pour les partenaires fédérés de XMPP</span><span class="sxs-lookup"><span data-stu-id="aeb05-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="aeb05-118">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aeb05-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aeb05-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aeb05-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="aeb05-120">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aeb05-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aeb05-121">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="aeb05-122">Dans la page de **stratégie d’accès externe** , procédez comme suit pour la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="aeb05-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="aeb05-123">Cliquez sur la stratégie globale, sur **modifier**, puis sur Afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="aeb05-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="aeb05-124">Entrez une description pour la politique globale (facultatif).</span><span class="sxs-lookup"><span data-stu-id="aeb05-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="aeb05-125">Sélectionnez **activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="aeb05-126">Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="aeb05-127">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="aeb05-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="aeb05-128">Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés de XMPP</span><span class="sxs-lookup"><span data-stu-id="aeb05-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="aeb05-129">Cliquez sur **nouveau**, puis sur **politique du site** ou stratégie de l' **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-129">Click **New**, and then click **Site policy** or **User policy**.</span></span> <span data-ttu-id="aeb05-130">Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-130">In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="aeb05-131">Entrez une description pour la stratégie de site (facultatif).</span><span class="sxs-lookup"><span data-stu-id="aeb05-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="aeb05-132">Dans la stratégie de site ou d’utilisateur, sélectionnez **activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="aeb05-133">Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="aeb05-134">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="aeb05-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="aeb05-135">Pour modifier une stratégie existante pour les partenaires fédérés de XMPP</span><span class="sxs-lookup"><span data-stu-id="aeb05-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="aeb05-136">Pour modifier une stratégie existante, sélectionnez la stratégie appropriée dans la liste, cliquez sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="aeb05-137">Modifiez ou mettez à jour la description de la stratégie (facultatif).</span><span class="sxs-lookup"><span data-stu-id="aeb05-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="aeb05-138">Activez ou désactivez l’option **activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="aeb05-139">Activez ou désactivez l’option **activer les communications avec les utilisateurs fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="aeb05-140">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="aeb05-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="aeb05-141">Pour modifier une stratégie existante pour les partenaires fédérés de XMPP à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb05-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="aeb05-142">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aeb05-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aeb05-143">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb05-144">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="aeb05-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="aeb05-145">Un exemple de commande qui définit la stratégie globale pour l’accès utilisateur fédéré à vrai (activé) et à l’accès au domaine XMPP sur vrai (activé) :</span><span class="sxs-lookup"><span data-stu-id="aeb05-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="aeb05-146">Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés de XMPP utilisant Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb05-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="aeb05-147">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aeb05-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aeb05-148">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb05-149">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="aeb05-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="aeb05-150">Commande d’exemple qui définira une stratégie de site pour le site de Redmond pour l’accès des utilisateurs fédérés à l’accès au domaine activé et XMPP sur activé :</span><span class="sxs-lookup"><span data-stu-id="aeb05-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="aeb05-151">Pour supprimer une stratégie existante pour les partenaires fédérés de XMPP à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeb05-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="aeb05-152">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aeb05-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aeb05-153">Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="aeb05-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="aeb05-154">Dans Lync Server Management Shell, tapez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="aeb05-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="aeb05-155">Voici un exemple de commande qui supprimera une stratégie de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="aeb05-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="aeb05-156">Par exemple, la commande suivante réinitialise la stratégie globale sur les valeurs par défaut :</span><span class="sxs-lookup"><span data-stu-id="aeb05-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aeb05-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="aeb05-157">See Also</span></span>


[<span data-ttu-id="aeb05-158">Attribution d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb05-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="aeb05-159">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb05-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="aeb05-160">Gestion des partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aeb05-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="aeb05-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aeb05-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="aeb05-162">Nouveau-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aeb05-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="aeb05-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aeb05-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="aeb05-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aeb05-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="aeb05-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="aeb05-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

