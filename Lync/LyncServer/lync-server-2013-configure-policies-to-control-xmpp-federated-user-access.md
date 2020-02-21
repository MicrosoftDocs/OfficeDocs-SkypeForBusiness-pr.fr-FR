---
title: 'Lync Server 2013 : configuration des stratégies de contrôle de l’accès des utilisateurs fédérés XMPP'
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
ms.openlocfilehash: 31889fa60f86d269e5efab696c2c27e48cc55d59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a><span data-ttu-id="f1ee2-102">Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ee2-102">Configure policies to control XMPP federated user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1ee2-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f1ee2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f1ee2-104">Cette documentation est préliminaire et sujette à modification.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="f1ee2-105">Des rubriques vides sont incluses comme espaces réservés.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="f1ee2-106">Lorsque vous configurez des stratégies visant à prendre en charge les partenaires fédérés du protocole XMPP, les stratégies s’appliquent aux utilisateurs des domaines fédérés XMPP, mais pas aux utilisateurs des fournisseurs de services de messagerie instantanée SIP (par exemple Windows Live) ou de domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-106">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="f1ee2-107">Vous configurez un **partenaire fédéré XMPP** pour chaque domaine fédéré XMPP avec lequel vous souhaitez que vos utilisateurs puissent communiquer et entrer en contact.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-107">You configure an **XMPP Federated Partner** for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="f1ee2-108">Les stratégies des partenaires fédérés XMPP ne sont disponibles que dans une seule étendue, et même si elles ne sont pas définies comme une stratégie globale, elles se comportent comme une stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-108">XMPP federated partners policies are only available in a single scope, though it is not defined as a global policy, acts as a global policy.</span></span> <span data-ttu-id="f1ee2-109">Pour définir une stratégie globale, de site ou de l’utilisateur pour les partenaires de la fédération XMPP, configurez l’étendue de la stratégie en créant et en configurant d’abord la stratégie d’accès externe pour l’étendue dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-109">To define a global, site or user policy for XMPP Federation Partners, you configure the policy scope by first creating and configuring the External Access Policy for the scope you require.</span></span> <span data-ttu-id="f1ee2-110">Pour plus d’informations sur les types de stratégies que vous pouvez configurer pour l’accès externe et la Fédération, voir gestion de la [Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-110">For details about the types of policies that you can configure for external access and federation, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f1ee2-111">Toutes les stratégies de type  <STRONG>Fédération et accès externe</STRONG> s’appliquent par le biais d’une mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-111">All <STRONG>Federation and External Access</STRONG> policies are applied through in-band provisioning.</span></span> <span data-ttu-id="f1ee2-112">Les stratégies qui s’appliquent à l’utilisateur, qui appartiennent à un site ou qui sont d’étendue globale, sont communiquées au client lors de la connexion.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-112">The policies that apply to the user, belong to a site, or are global in scope are communicated to the client during login.</span></span> <span data-ttu-id="f1ee2-113">Vous pouvez configurer les stratégies de manière à contrôler l’accès aux partenaires fédérés XMPP, même si vous n’avez pas activé de fédération XMPP pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-113">You can configure policies to control XMPP federated partner access, even if you have not enabled XMPP federation for your organization.</span></span> <span data-ttu-id="f1ee2-114">Toutefois, les stratégies que vous configurez ne prennent effet que lorsqu’une fédération de partenaires XMPP est déployée, activée et configurée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-114">However, the policies that you configure take effect only when you have XMPP partner federation deployed, enabled and configured for your organization.</span></span> <span data-ttu-id="f1ee2-115">Pour plus d’informations sur le déploiement et la configuration de la Fédération de partenaires XMPP, voir Configuration de la Fédération <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP, la Fédération XMPP et la messagerie instantanée publique dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-115">For details about deploying and configuring XMPP partner federation, see <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</A> in the Deployment documentation.</span></span> <span data-ttu-id="f1ee2-116">En outre, si vous spécifiez une stratégie utilisateur dans la stratégie d’accès externe pour contrôler les partenaires fédérés XMPP, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server 2013 et qui sont configurés pour utiliser la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-116">Additionally, if you specify a user policy in External Access Policy to control XMPP federated partners, the policy applies only to users that are enabled for Lync Server 2013 and configured to use the policy.</span></span>



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a><span data-ttu-id="f1ee2-117">Pour modifier une stratégie globale pour les partenaires fédérés XMPP</span><span class="sxs-lookup"><span data-stu-id="f1ee2-117">To edit a global policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="f1ee2-118">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1ee2-119">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-119">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f1ee2-120">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f1ee2-120">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f1ee2-121">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-121">In the left navigation bar, click **External User Access**, and then click **External Access Policy**.</span></span>

4.  <span data-ttu-id="f1ee2-122">Dans la page **Stratégie d’accès externe**, procédez comme suit pour la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-122">On the **External Access Policy** page, do the following for the global policy:</span></span>

5.  <span data-ttu-id="f1ee2-123">Cliquez sur la stratégie globale, sur **Modifier**, puis sur Afficher les détails.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-123">Click the global policy, click **Edit**, and then click Show details.</span></span>

6.  <span data-ttu-id="f1ee2-124">Attribuer une description à la stratégie globale (facultatif).</span><span class="sxs-lookup"><span data-stu-id="f1ee2-124">Provide a description for the Global policy (optional).</span></span>

7.  <span data-ttu-id="f1ee2-125">Sélectionnez **Autoriser les communications avec des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-125">Select **Enable communications with federated users**.</span></span>

8.  <span data-ttu-id="f1ee2-126">Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-126">Select **Enable communications with XMPP federated users**.</span></span>

9.  <span data-ttu-id="f1ee2-127">Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-127">Click **Commit** to save your changes to the Global policy.</span></span>

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a><span data-ttu-id="f1ee2-128">Pour créer une stratégie de site ou de l’utilisateur pour les partenaires fédérés XMPP</span><span class="sxs-lookup"><span data-stu-id="f1ee2-128">To create a site or user policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="f1ee2-p105">Cliquez sur **Nouveau**, puis sur **Stratégie de site** ou **Stratégie de l’utilisateur**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-p105">Click **New**, and then click **Site policy** or **User policy**. In **Select a Site**, click the appropriate site from the list and then click **OK**.</span></span>

2.  <span data-ttu-id="f1ee2-131">Attribuer une description à la stratégie de site (facultatif).</span><span class="sxs-lookup"><span data-stu-id="f1ee2-131">Provide a description for the Site policy (optional).</span></span>

3.  <span data-ttu-id="f1ee2-132">Dans la stratégie de site ou de l’utilisateur, sélectionnez **Autoriser les communications avec des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-132">In the site or user policy, select **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="f1ee2-133">Sélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-133">Select **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="f1ee2-134">Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-134">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a><span data-ttu-id="f1ee2-135">Pour modifier une stratégie existante pour les partenaires fédérés XMPP</span><span class="sxs-lookup"><span data-stu-id="f1ee2-135">To edit an existing policy for XMPP federated partners</span></span>

1.  <span data-ttu-id="f1ee2-136">Pour modifier une stratégie existante, sélectionnez la stratégie appropriée dans la liste, cliquez sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-136">To change an existing policy, select the appropriate policy in the list, click **Edit**, and then click **Show details**.</span></span>

2.  <span data-ttu-id="f1ee2-137">Modifier ou actualiser la description de la stratégie (facultatif).</span><span class="sxs-lookup"><span data-stu-id="f1ee2-137">Change or update the description for the policy (optional).</span></span>

3.  <span data-ttu-id="f1ee2-138">Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-138">Select or unselect **Enable communications with federated users**.</span></span>

4.  <span data-ttu-id="f1ee2-139">Sélectionnez ou désélectionnez **Autoriser les communications avec des utilisateurs fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-139">Select or unselect **Enable communications with XMPP federated users**.</span></span>

5.  <span data-ttu-id="f1ee2-140">Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-140">Click **Commit** to save your changes to the policy.</span></span>

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="f1ee2-141">Pour modifier une stratégie existante pour les partenaires fédérés XMPP à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ee2-141">To edit an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="f1ee2-142">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-142">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1ee2-143">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1ee2-144">Tapez ce qui suit dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-144">Type the following in the Lync Server Management Shell:</span></span>
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="f1ee2-145">Exemple de commande qui définit la stratégie globale pour l’accès des utilisateurs fédérés à true (activé) et à l’accès au domaine XMPP sur true (activé) :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-145">An example command that will set the global policy for Federated user access to True (enabled) and XMPP domain access to True (enabled):</span></span>
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a><span data-ttu-id="f1ee2-146">Pour créer une stratégie de site ou d’utilisateur pour les partenaires fédérés XMPP à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ee2-146">To create a site or user policy for XMPP federated partners using Windows PowerShell</span></span>

1.  <span data-ttu-id="f1ee2-147">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-147">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1ee2-148">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1ee2-149">Tapez ce qui suit dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-149">Type the following in the Lync Server Management Shell:</span></span>
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    <span data-ttu-id="f1ee2-150">Exemple de commande permettant d’activer une stratégie de site concernant le site Redmond pour Accès utilisateur fédéré et d’activer l’accès au domaine XMPP :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-150">An example command that will set a site policy for the Redmond site for Federated user access to enabled and XMPP domain access to enabled:</span></span>
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a><span data-ttu-id="f1ee2-151">Pour supprimer une stratégie existante pour les partenaires fédérés XMPP à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1ee2-151">To delete an existing policy for XMPP federated partners by using Windows PowerShell</span></span>

1.  <span data-ttu-id="f1ee2-152">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-152">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f1ee2-153">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f1ee2-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f1ee2-154">Tapez ce qui suit dans Lync Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-154">Type the following in the Lync Server Management Shell:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    <span data-ttu-id="f1ee2-155">Exemple de commande permettant de supprimer une stratégie de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-155">An example command that will delete a user policy:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  <span data-ttu-id="f1ee2-156">Exemple de commande permettant de rétablir les paramètres par défaut de la stratégie globale :</span><span class="sxs-lookup"><span data-stu-id="f1ee2-156">An example command that will reset the global policy to defaults:</span></span>
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f1ee2-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1ee2-157">See Also</span></span>


[<span data-ttu-id="f1ee2-158">Affectation d’une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ee2-158">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[<span data-ttu-id="f1ee2-159">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ee2-159">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[<span data-ttu-id="f1ee2-160">Gérer les partenaires fédérés XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1ee2-160">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[<span data-ttu-id="f1ee2-161">Set-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f1ee2-161">Set-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[<span data-ttu-id="f1ee2-162">New-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f1ee2-162">New-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[<span data-ttu-id="f1ee2-163">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f1ee2-163">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="f1ee2-164">Remove-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f1ee2-164">Remove-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[<span data-ttu-id="f1ee2-165">Grant-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="f1ee2-165">Grant-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

