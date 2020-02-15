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
ms.openlocfilehash: 7f84e07deea6540370d8358683b474e14d767046
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="bfd9d-102">Configuration de DNS pour la découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfd9d-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfd9d-103">_**Dernière modification de la rubrique :** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="bfd9d-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="bfd9d-104">Pour prendre en charge la découverte automatique pour les clients Lync, vous devez créer les enregistrements DNS (Domain Name System) suivants :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="bfd9d-105">Un enregistrement DNS interne pour prendre en charge les clients Lync qui se connectent à partir du réseau de votre organisation ;</span><span class="sxs-lookup"><span data-stu-id="bfd9d-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="bfd9d-106">Un enregistrement DNS externe ou public pour prendre en charge les clients Lync qui se connectent à partir d’Internet</span><span class="sxs-lookup"><span data-stu-id="bfd9d-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="bfd9d-107">Vous devez créer un enregistrement DNS interne et un enregistrement DNS externe pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="bfd9d-108">Les enregistrements DNS peuvent être des enregistrements A (hôte) ou CNAMe, en fonction de votre capacité à créer des certificats avec l’autre nom de l’objet (SAN).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="bfd9d-109">Si vous n’êtes pas en mesure de demander et de déployer un nouveau certificat externe (public) avec le lyncdiscover. \<nom\> de domaine San, utilisez la procédure d’utilisation du port http/TCP 80.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\> SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="bfd9d-110">Les procédures suivantes décrivent comment créer des enregistrements DNS internes et externes.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-110">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="bfd9d-111">Pour créer des enregistrements CNAME DNS</span><span class="sxs-lookup"><span data-stu-id="bfd9d-111">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="bfd9d-112">Ouvrez une session sur un serveur DNS comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-112">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-113">Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-113">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="bfd9d-114">Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-114">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="bfd9d-115">Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-115">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="bfd9d-116">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-116">Do one of the following:</span></span>
    
      - <span data-ttu-id="bfd9d-117">Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-117">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bfd9d-118">Ce domaine est le domaine Active Directory dans lequel votre pool directeur&nbsp;et votre pool frontal Lync Server 2013 sont installés.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-118">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="bfd9d-119">Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-119">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="bfd9d-120">Vérifiez qu’un enregistrement hôte A existe pour votre pool Directeur, comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-120">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-121">Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-121">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="bfd9d-122">Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-122">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="bfd9d-123">Vérifiez qu’il existe un enregistrement A d’hôte pour votre pool frontal comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-123">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-124">Pour un enregistrement DNS interne, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-124">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="bfd9d-125">Pour un enregistrement DNS externe, il doit exister un enregistrement A d’hôte pour le nom de domaine complet des services Web externes pour votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-125">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="bfd9d-126">Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-126">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfd9d-127">Si vous créez un enregistrement DNS externe, <STRONG>Zones de recherche directes</STRONG> est déjà développé pour votre domaine SIP (suite à l’étape 3).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-127">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="bfd9d-128">Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-128">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="bfd9d-129">Dans **Nom de l’alias**, tapez l’un des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-129">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="bfd9d-130">Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-130">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="bfd9d-131">Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-131">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="bfd9d-132">Dans **Nom de domaine complet (FQDN) pour l’hôte de destination**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-132">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="bfd9d-133">Pour un enregistrement DNS interne, tapez ou recherchez le nom de domaine complet (FQDN) des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-133">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="bfd9d-134">Pour un enregistrement DNS externe, tapez ou recherchez le nom de domaine complet (FQDN) des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com), puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-134">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfd9d-135">Si vous n’utilisez pas de directeur, utilisez le nom de domaine complet des services Web internes et externes pour le pool frontal ou, pour un serveur unique, le nom de domaine complet (FQDN) du serveur frontal ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-135">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bfd9d-136">Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-136">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="bfd9d-137">Pour créer des enregistrements A DNS</span><span class="sxs-lookup"><span data-stu-id="bfd9d-137">To create DNS A records</span></span>

