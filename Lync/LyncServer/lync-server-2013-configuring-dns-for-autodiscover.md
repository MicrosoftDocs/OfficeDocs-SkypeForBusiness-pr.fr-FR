---
title: 'Lync Server 2013 : configuration du DNS pour la découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cf81cd82655a37ad089d915e9e3799671025bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="4439f-102">Configuration de DNS pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4439f-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4439f-103">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="4439f-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="4439f-104">Pour prendre en charge la découverte automatique pour les clients Lync, vous devez créer les enregistrements DNS suivants :</span><span class="sxs-lookup"><span data-stu-id="4439f-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="4439f-105">Un enregistrement DNS interne pour la prise en charge des clients Lync qui se connectent au sein du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4439f-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="4439f-106">Enregistrement DNS externe ou public permettant de prendre en charge les clients Lync qui se connectent à partir d’Internet</span><span class="sxs-lookup"><span data-stu-id="4439f-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="4439f-107">Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="4439f-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="4439f-108">Les enregistrements DNS peuvent être des enregistrements CNAMe ou CNAMe, en fonction de votre capacité à créer des certificats avec le nouveau nom d’objet.</span><span class="sxs-lookup"><span data-stu-id="4439f-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="4439f-109">Si vous n’êtes pas en mesure de demander et de déployer un nouveau certificat externe (public) avec le lyncdiscover. \<réseau de\> noms de domaine, utilisez la procédure d’utilisation du port 80 http/TCP.</span><span class="sxs-lookup"><span data-stu-id="4439f-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="4439f-110">Les procédures suivantes décrivent la création d’enregistrements DNS internes et externes.</span><span class="sxs-lookup"><span data-stu-id="4439f-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="4439f-111">Pour créer des enregistrements CNAMe DNS</span><span class="sxs-lookup"><span data-stu-id="4439f-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="4439f-112">Connectez-vous à un serveur DNS comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="4439f-113">Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS de votre réseau en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="4439f-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="4439f-114">Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public.</span><span class="sxs-lookup"><span data-stu-id="4439f-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="4439f-115">Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4439f-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="4439f-116">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4439f-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="4439f-117">Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez la **zone de recherche directe** pour votre domaine Active Directory (par exemple, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4439f-118">Ce domaine est le domaine Active Directory dans lequel votre pool de&nbsp;directeurs Lync Server 2013 et votre pool frontal sont installés.</span><span class="sxs-lookup"><span data-stu-id="4439f-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="4439f-119">Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="4439f-120">Vérifiez qu’un enregistrement A existe pour votre pool de directeurs comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="4439f-121">Dans le cas d’un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet (FQDN) des services Web internes pour votre pool de répertoires (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="4439f-122">Dans le cas d’un enregistrement DNS externe, un enregistrement de l’hôte A doit exister pour le nom de domaine complet des services Web externes de votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="4439f-123">Vérifiez qu’un enregistrement A existe pour votre pool frontal comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="4439f-124">Dans le cas d’un enregistrement DNS interne, un enregistrement A doit exister pour le nom de domaine complet des services Web internes de votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="4439f-125">Dans le cas d’un enregistrement DNS externe, un enregistrement de l’hôte A doit exister pour le nom de domaine complet des services Web externes de votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="4439f-126">Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4439f-127">Si vous créez un enregistrement DNS externe, les <STRONG>zones de recherche directe</STRONG> sont déjà développées pour votre domaine SIP à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="4439f-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="4439f-128">Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="4439f-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="4439f-129">Dans **nom**de l’alias, tapez l’une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="4439f-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="4439f-130">Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="4439f-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="4439f-131">Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="4439f-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="4439f-132">Dans **nom de domaine complet (FQDN) de l’hôte cible**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4439f-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="4439f-133">Pour un enregistrement DNS interne, tapez ou accédez au nom de domaine complet des services Web internes de votre pool de réalisateurs (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4439f-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="4439f-134">Pour un enregistrement DNS externe, tapez ou accédez au nom de domaine complet des services Web externes de votre pool de réalisateurs (par exemple, lyncwebextdir.contoso.com), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4439f-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4439f-135">Si vous n’utilisez pas de réalisateur, utilisez le nom de domaine complet (FQDN) de services Web interne et externe pour le pool frontal, ou, pour un serveur unique, le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4439f-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4439f-136">Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4439f-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="4439f-137">Pour créer des enregistrements DNS A</span><span class="sxs-lookup"><span data-stu-id="4439f-137">To create DNS A records</span></span>

