---
title: 'Lync Server 2013 : Configuration du DNS pour l’équilibrage de charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="88a3c-102">Configuration du DNS pour l’équilibrage de charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a3c-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88a3c-103">_**Dernière modification de la rubrique:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="88a3c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="88a3c-104">Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe administrateurs de domaine ou membre du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="88a3c-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="88a3c-105">L’équilibrage de charge DNS (Domain Name System) équilibre le trafic réseau unique vers Lync Server 2013, comme le trafic SIP et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="88a3c-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="88a3c-106">L’équilibrage de charge DNS est pris en charge pour les listes frontales, les pools de périphériques, les pools de directeurs et les pools de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="88a3c-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="88a3c-107">Un pool configuré pour utiliser l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) définis: le nom de domaine complet (FQDN) du pool standard utilisé par l’équilibrage de charge DNS (par exemple, pool1.contoso.com) et résolu vers l’IPs physique des serveurs du pool. et un autre nom de domaine complet (par exemple, web1.contoso.net) pour les services Web du pool, qui est résolu sur l’adresse IP virtuelle du pool.</span><span class="sxs-lookup"><span data-stu-id="88a3c-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="88a3c-108">Pour plus d’informations sur l’équilibrage de charge DNS, voir [équilibrage de charge DNS dans Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="88a3c-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88a3c-109">L’équilibrage de charge matérielle est toujours requis pour le trafic du client vers le serveur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="88a3c-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="88a3c-110">Pour pouvoir utiliser l’équilibrage de charge DNS, vous devez procéder comme suit:</span><span class="sxs-lookup"><span data-stu-id="88a3c-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="88a3c-111">Remplacez le nom de domaine complet (FQDN) du pool de services Web interne.</span><span class="sxs-lookup"><span data-stu-id="88a3c-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="88a3c-112">Si vous décidez de remplacer les services Web internes par un nom de domaine complet autonome, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool de réalisateur.</span><span class="sxs-lookup"><span data-stu-id="88a3c-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="88a3c-113">Créer des enregistrements DNS A pour résoudre le nom de domaine complet (FQDN) du pool en adresses IP de tous les serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="88a3c-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="88a3c-114">Activez la randomisation des adresses IP ou, pour le DNS de Windows Server, activez la répétition alternée.</span><span class="sxs-lookup"><span data-stu-id="88a3c-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="88a3c-115">La répétition alternée doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="88a3c-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="88a3c-116">Pour ignorer le nom de domaine complet des services Web internes</span><span class="sxs-lookup"><span data-stu-id="88a3c-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="88a3c-117">Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="88a3c-118">Dans l’arborescence de la console, développez le nœud Pools front end Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="88a3c-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="88a3c-119">Cliquez avec le bouton droit sur la liste, cliquez sur **modifier les propriétés**, puis cliquez sur **services Web**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="88a3c-120">Sous les **services Web internes**, activez la case à cocher **remplacer le FQDN** .</span><span class="sxs-lookup"><span data-stu-id="88a3c-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="88a3c-121">Tapez le nom de domaine complet (FQDN) du pool qui se résout aux adresses IP physiques des serveurs du pool.</span><span class="sxs-lookup"><span data-stu-id="88a3c-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="88a3c-122">Sous **services Web externes**, tapez le nom de domaine complet du pool externe qui se résout aux adresses IP virtuelles de la liste, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="88a3c-123">À partir de l’arborescence de la console, cliquez sur **Lync Server 2013**, puis, dans le volet **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="88a3c-124">Pour créer des enregistrements d’hôte DNS (A) pour tous les serveurs de pool interne</span><span class="sxs-lookup"><span data-stu-id="88a3c-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="88a3c-125">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="88a3c-126">Dans le **Gestionnaire DNS**, cliquez sur le serveur DNS qui gère vos enregistrements pour le développer.</span><span class="sxs-lookup"><span data-stu-id="88a3c-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="88a3c-127">Cliquez sur **transférer des zones de recherche** pour les développer.</span><span class="sxs-lookup"><span data-stu-id="88a3c-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="88a3c-128">Cliquez avec le bouton droit sur le domaine DNS auquel vous devez ajouter des enregistrements, puis cliquez sur **nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="88a3c-129">Dans la zone **Nom**, tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).</span><span class="sxs-lookup"><span data-stu-id="88a3c-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="88a3c-130">Dans la zone adresse IP, tapez l’adresse IP du serveur principal individuel, puis sélectionnez créer un **pointeur associé (PTR)** , ou **autorisez les utilisateurs authentifiés à mettre à jour les enregistrements DNS portant le même nom de propriétaire**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="88a3c-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="88a3c-131">Continuez à créer des enregistrements pour tous les serveurs frontaux de membre qui feront partie de l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="88a3c-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="88a3c-132">Par exemple, si vous avez un pool intitulé pool1.contoso.com et trois serveurs front-end, vous devez créer les entrées DNS suivantes:</span><span class="sxs-lookup"><span data-stu-id="88a3c-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="88a3c-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="88a3c-133">FQDN</span></span></th>
    <th><span data-ttu-id="88a3c-134">Type</span><span class="sxs-lookup"><span data-stu-id="88a3c-134">Type</span></span></th>
    <th><span data-ttu-id="88a3c-135">Données</span><span class="sxs-lookup"><span data-stu-id="88a3c-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="88a3c-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88a3c-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-137">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="88a3c-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="88a3c-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="88a3c-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88a3c-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-140">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="88a3c-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="88a3c-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="88a3c-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="88a3c-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-143">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="88a3c-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="88a3c-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="88a3c-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="88a3c-145">Pour plus d’informations sur la création d’enregistrements DNS Host (A), voir [configurer les enregistrements d’hôte DNS pour Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="88a3c-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="88a3c-146">Pour activer le tourniquet cyclique pour Windows Server</span><span class="sxs-lookup"><span data-stu-id="88a3c-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="88a3c-147">Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="88a3c-148">Développez **DNS**, cliquez avec le bouton droit sur le serveur DNS à configurer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="88a3c-149">Cliquez sur l’onglet **avancé** , sélectionnez **activer la répétition alternée** et activez l’ordre de tri des **masques**net, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="88a3c-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="88a3c-150">![Boîte de dialogue de répétition alternée DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Boîte de dialogue de répétition alternée DNS")</span><span class="sxs-lookup"><span data-stu-id="88a3c-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88a3c-151">Cette fonctionnalité doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="88a3c-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88a3c-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88a3c-152">See Also</span></span>


[<span data-ttu-id="88a3c-153">Équilibrage de charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a3c-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

