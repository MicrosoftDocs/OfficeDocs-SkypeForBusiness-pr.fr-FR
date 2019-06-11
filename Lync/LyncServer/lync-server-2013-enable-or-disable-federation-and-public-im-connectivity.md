---
title: 'Lync Server 2013 : Activation ou désactivation de la fédération et de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4123a17c01ad6358038b1937b57bab29eeec85c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="6b805-102">Activation ou désactivation de la fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b805-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b805-103">_**Dernière modification de la rubrique:** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="6b805-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="6b805-104">La prise en charge de la Fédération est requise pour permettre aux utilisateurs disposant d’un compte auprès d’un client ou d’une organisation de partenaire approuvés, notamment des domaines de partenariat et des utilisateurs de fournisseurs de messagerie instantanée publics que vous prenez en charge, pour collaborer avec des utilisateurs dans votre société.</span><span class="sxs-lookup"><span data-stu-id="6b805-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="6b805-105">La Fédération est également requise pour l’utilisation d’un fournisseur de services Exchange hébergés pour fournir des messages vocaux aux utilisateurs vocaux d’entreprise dont la boîte aux lettres est située sur un service Exchange hébergé tel que Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6b805-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="6b805-106">Lorsque vous établissez une relation d’approbation avec ces domaines externes, vous pouvez autoriser des utilisateurs dans ces domaines à accéder à votre déploiement et participer aux communications de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b805-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="6b805-107">Cette relation d’approbation est appelée Fédération et ne dépend pas d’une relation d’approbation Active Directory ou n’est pas liée.</span><span class="sxs-lookup"><span data-stu-id="6b805-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="6b805-108">Pour prendre en charge l’accès par des utilisateurs de domaines fédérés, vous devez activer la Fédération.</span><span class="sxs-lookup"><span data-stu-id="6b805-108">To support access by users of federated domains, you must enable federation.</span></span> <span data-ttu-id="6b805-109">Si vous activez la Fédération pour votre organisation, vous devez également spécifier si vous voulez implémenter les options suivantes:</span><span class="sxs-lookup"><span data-stu-id="6b805-109">If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="6b805-110">**Activer la découverte**   de domaine partenaire si vous activez cette option, Lync Server utilise des enregistrements DNS (Domain Name System) pour essayer de détecter les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant provenant de la découverte fédérée partenaires et limiter ou bloquer ce trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="6b805-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="6b805-111">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est activé uniquement pour les utilisateurs des domaines que vous incluez dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="6b805-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="6b805-112">Si vous sélectionnez cette option, vous pouvez spécifier que les domaines individuels doivent être bloqués ou autorisés, y compris limiter l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="6b805-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="6b805-113">Pour plus d’informations sur le contrôle d’accès par des domaines fédérés, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="6b805-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="6b805-114">**Envoyer une exclusion de responsabilité à l’archivage pour les partenaires**     fédérés vous recevez des notifications de non-responsabilité pour les partenaires fédérés dans lesquels l’archivage de votre déploiement est en place.</span><span class="sxs-lookup"><span data-stu-id="6b805-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="6b805-115">Si vous prise en charge de l’archivage des communications externes avec les domaines de partenaires fédérés, vous devez activer la notification d’exclusion de responsabilité de l’archivage pour avertir les partenaires de l’archivage de leurs messages.</span><span class="sxs-lookup"><span data-stu-id="6b805-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="6b805-116">Si vous souhaitez par la suite empêcher l’accès temporaire ou définitive aux utilisateurs de domaines fédérés, vous pouvez désactiver la Fédération pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6b805-116">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization.</span></span> <span data-ttu-id="6b805-117">Utilisez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation, y compris les options de Fédération appropriées qui doivent être prises en charge pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="6b805-117">Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b805-118">L’activation de la Fédération pour votre organisation indique uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="6b805-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="6b805-119">Les utilisateurs dans les domaines fédérés ne peuvent pas participer à la messagerie instantanée ou aux conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="6b805-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="6b805-120">Les utilisateurs des fournisseurs de service de messagerie instantanée publique ne peuvent pas participer à la messagerie instantanée ou aux conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie pour la prise en charge de la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="6b805-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="6b805-121">Lync Server ne peut pas utiliser un service Exchange hébergé pour fournir des réponses aux appels, Outlook Voice Access (y compris la messagerie vocale), ou les services de standard automatique pour les utilisateurs dont la boîte aux lettres est située sur un service Exchange hébergé tant que vous n’avez pas configuré une stratégie de messagerie vocale hébergée. qui fournit des informations de routage.</span><span class="sxs-lookup"><span data-stu-id="6b805-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="6b805-122">Pour plus d’informations sur la configuration des stratégies de communication avec des utilisateurs de domaines fédérés dans d’autres organisations, voir <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation opérations.</span><span class="sxs-lookup"><span data-stu-id="6b805-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="6b805-123">Par ailleurs, si vous souhaitez prendre en charge les communications avec les utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies pour le prendre en charge et configurer également la prise en charge des fournisseurs de services individuels que vous voulez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="6b805-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="6b805-124">Pour plus d’informations, reportez-vous à <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gérer les fournisseurs fédérés SIP pour votre organisation dans</A> la documentation des opérations de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6b805-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="6b805-125">Pour plus d’informations sur la création d’une stratégie de messagerie vocale hébergée, consultez <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">gérer les stratégies de messagerie vocale hébergées dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="6b805-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="6b805-126">Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre organisation</span><span class="sxs-lookup"><span data-stu-id="6b805-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="6b805-127">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="6b805-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6b805-128">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6b805-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6b805-129">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b805-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6b805-130">Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis cliquez sur **configuration d’Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="6b805-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="6b805-131">Dans la page **configuration de Microsoft Edge** , cliquez sur **Global**, sur **modifier**, puis sur **afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="6b805-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="6b805-132">Dans **modification de la configuration d’Access Edge**, effectuez l’une des opérations suivantes:</span><span class="sxs-lookup"><span data-stu-id="6b805-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="6b805-133">Pour autoriser l’accès des utilisateurs fédérés pour votre organisation, activez la case à cocher **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="6b805-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="6b805-134">Pour désactiver l’accès des utilisateurs fédérés pour votre organisation, décochez la case **activer les communications avec les utilisateurs fédérés** .</span><span class="sxs-lookup"><span data-stu-id="6b805-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="6b805-135">Si vous avez activé la case à cocher **activer les communications avec les utilisateurs fédérés** , procédez comme suit:</span><span class="sxs-lookup"><span data-stu-id="6b805-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="6b805-136">Si vous voulez prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **activer la découverte de domaines partenaires** .</span><span class="sxs-lookup"><span data-stu-id="6b805-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="6b805-137">Si votre organisation prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer le démenti d’archivage aux partenaires fédérés** .</span><span class="sxs-lookup"><span data-stu-id="6b805-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="6b805-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="6b805-138">Click **Commit**.</span></span>

