---
title: 'Lync Server 2013 : Création et vérification des enregistrements SRV DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="504a9-102">Création et vérification des enregistrements SRV DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="504a9-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="504a9-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="504a9-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="504a9-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="504a9-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="504a9-105">Cette rubrique décrit comment configurer les enregistrements DNS (Domain Name System) nécessaires à la création dans les déploiements Lync Server 2013 et ceux requis pour la connexion automatique du client.</span><span class="sxs-lookup"><span data-stu-id="504a9-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="504a9-106">Lorsque vous créez un pool frontal, le programme d’installation crée des objets et des paramètres Active Directory pour le pool, y compris le nom de domaine complet (FQDN) du pool.</span><span class="sxs-lookup"><span data-stu-id="504a9-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="504a9-107">Des objets et des paramètres similaires sont créés pour un serveur Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="504a9-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="504a9-108">Pour que les clients puissent se connecter au pool ou Standard Edition Server, le nom de domaine complet (FQDN) du pool ou du serveur Standard Edition doit être enregistré dans DNS.</span><span class="sxs-lookup"><span data-stu-id="504a9-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="504a9-109">Vous devez créer des enregistrements DNS SRV dans votre DNS interne pour chaque domaine SIP.</span><span class="sxs-lookup"><span data-stu-id="504a9-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="504a9-110">Cette procédure part du principe que votre DNS interne comporte des zones pour vos domaines d’utilisateur SIP.</span><span class="sxs-lookup"><span data-stu-id="504a9-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="504a9-111">Pour configurer un enregistrement SRV DNS</span><span class="sxs-lookup"><span data-stu-id="504a9-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="504a9-112">Sur le serveur DNS, cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="504a9-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="504a9-113">Dans l’arborescence de la console de votre domaine SIP, développez **zones de recherche directe**, puis cliquez avec le bouton droit sur le domaine SIP sur lequel Lync Server 2013 sera installé.</span><span class="sxs-lookup"><span data-stu-id="504a9-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="504a9-114">Cliquez sur **nouveaux enregistrements**.</span><span class="sxs-lookup"><span data-stu-id="504a9-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="504a9-115">Dans **Choisissez un type d’enregistrement de ressource**, cliquez sur **Emplacement du service (SRV)**, puis sur **Créer un enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="504a9-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="504a9-116">Cliquez sur **service**, puis tapez \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="504a9-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="504a9-117">Cliquez sur **protocole**, puis tapez \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="504a9-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="504a9-118">Cliquez sur **Numéro de port**, puis saisissez **5061**.</span><span class="sxs-lookup"><span data-stu-id="504a9-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="504a9-119">Cliquez sur **Hôte offrant ce service**, puis tapez le nom de domaine complet du pool ou du serveur en édition Standard.</span><span class="sxs-lookup"><span data-stu-id="504a9-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="504a9-120">Cliquez sur **OK**, puis sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="504a9-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="504a9-121">Pour vérifier la création d’un enregistrement SRV DNS</span><span class="sxs-lookup"><span data-stu-id="504a9-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="504a9-122">Ouvrez une session sur un ordinateur client du domaine dont le compte est membre du groupe Utilisateurs authentifiés ou qui dispose des autorisations équivalentes.</span><span class="sxs-lookup"><span data-stu-id="504a9-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="504a9-123">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="504a9-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="504a9-124">Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="504a9-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="504a9-125">À l’invite de commandes, tapez **nslookup**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="504a9-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="504a9-126">Tapez **Set type = SRV**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="504a9-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="504a9-127">Tapez \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="504a9-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="504a9-128">Le résultat affiché pour l’enregistrement TLS (Transport Layer Security) est le suivant:</span><span class="sxs-lookup"><span data-stu-id="504a9-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="504a9-129">Serveur: \<DNS server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="504a9-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="504a9-130">Adresse: \<adresse IP du serveur DNS\></span><span class="sxs-lookup"><span data-stu-id="504a9-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="504a9-131">Réponse ne faisant pas autorité:</span><span class="sxs-lookup"><span data-stu-id="504a9-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="504a9-132">\_sipinternaltls. \_emplacement du service SRV TCP.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="504a9-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="504a9-133">Priority = 0</span><span class="sxs-lookup"><span data-stu-id="504a9-133">priority = 0</span></span>
    
    <span data-ttu-id="504a9-134">épaisseur = 0</span><span class="sxs-lookup"><span data-stu-id="504a9-134">weight = 0</span></span>
    
    <span data-ttu-id="504a9-135">port = 5061</span><span class="sxs-lookup"><span data-stu-id="504a9-135">port = 5061</span></span>
    
    <span data-ttu-id="504a9-136">SVR nom d’hôte = poolname.contoso.com (ou enregistrement d’un serveur Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="504a9-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="504a9-137">poolname.contoso.com adresse Internet = \<adresse IP virtuelle de l’équilibrage de charge\> ou \<de l’adresse IP d’un serveur Enterprise Edition pour les pools avec un seul\> serveur \<Enterprise Edition ou une adresse IP du standard Serveur édition\></span><span class="sxs-lookup"><span data-stu-id="504a9-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="504a9-138">Lorsque vous avez terminé, à l’invite de commandes, tapez **Exit**, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="504a9-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="504a9-139">Pour vérifier que le nom de domaine complet (FQDN) du pool frontal ou du serveur Standard Edition peut être résolu</span><span class="sxs-lookup"><span data-stu-id="504a9-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="504a9-140">Connectez-vous à un ordinateur client dans le domaine.</span><span class="sxs-lookup"><span data-stu-id="504a9-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="504a9-141">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="504a9-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="504a9-142">Dans la zone **ouvrir** , tapez **cmd**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="504a9-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="504a9-143">À l’invite de commandes, tapez **nslookup** \<FQDN du pool\> frontal ou \<du FQDN du serveur\>Standard Edition, puis appuyez sur entrée.</span><span class="sxs-lookup"><span data-stu-id="504a9-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="504a9-144">Vérifiez que vous recevez une réponse qui est résolue en adresse IP appropriée pour le nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="504a9-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

