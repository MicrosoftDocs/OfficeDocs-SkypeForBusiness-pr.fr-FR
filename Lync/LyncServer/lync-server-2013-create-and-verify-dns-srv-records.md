---
title: 'Lync Server 2013 : création et vérification des enregistrements SRV DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="c74ab-102">Créer et vérifier des enregistrements SRV DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c74ab-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c74ab-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c74ab-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c74ab-104">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="c74ab-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="c74ab-105">Cette rubrique décrit comment configurer les enregistrements DNS (Domain Name System) que vous devez créer dans les déploiements de Lync Server 2013 et ceux requis pour la connexion automatique des clients.</span><span class="sxs-lookup"><span data-stu-id="c74ab-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="c74ab-106">Lorsque vous créez un pool frontal, le programme d’installation crée des objets et des paramètres Active Directory pour le pool, y compris le nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="c74ab-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c74ab-107">Des objets et des paramètres similaires sont créés pour un serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c74ab-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="c74ab-108">Pour que les clients puissent se connecter au pool ou au serveur Standard Edition, le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition doit être enregistré dans le système DNS.</span><span class="sxs-lookup"><span data-stu-id="c74ab-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="c74ab-109">Vous devez créer des enregistrements SRV DNS dans votre serveur DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="c74ab-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="c74ab-110">Cela présuppose que votre serveur DNS interne comporte des zones pour vos domaines utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="c74ab-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="c74ab-111">Pour configurer un enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="c74ab-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="c74ab-112">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="c74ab-113">Dans l’arborescence de la console pour votre domaine SIP, développez **zones de recherche directes**, puis cliquez avec le bouton droit sur le domaine SIP dans lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="c74ab-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="c74ab-114">Cliquez sur **Nouveaux enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="c74ab-115">Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="c74ab-116">Cliquez sur **service**, puis tapez \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="c74ab-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="c74ab-117">Cliquez sur **protocole**, puis tapez \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="c74ab-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="c74ab-118">Cliquez sur **Numéro de port**, puis tapez **5061**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="c74ab-119">Cliquez sur **hôte offrant ce service**, puis tapez le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c74ab-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="c74ab-120">Cliquez sur **OK**, puis sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="c74ab-121">Pour vérifier la création d’un enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="c74ab-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="c74ab-122">Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="c74ab-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="c74ab-123">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="c74ab-124">Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="c74ab-125">À l’invite de commandes, tapez **nslookup**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="c74ab-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="c74ab-126">Tapez **set type=srv**, puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="c74ab-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="c74ab-127">Tapez \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="c74ab-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="c74ab-128">Le résultat obtenu pour l’enregistrement TLS (Transport Layer Security, sécurité de la couche de transport) est le suivant :</span><span class="sxs-lookup"><span data-stu-id="c74ab-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="c74ab-129">Serveur : \<DNS server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="c74ab-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="c74ab-130">Adresse : \<adresse IP du serveur DNS\></span><span class="sxs-lookup"><span data-stu-id="c74ab-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="c74ab-131">Réponse ne faisant pas autorité :</span><span class="sxs-lookup"><span data-stu-id="c74ab-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="c74ab-132">\_sipinternaltls. \_emplacement du service SRV TCP.contoso.com :</span><span class="sxs-lookup"><span data-stu-id="c74ab-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="c74ab-133">priorité = 0</span><span class="sxs-lookup"><span data-stu-id="c74ab-133">priority = 0</span></span>
    
    <span data-ttu-id="c74ab-134">poids = 0</span><span class="sxs-lookup"><span data-stu-id="c74ab-134">weight = 0</span></span>
    
    <span data-ttu-id="c74ab-135">port = 5061</span><span class="sxs-lookup"><span data-stu-id="c74ab-135">port = 5061</span></span>
    
    <span data-ttu-id="c74ab-136">nom de l’hôte : poolname.contoso.com (ou enregistrement A du serveur Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="c74ab-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="c74ab-137">adresse Internet poolname.contoso.com = \<adresse IP virtuelle de l’équilibreur de\> charge \<ou adresse IP d’un serveur Enterprise Edition unique pour les pools avec un seul\> serveur \<Enterprise Edition ou adresse IP du serveur Standard Edition\></span><span class="sxs-lookup"><span data-stu-id="c74ab-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="c74ab-138">Lorsque vous avez terminé, à l’invite de commandes, tapez **exit** et appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="c74ab-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="c74ab-139">Pour vérifier que le nom de domaine complet du pool frontal ou du serveur Standard Edition peut être résolu</span><span class="sxs-lookup"><span data-stu-id="c74ab-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="c74ab-140">Ouvrez une session sur un ordinateur client du domaine.</span><span class="sxs-lookup"><span data-stu-id="c74ab-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="c74ab-141">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="c74ab-142">Dans la zone **Ouvrir**, tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c74ab-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="c74ab-143">À l’invite de commandes, tapez **nslookup** \<nom de domaine complet du\> pool \<frontal ou du nom de domaine\>complet du serveur Standard Edition, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="c74ab-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="c74ab-144">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet.</span><span class="sxs-lookup"><span data-stu-id="c74ab-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

