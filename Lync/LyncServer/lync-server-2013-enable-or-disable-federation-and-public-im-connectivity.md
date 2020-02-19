---
title: 'Lync Server 2013 : activation ou désactivation de la Fédération et de la connectivité PIC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abc035b60c052981834a3bc6e0c1bb4cf7b68777
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a><span data-ttu-id="72231-102">Activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72231-102">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72231-103">_**Dernière modification de la rubrique :** 2013-06-24_</span><span class="sxs-lookup"><span data-stu-id="72231-103">_**Topic Last Modified:** 2013-06-24_</span></span>

<span data-ttu-id="72231-104">La fédération doit être prise en charge pour permettre aux utilisateurs possédant un compte auprès d’un client approuvé ou d’une organisation partenaire, y compris les domaines partenaires et les utilisateurs de fournisseurs de services de messagerie instantanée publics que vous prenez en charge, de collaborer avec des utilisateurs de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="72231-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="72231-105">La fédération est également nécessaire pour utiliser un fournisseur de service Exchange hébergé afin de procurer une messagerie vocale aux utilisateurs Voix Entreprise dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tel que Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="72231-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="72231-106">Une fois que vous avez établi une relation d’approbation avec ces domaines externes, vous pouvez autoriser les utilisateurs de ces domaines à accéder à votre déploiement et à participer à des communications Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72231-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Lync Server communications.</span></span> <span data-ttu-id="72231-107">Cette relation de confiance est appelée « fédération » ; elle n’est pas liée à une relation de confiance Active Directory et n’en dépend pas non plus.</span><span class="sxs-lookup"><span data-stu-id="72231-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="72231-p102">Pour prendre en charge l’accès des utilisateurs de domaines fédérés, vous devez activer la fédération. Si vous activez la fédération pour votre entreprise, vous devez également préciser si vous voulez implémenter les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="72231-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="72231-110">**Activer la découverte**   du domaine partenaire si vous activez cette option, Lync Server utilise des enregistrements DNS (Domain Name System) pour essayer de découvrir les domaines qui ne sont pas répertoriés dans la liste des domaines autorisés, en évaluant automatiquement le trafic entrant des partenaires fédérés découverts et en limitant ou bloquant le trafic en fonction du niveau de confiance, de la quantité de trafic et des paramètres d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="72231-110">**Enable partner domain discovery**   If you enable this option, Lync Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="72231-111">Si vous ne sélectionnez pas cette option, l’accès des utilisateurs fédérés est uniquement activé pour les utilisateurs des domaines inclus dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="72231-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="72231-112">Que vous choisissiez ou non cette option, vous pouvez bloquer ou autoriser des domaines individuels, et restreindre l’accès à des serveurs spécifiques exécutant le service Edge d’accès dans le domaine fédéré.</span><span class="sxs-lookup"><span data-stu-id="72231-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="72231-113">Pour plus d’informations sur le contrôle de l’accès par les domaines fédérés, voir [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="72231-113">For details about controlling access by federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>

  - <span data-ttu-id="72231-114">**Envoyer une notification d’exclusion relative à l’archivage aux partenaires**     fédérés l’avis d’exclusion de responsabilité est envoyé aux partenaires fédérés pour lesquels l’archivage dans votre déploiement est en place.</span><span class="sxs-lookup"><span data-stu-id="72231-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="72231-115">Si vous prenez en charge l’archivage des communications externes avec des domaines de partenaires fédérés, vous devez activer la notification d’exclusion relative à l’archivage afin de prévenir les partenaires que leurs messages sont archivés.</span><span class="sxs-lookup"><span data-stu-id="72231-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="72231-p105">Si plus tard, vous souhaitez empêcher temporairement ou définitivement des utilisateurs d’accéder aux domaines fédérés, vous pouvez désactiver la fédération pour votre entreprise. Suivez la procédure de cette section pour activer ou désactiver l’accès des utilisateurs fédérés dans votre entreprise, en spécifiant notamment les options de fédération que vous souhaitez prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="72231-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="72231-118">L’activation de la fédération pour votre organisation signifie uniquement que vos serveurs exécutant le service Edge d’accès prennent en charge le routage vers des domaines fédérés.</span><span class="sxs-lookup"><span data-stu-id="72231-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="72231-119">Les utilisateurs des domaines fédérés ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="72231-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="72231-120">Les utilisateurs de fournisseurs de services de messagerie instantanée publics ne peuvent pas participer aux sessions de messagerie instantanée ni aux conférences dans votre organisation tant que vous n’avez pas également configuré au moins une stratégie de prise en charge de la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="72231-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="72231-121">Lync Server ne peut pas utiliser de service Exchange hébergé pour fournir des services de répondeur automatique, Outlook Voice Access (y compris la messagerie vocale) ou des services de standard automatique aux utilisateurs dont les boîtes aux lettres se trouvent sur un service Exchange hébergé tant que vous n’avez pas configuré de stratégie de messagerie vocale hébergée qui procure des informations de routage.</span><span class="sxs-lookup"><span data-stu-id="72231-121">Lync Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="72231-122">Pour plus d’informations sur la configuration des stratégies de communication avec des utilisateurs de domaines fédérés dans d’autres organisations, voir <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="72231-122">For details about configuring policies for communication with users of federated domains in other organizations, see <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP federated domains for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="72231-123">Qui plus est, si vous souhaitez prendre en charge les communications avec des utilisateurs de fournisseurs de services de messagerie instantanée, vous devez configurer des stratégies à cet effet et configurer la prise en charge des différents fournisseurs de services de votre choix.</span><span class="sxs-lookup"><span data-stu-id="72231-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="72231-124">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gestion des fournisseurs fédérés SIP pour votre organisation dans Lync Server 2013</A> dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="72231-124">For details, see <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP federated providers for your organization in Lync Server 2013</A> in the Operations documentation.</span></span> <span data-ttu-id="72231-125">Pour plus d’informations sur la création d’une stratégie de messagerie vocale hébergée, voir <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">gérer les stratégies de messagerie vocale hébergées dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="72231-125">For details about creating a hosted voice mail policy, see <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="72231-126">Pour activer ou désactiver l’accès des utilisateurs fédérés pour votre entreprise</span><span class="sxs-lookup"><span data-stu-id="72231-126">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="72231-127">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="72231-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="72231-128">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72231-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="72231-129">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="72231-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="72231-130">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Configuration du serveur Edge d’accès**.</span><span class="sxs-lookup"><span data-stu-id="72231-130">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="72231-131">Dans la page **Configuration du serveur Edge d’accès**, cliquez sur **Global**, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="72231-131">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="72231-132">Dans **Modifier la configuration du serveur Edge d’accès**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="72231-132">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="72231-133">Pour activer l’accès des utilisateurs fédérés pour votre entreprise, activez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="72231-133">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="72231-134">Pour désactiver l’accès des utilisateurs fédérés pour votre entreprise, désactivez la case à cocher **Autoriser les communications avec des utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="72231-134">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="72231-135">Si vous avez activé la case à cocher **Autoriser les communications avec des utilisateurs fédérés**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="72231-135">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="72231-136">Pour prendre en charge la découverte automatique des domaines partenaires, activez la case à cocher **Activer la découverte du domaine partenaire**.</span><span class="sxs-lookup"><span data-stu-id="72231-136">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="72231-137">Si votre entreprise prend en charge l’archivage des communications externes, activez la case à cocher **Envoyer une notification d’exclusion aux partenaires fédérés relative à l’archivage**.</span><span class="sxs-lookup"><span data-stu-id="72231-137">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="72231-138">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="72231-138">Click **Commit**.</span></span>

<span data-ttu-id="72231-139">Pour permettre aux utilisateurs fédérés de collaborer avec des utilisateurs dans votre déploiement Lync Server 2013, vous devez également configurer au moins une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="72231-139">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="72231-140">Pour plus d’informations, voir [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) dans la documentation de déploiement ou la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="72231-140">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="72231-141">Pour contrôler l’accès à des domaines fédérés spécifiques, reportez-vous à la rubrique [configurer la prise en charge des domaines externes autorisés dans Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) dans la documentation sur le déploiement ou les opérations.</span><span class="sxs-lookup"><span data-stu-id="72231-141">To control access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="72231-142">Activation ou désactivation de la Fédération et de la connectivité PIC à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="72231-142">Enabling or Disabling Federation and Public IM Connectivity by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="72231-143">La Fédération et la connectivité PIC peuvent également être gérées à l’aide de Windows PowerShell et de l’applet de commande Set-CsAccessEdgeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="72231-143">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="72231-144">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="72231-144">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="72231-145">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="72231-145">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="72231-146">Pour activer la Fédération et la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="72231-146">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="72231-147">Pour activer la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à True ($True) :</span><span class="sxs-lookup"><span data-stu-id="72231-147">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="72231-148">Pour désactiver la Fédération et la connectivité PIC</span><span class="sxs-lookup"><span data-stu-id="72231-148">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="72231-149">Pour désactiver la fédération et la connectivité PIC, définissez la valeur de la propriété **AllowFederatedUsers** à False ($False) :</span><span class="sxs-lookup"><span data-stu-id="72231-149">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