<span data-ttu-id="6b805-139">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans le déploiement de Lync Server 2013, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="6b805-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="6b805-140">Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="6b805-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="6b805-141">Pour contrôler l’accès pour des domaines fédérés spécifiques, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation relative aux opérations de déploiement ou aux opérations.</span><span class="sxs-lookup"><span data-stu-id="6b805-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6b805-142">Activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique à l’aide d’applets de cmdlet Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b805-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6b805-143">La connectivité de Fédération et de messagerie instantanée publique peut également être gérée à l’aide de Windows PowerShell et de l’applet de connexion Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="6b805-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="6b805-144">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b805-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6b805-145">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="6b805-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="6b805-146">Pour activer la connectivité de Fédération et de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="6b805-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="6b805-147">Pour activer la connectivité de Fédération et de messagerie instantanée publique, définissez la valeur de la propriété **AllowFederatedUsers** sur True ($true):</span><span class="sxs-lookup"><span data-stu-id="6b805-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="6b805-148">Pour désactiver la connectivité de Fédération et de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="6b805-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="6b805-149">Pour désactiver la connectivité de Fédération et de messagerie instantanée publique, définissez la valeur de la propriété **AllowFederatedUsers** sur false ($false):</span><span class="sxs-lookup"><span data-stu-id="6b805-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

