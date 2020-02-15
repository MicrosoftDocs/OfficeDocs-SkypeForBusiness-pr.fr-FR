---
title: 'Lync Server 2013 : configuration de la prise en charge des domaines externes autorisés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a><span data-ttu-id="4ea0d-102">Configurer la prise en charge des domaines externes autorisés dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4ea0d-102">Configure support for allowed external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ea0d-103">_**Dernière modification de la rubrique :** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4ea0d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4ea0d-p101">Si vous avez configuré la prise en charge des partenaires fédérés, vous pouvez décider des domaines qui sont autorisés à se fédérer avec votre organisation. Vous devez configurer un ou plusieurs domaines externes spécifiques en tant que domaines fédérés autorisés. Pour ce faire, ajoutez chaque domaine à la liste des domaines autorisés. Même si la découverte de partenaire est activée pour votre organisation, effectuez cette opération si le domaine est un partenaire fédéré qui devra peut-être communiquer avec plus de 1 000 de vos utilisateurs ou envoyer plus de 20 messages par seconde. Si la découverte de partenaire est désactivée pour votre organisation, seuls les utilisateurs des domaines externes que vous ajoutez à la liste des domaines autorisés peuvent utiliser la messagerie instantanée et les services de conférence avec les utilisateurs de votre organisation. Si vous souhaitez limiter l’accès d’un domaine fédéré à un serveur spécifique qui exécute le service Edge d’accès du partenaire fédéré, vous pouvez spécifier le nom de domaine du serveur exécutant le service Edge d’accès pour chaque domaine présent dans la liste des domaines autorisés.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-p101">If you have configured support for federated partners, you can manage which specific domains can federate with your organization. You configure one or more specific external domains as allowed federated domains. To do this, add each domain to the list of allowed domains. Even if partner discovery is enabled for your organization, do this if the domain is a federated partner that might need to communicate with more than 1,000 of your users or might need to send more than 20 messages per second. If partner discovery is not enabled for your organization, only users of external domains that you add to the allowed domains list can participate in IM and conferencing with users in your organization. If you want to restrict access for a federated domain to a specific server running the Access Edge service of the federated partner, you can specify the domain name of the server running the Access Edge service for each domain in the list of allowed domains.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ea0d-110">Cette procédure décrit la façon de configurer la prise en charge de domaines spécifiques, mais l’implémentation de la prise en charge des utilisateurs fédérés nécessite également d’activer la prise en charge des utilisateurs fédérés pour votre organisation, mais aussi de configurer et d’appliquer des stratégies permettant de spécifier les utilisateurs qui sont autorisés à collaborer avec les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-110">This procedure describes how to configure support for specific domains, but implementing support for federated users also requires that you enable support for federated users for your organization, and configure and apply policies to control which users can collaborate with federated users.</span></span> <span data-ttu-id="4ea0d-111">Pour plus d’informations sur l’activation de la prise en charge des utilisateurs fédérés, voir <A href="lync-server-2013-enable-or-disable-remote-user-access.md">activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-111">For details about enabling support for federated users, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A>.</span></span> <span data-ttu-id="4ea0d-112">Pour plus d’informations sur la configuration des stratégies de contrôle de la Fédération, voir <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-112">For details about configuring policies to control federation, see <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure policies to control federated user access in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a><span data-ttu-id="4ea0d-113">Pour ajouter un domaine externe à la liste des domaines autorisés</span><span class="sxs-lookup"><span data-stu-id="4ea0d-113">To add an external domain to the list of allowed domains</span></span>

1.  <span data-ttu-id="4ea0d-114">Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4ea0d-115">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4ea0d-116">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4ea0d-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4ea0d-117">Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis cliquez sur **Domaines fédérés**.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-117">In the left navigation bar, click **External User Access**, and then click **Federated Domains**.</span></span>

4.  <span data-ttu-id="4ea0d-118">Dans la page **Domaines fédérés**, cliquez sur **Nouveau**, puis sur **Domaine autorisé**.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-118">On the **Federated Domains** page, click **New**, and then click **Allowed domain**.</span></span>

5.  <span data-ttu-id="4ea0d-119">Dans **Nouveaux domaines fédérés**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="4ea0d-119">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="4ea0d-120">Dans **Nom de domaine complet (ou FQDN)**, tapez le nom de domaine du partenaire fédéré.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-120">In **Domain name (or FQDN)**, type the name of the federated partner domain.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4ea0d-p104">Ce nom doit être unique et ne doit pas déjà exister en tant que domaine autorisé pour ce serveur exécutant le service Edge d’accès. Il peut contenir jusqu’à 256 caractères.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-p104">This name must be unique and cannot already exist as an allowed domain for this server running the Access Edge service. The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="4ea0d-p105">La recherche du nom de domaine du partenaire fédéré établit une correspondance à partir du suffixe. Par exemple, si vous tapez <STRONG>contoso.com</STRONG>, la recherche renverra également le domaine <STRONG>it.contoso.com</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-p105">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="4ea0d-125">Un domaine de partenaire fédéré ne peut pas être simultanément bloqué et autorisé.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-125">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="4ea0d-126">Lync Server 2013 empêche ce problème de se produire afin que vous n’ayez pas besoin de synchroniser vos listes.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-126">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="4ea0d-127">Si vous souhaitez restreindre l’accès pour ce domaine fédéré aux utilisateurs d’un serveur spécifique qui exécute le service Edge d’accès, dans **Service Edge d’accès (FQDN)**, tapez le nom de domaine complet du serveur de domaine fédéré exécutant le service Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-127">If you want to restrict access for this federated domain to users of a specific server running the Access Edge service, in **Access Edge service (FQDN)**, type the FQDN of the federated domain’s server running the Access Edge service.</span></span>
    
      - <span data-ttu-id="4ea0d-128">Si vous souhaitez fournir des informations supplémentaires, dans **Commentaire**, tapez les informations sur cette configuration que vous voulez partager avec les autres administrateurs système.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-128">If you want to provide additional information, in **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="4ea0d-129">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-129">Click **Commit**.</span></span>

7.  <span data-ttu-id="4ea0d-130">Répétez les étapes 4 à 6 pour chaque domaine de partenaire fédéré que vous souhaitez autoriser.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-130">Repeat steps 4 through 6 for each federated partner domain that you want to allow.</span></span>

<span data-ttu-id="4ea0d-131">Pour activer l’accès des utilisateurs fédérés, vous devez aussi activer la prise en charge de l’accès des utilisateurs fédérés dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-131">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="4ea0d-132">Pour plus d’informations, consultez la rubrique [activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4ea0d-132">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="4ea0d-133">De plus, vous devez configurer et appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à collaborer avec les utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="4ea0d-133">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="4ea0d-134">Pour plus d’informations, consultez la rubrique [configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4ea0d-134">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

