---
title: 'Lync Server 2013 : création d’enregistrements DNS pour le service de découverte automatique'
description: 'Lync Server 2013 : création d’enregistrements DNS pour le service de découverte automatique.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563100"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="3a749-103">Création d’enregistrements DNS pour le service de découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a749-103">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a749-104">_**Dernière modification de la rubrique :** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="3a749-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="3a749-105">Vos utilisateurs de Lync mobile auront besoin d’activer la découverte automatique, qui implique la création de certains enregistrements DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="3a749-105">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="3a749-106">En fonction de vos besoins, vous avez besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="3a749-106">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="3a749-107">Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="3a749-107">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="3a749-108">Un enregistrement DNS externe ou public pour prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet</span><span class="sxs-lookup"><span data-stu-id="3a749-108">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="3a749-109">Pourquoi ?</span><span class="sxs-lookup"><span data-stu-id="3a749-109">Why both?</span></span> <span data-ttu-id="3a749-110">Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="3a749-110">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="3a749-111">Les enregistrements DNS que vous créez peuvent être des enregistrements A (hôte) ou CNAMe.</span><span class="sxs-lookup"><span data-stu-id="3a749-111">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="3a749-112">Pour vous aider, consultez la rubrique relative à la création de ces enregistrements DNS internes et externes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3a749-112">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="3a749-113">Si vous devez effectuer des lectures supplémentaires sur les exigences DNS pour les utilisateurs mobiles, vous pouvez consulter la [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="3a749-113">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="3a749-114">Création d’un enregistrement CNAMe DNS interne</span><span class="sxs-lookup"><span data-stu-id="3a749-114">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="3a749-115">Pour créer un enregistrement DNS interne, vous devez vous connecter à un serveur DNS de votre réseau à l’aide d’un compte de domaine membre du groupe administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="3a749-115">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="3a749-116">Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3a749-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="3a749-117">Dans l’arborescence de la console du serveur DNS, développez **zones de recherche directes** pour le domaine Active Directory dans lequel votre pool de directeurs et votre pool frontal Lync Server 2013 sont installés.</span><span class="sxs-lookup"><span data-stu-id="3a749-117">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="3a749-118">(par exemple, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3a749-118">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="3a749-119">Vérifier s’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de directeurs pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3a749-119">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="3a749-120">Si ce n’est pas le cas, il est possible que vous n’utilisiez pas un pool directeur et que vous devez utiliser le nom de domaine complet (FQDN) de votre pool frontal ou même un nom de domaine complet (FQDN) de serveur unique, si c’est votre configuration.</span><span class="sxs-lookup"><span data-stu-id="3a749-120">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="3a749-121">À l’esprit, vérifiez si un enregistrement A (AAAA pour IPv6) hôte existe pour votre pool frontal pour un enregistrement DNS interne, il doit exister un enregistrement A (ou AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3a749-121">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="3a749-122">Si ce n’est pas le cas, vous devez noter le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a749-122">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="3a749-123">Une fois que vous connaissez les enregistrements A (ou AAAA) de l’hôte, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3a749-123">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="3a749-124">Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="3a749-124">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="3a749-125">Dans **nom**de l’alias, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="3a749-125">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="3a749-126">Dans **nom de domaine complet (FQDN) pour l’hôte de destination**, tapez ou naviguez jusqu’au nom de domaine complet des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a749-126">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="3a749-127">Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a749-127">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="3a749-128">Création d’un enregistrement CNAMe DNS externe</span><span class="sxs-lookup"><span data-stu-id="3a749-128">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="3a749-129">Pour créer un enregistrement CNAMe DNS externe, vous devez vous connecter à votre fournisseur DNS public, puis suivre nos étapes.</span><span class="sxs-lookup"><span data-stu-id="3a749-129">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="3a749-130">Nous ne pouvons pas décrire exactement où vous allez dans l’environnement de votre fournisseur DNS car il peut y avoir différentes façons de gérer votre DNS externe, mais nous espérons que ces étapes seront utiles.</span><span class="sxs-lookup"><span data-stu-id="3a749-130">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="3a749-131">Connectez-vous à votre fournisseur DNS externe à l’aide d’un compte qui peut créer des enregistrements DNS dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="3a749-131">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="3a749-132">Un domaine SIP doit déjà être créé pour cet environnement.</span><span class="sxs-lookup"><span data-stu-id="3a749-132">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="3a749-133">Développez la **zone de recherche directe** pour ce domaine SIP, ou sélectionnez-la en fonction de l’interface DNS externe utilisée.</span><span class="sxs-lookup"><span data-stu-id="3a749-133">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="3a749-134">Vous devriez déjà voir un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool directeur (par exemple, lyncwebexdir01.contoso.com), vous devez donc confirmer qu’il s’agit bien.</span><span class="sxs-lookup"><span data-stu-id="3a749-134">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="3a749-135">Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3a749-135">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="3a749-136">Si c’est le cas, vous devez utiliser le nom de domaine complet de votre pool frontal, ou si vous effectuez cette opération pour un serveur unique, pour votre serveur Front-End ou votre serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a749-136">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="3a749-137">Vous devrez également vérifier qu’il existe un enregistrement A (AAAA pour IPv6) hôte pour votre nom de domaine complet (FQDN) des services Web externes pour votre pool frontal (tel que lyncwebextpool01.contoso.com) ou un nom de domaine complet pour votre nom de domaine complet (FQDN) de serveur unique si vous n’avez pas de pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3a749-137">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="3a749-138">Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous n’avez pas de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3a749-138">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="3a749-139">À présent, dans le format approprié pour votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **Nouvel alias (CNAME)** (il peut s’agir d’une option de menu ou d’un lien, selon le format du fournisseur DNS).</span><span class="sxs-lookup"><span data-stu-id="3a749-139">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="3a749-140">Il doit y avoir une forme de zone de texte **nom d’alias** comme avec le DNS interne, vous devez entrer lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="3a749-140">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="3a749-141">Il doit également exister une forme de zone de texte **nom de domaine complet (FQDN) pour l’hôte cible** , où vous devez entrer le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebexdir01.contoso.com), puis cliquer sur OK ou exécuter toute action dans le DNS externe pour accepter la création de cette entrée.</span><span class="sxs-lookup"><span data-stu-id="3a749-141">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="3a749-142">Comme indiqué à l’étape 4 ci-dessus, si vous n’avez pas de pool Directeur, vous devez utiliser le nom de domaine complet du pool frontal ou le nom de domaine complet du serveur unique que vous avez configuré, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="3a749-142">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="3a749-143">Vous devrez créer un nouvel enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3a749-143">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="3a749-144">Création d’un enregistrement DNS A interne</span><span class="sxs-lookup"><span data-stu-id="3a749-144">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="3a749-145">Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau à l’aide d’un compte de domaine membre du groupe administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="3a749-145">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="3a749-146">Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="3a749-146">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="3a749-147">Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso. local) où le pool de directeurs et les pools frontaux Lync Server 2013 sont installés.</span><span class="sxs-lookup"><span data-stu-id="3a749-147">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="3a749-148">Vérifier s’il existe un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool de directeurs pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3a749-148">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="3a749-149">Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur et que vous deviez utiliser l’adresse IP de votre pool frontal ou même une adresse IP de serveur unique, si c’est votre configuration.</span><span class="sxs-lookup"><span data-stu-id="3a749-149">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="3a749-150">À l’esprit, vérifiez si un enregistrement A (AAAA pour IPv6) hôte existe pour votre pool frontal pour un enregistrement DNS interne, il doit exister un enregistrement A (ou AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="3a749-150">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="3a749-151">Si ce n’est pas le cas, vous devez prendre note de l’adresse IP pour le serveur frontal ou le serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a749-151">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="3a749-152">Une fois que vous connaissez les enregistrements A (ou AAAA) de l’hôte, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3a749-152">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="3a749-153">Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="3a749-153">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="3a749-154">Dans **nom**, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="3a749-154">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="3a749-155">Dans **adresse IP**, tapez l’adresse IP interne des services Web du directeur (ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP virtuelle de l’équilibreur de charge du directeur).</span><span class="sxs-lookup"><span data-stu-id="3a749-155">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="3a749-156">Comme indiqué à l’étape 4 ci-dessus, si vous n’utilisez pas de directeur, vous devrez peut-être entrer l’adresse IP du serveur frontal ou du serveur Standard Edition ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP du programme d’équilibrage de la charge du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3a749-156">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="3a749-157">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a749-157">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="3a749-158">Pour créer un enregistrement A ou AAAA supplémentaire, répétez les étapes 8 à 10, en gardant à l’esprit que vous devrez créer des enregistrements de découverte automatique A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a749-158">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="3a749-159">Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="3a749-159">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="3a749-160">Création d’un enregistrement DNS A externe</span><span class="sxs-lookup"><span data-stu-id="3a749-160">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="3a749-161">Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public, puis suivez les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="3a749-161">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="3a749-162">Nous ne pouvons pas décrire exactement où vous allez dans l’environnement de votre fournisseur DNS car il peut y avoir différentes façons de gérer votre DNS externe, mais nous espérons que ces étapes seront utiles.</span><span class="sxs-lookup"><span data-stu-id="3a749-162">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="3a749-163">Vous devez être connecté en tant que compte pouvant créer des enregistrements DNS dans cet environnement.</span><span class="sxs-lookup"><span data-stu-id="3a749-163">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="3a749-164">Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3a749-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="3a749-165">Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3a749-165">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="3a749-166">Vous devriez déjà voir un enregistrement A (AAAA pour IPv6) d’hôte pour votre pool directeur (tel que lyncwebexdir01.contoso.com), vérifiez qu’il s’agit du point de vue et de l’adresse IP.</span><span class="sxs-lookup"><span data-stu-id="3a749-166">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="3a749-167">Si ce n’est pas le cas, il se peut que vous n’utilisiez pas de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3a749-167">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="3a749-168">Si c’est le cas, vous devez utiliser l’adresse IP de votre pool frontal, ou si vous effectuez cette opération pour un serveur unique, pour votre serveur Front-End ou votre serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="3a749-168">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="3a749-169">Gardez à l’esprit que vos serveurs peuvent également être derrière un équilibrage de charge ou utiliser un proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="3a749-169">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="3a749-170">Prenez note des adresses IP pour suivre les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="3a749-170">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="3a749-171">Vous devrez également vérifier qu’il existe un enregistrement A (AAAA pour IPv6) hôte pour votre nom de domaine complet (FQDN) des services Web externes pour votre pool frontal (tel que lyncwebextpool01.contoso.com) ou une adresse IP pour votre installation Lync à serveur unique si vous n’avez pas de pool frontal.</span><span class="sxs-lookup"><span data-stu-id="3a749-171">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="3a749-172">Comme indiqué à l’étape précédente, vous en aurez besoin ci-dessous si vous n’avez pas de pool directeur.</span><span class="sxs-lookup"><span data-stu-id="3a749-172">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="3a749-173">À présent, dans le format approprié pour votre fournisseur DNS externe, sélectionnez l’option permettant de créer un **nouvel hôte a ou AAAA** (il peut s’agir d’une option de menu ou d’un lien, selon le format du fournisseur DNS).</span><span class="sxs-lookup"><span data-stu-id="3a749-173">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="3a749-174">Vous devez entrer un **nom**, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="3a749-174">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="3a749-175">Il doit également exister une zone de texte **adresse IP** , où vous devez entrer l’adresse IP de votre pool de directeurs (par exemple, lyncwebexdir01.contoso.com) ou éventuellement l’adresse IP de l’équilibreur de charge de votre pool (ou une adresse IP de proxy inverse qui conduit au même), puis cliquer sur OK ou prendre l’une des mesures dans le DNS externe pour accepter la création de cette entrée.</span><span class="sxs-lookup"><span data-stu-id="3a749-175">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="3a749-176">Comme indiqué à l’étape 4 ci-dessus, si vous n’avez pas de pool Directeur, vous devrez utiliser l’adresse IP du pool frontal ou l’adresse IP à serveur unique que vous avez configurée, selon le cas.</span><span class="sxs-lookup"><span data-stu-id="3a749-176">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="3a749-177">Vous devrez créer un nouvel enregistrement Autodiscover A ou AAAA dans la zone de recherche directe de chaque domaine SIP pris en charge dans votre environnement Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="3a749-177">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