1.  <span data-ttu-id="bfd9d-138">Ouvrez une session sur un serveur DNS comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-138">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-139">Pour créer un enregistrement DNS interne, ouvrez une session sur un serveur DNS de votre réseau en tant que membre du groupe Administrateurs du domaine ou DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-139">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="bfd9d-140">Pour créer un enregistrement DNS externe, connectez-vous à votre fournisseur DNS public ou à votre serveur DNS externe.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-140">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="bfd9d-141">Ouvrez le composant logiciel enfichable DNS : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-141">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="bfd9d-142">Effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-142">Do one of the following:</span></span>
    
      - <span data-ttu-id="bfd9d-143">Pour un enregistrement DNS interne, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine Active Directory (par exemple, contoso.local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-143">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bfd9d-144">Ce domaine est le domaine Active Directory dans lequel votre pool directeur&nbsp;et votre pool frontal Lync Server 2013 sont installés.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-144">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="bfd9d-145">Pour un enregistrement DNS externe, dans l’arborescence de la console du serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-145">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="bfd9d-146">Vérifiez qu’il existe un enregistrement A (pour IPv6, AAAA) hôte pour votre pool Directeur, comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-146">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-147">Pour un enregistrement DNS interne, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool directeur (par exemple, lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-147">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="bfd9d-148">Pour un enregistrement DNS externe, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web externes pour votre pool directeur (par exemple, lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-148">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="bfd9d-149">Vérifiez qu’il existe un enregistrement A (pour IPv6, AAAA) hôte pour votre pool frontal comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-149">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-150">Pour un enregistrement DNS interne, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web internes pour votre pool frontal (par exemple, lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-150">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="bfd9d-151">Pour un enregistrement DNS externe, il doit exister un enregistrement A (pour IPv6, AAAA) hôte pour le nom de domaine complet des services Web externes pour votre pool frontal (par exemple, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-151">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="bfd9d-152">Pour un enregistrement DNS interne, dans l’arborescence de la console de votre serveur DNS, développez **Zones de recherche directes** pour votre domaine SIP (par exemple, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-152">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfd9d-153">Si vous créez un enregistrement DNS externe, <STRONG>Zones de recherche directes</STRONG> est déjà développé pour votre domaine SIP (suite à l’étape 3).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-153">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="bfd9d-154">Cliquez avec le bouton droit sur le nom du domaine SIP, puis cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-154">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="bfd9d-155">Dans **Nom**, tapez le nom d’hôte comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-155">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-156">Pour un enregistrement DNS interne, tapez lyncdiscoverinternal comme nom d’hôte pour l’URL du service de découverte automatique interne.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-156">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="bfd9d-157">Pour un enregistrement DNS externe, tapez lyncdiscover comme nom d’hôte pour l’URL du service de découverte automatique externe.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-157">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfd9d-158">Le nom de domaine est déduit d’après la zone dans laquelle l’enregistrement est défini ; il est par conséquent inutile de l’entrer dans le cadre de l’enregistrement A.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-158">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="bfd9d-159">Dans **Adresse IP**, tapez l’adresse IP comme suit :</span><span class="sxs-lookup"><span data-stu-id="bfd9d-159">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="bfd9d-160">Pour un enregistrement DNS interne, tapez l’adresse IP interne des services Web du directeur (ou, si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP virtuelle de l’équilibreur de charge du directeur).</span><span class="sxs-lookup"><span data-stu-id="bfd9d-160">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bfd9d-161">Si vous n’utilisez pas de directeur, tapez l’adresse IP du serveur frontal ou du serveur Standard Edition, ou si vous utilisez un programme d’équilibrage de la charge, tapez l’adresse IP du programme d’équilibrage de la charge du pool frontal.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-161">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="bfd9d-162">Pour un enregistrement DNS externe, tapez l’adresse IP externe ou publique du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-162">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="bfd9d-163">Cliquez sur **Ajouter un hôte**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-163">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="bfd9d-164">Pour créer un enregistrement A supplémentaire, répétez les étapes 8 à 10.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-164">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bfd9d-165">Vous devez créer un nouveau lyncdiscover et lyncdiscoverinternal des enregistrements A dans la zone de recherche directe de chaque domaine SIP que vous prenez en charge dans votre environnement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-165">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="bfd9d-166">Lorsque vous avez terminé de créer des enregistrements A (AAAA pour IPv6), cliquez sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="bfd9d-166">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