1.  <span data-ttu-id="4439f-138">Connectez-vous à un serveur DNS comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="4439f-139">Pour créer un enregistrement DNS interne, connectez-vous à un serveur DNS de votre réseau en tant que membre du groupe Domain Admins ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="4439f-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="4439f-140">Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public ou votre serveur DNS externe.</span><span class="sxs-lookup"><span data-stu-id="4439f-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="4439f-141">Ouvrez le composant logiciel enfichable d’administration DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="4439f-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="4439f-142">Effectuez l’une des actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4439f-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="4439f-143">Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez la **zone de recherche directe** pour votre domaine Active Directory (par exemple, contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4439f-144">Ce domaine est le domaine Active Directory dans lequel votre pool de&nbsp;directeurs Lync Server 2013 et votre pool frontal sont installés.</span><span class="sxs-lookup"><span data-stu-id="4439f-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="4439f-145">Dans le cas d’un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="4439f-146">Vérifiez qu’un enregistrement hôte A (pour IPv6, AAAA) existe pour votre pool de réalisateurs comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="4439f-147">Dans le cas d’un enregistrement DNS interne, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet (FQDN) des services Web internes de votre pool de directeurs (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="4439f-148">Dans le cas d’un enregistrement DNS externe, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web externes de votre pool de directeurs (par exemple, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="4439f-149">Vérifiez qu’un enregistrement A (pour IPv6, AAAA) existe pour le pool frontal comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="4439f-150">Dans le cas d’un enregistrement DNS interne, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web internes de votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="4439f-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="4439f-151">Dans le cas d’un enregistrement DNS externe, un enregistrement hôte A (pour IPv6, AAAA) doit exister pour le nom de domaine complet des services Web externes de votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="4439f-152">Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **zones de recherche directe** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4439f-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4439f-153">Si vous créez un enregistrement DNS externe, les <STRONG>zones de recherche directe</STRONG> sont déjà développées pour votre domaine SIP à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="4439f-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="4439f-154">Cliquez avec le bouton droit sur le nom de domaine SIP, puis cliquez sur **nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="4439f-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="4439f-155">Dans **nom**, tapez le nom d’hôte comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="4439f-156">Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte de l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="4439f-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="4439f-157">Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte de l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="4439f-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4439f-158">Le nom de domaine est supposé à partir de la zone dans laquelle l’enregistrement est défini et, par conséquent, n’a pas besoin d’être entré dans le cadre de l’enregistrement A.</span><span class="sxs-lookup"><span data-stu-id="4439f-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="4439f-159">Dans **adresse IP**, tapez l’adresse IP comme suit :</span><span class="sxs-lookup"><span data-stu-id="4439f-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="4439f-160">Dans le cas d’un enregistrement DNS interne, tapez l’adresse IP de services Web internes du directeur (ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP virtuelle de l’équilibreur de charge).</span><span class="sxs-lookup"><span data-stu-id="4439f-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="4439f-161">Si vous n’utilisez pas de réalisateur, tapez l’adresse IP du serveur frontal ou du serveur Standard Edition, ou, si vous utilisez un équilibreur de charge, tapez l’adresse IP du serveur principal de chargement.</span><span class="sxs-lookup"><span data-stu-id="4439f-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="4439f-162">Pour un enregistrement DNS externe, tapez l’adresse IP externe ou publique du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="4439f-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="4439f-163">Cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="4439f-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="4439f-164">Pour créer un enregistrement A supplémentaires, répétez les étapes 8 à 10.</span><span class="sxs-lookup"><span data-stu-id="4439f-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4439f-165">Vous devez créer un nouveau lyncdiscover et lyncdiscoverinternal A enregistrements dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4439f-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="4439f-166">Lorsque vous avez terminé de créer un (pour les enregistrements IPv6, AAAA), cliquez sur **terminé**.</span><span class="sxs-lookup"><span data-stu-id="4439f-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

