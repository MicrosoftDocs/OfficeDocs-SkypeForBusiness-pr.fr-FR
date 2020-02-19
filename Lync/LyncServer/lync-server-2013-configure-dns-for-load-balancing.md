---
title: 'Lync Server 2013 : configuration du DNS pour l’équilibrage de charge'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257bd8d1d4874bb2483c16c2216c4b76b178a881
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="2be74-102">Configurer le DNS pour l’équilibrage de charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be74-102">Configure DNS for load balancing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2be74-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2be74-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2be74-104">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="2be74-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="2be74-105">L’équilibrage de charge DNS (Domain Name System) équilibre le trafic réseau propre à Lync Server 2013, tel que le trafic SIP et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="2be74-105">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="2be74-106">L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools de serveurs directeurs et les pools de serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="2be74-106">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="2be74-107">Un pool configuré pour utiliser l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) définis : le nom de domaine complet du pool normal qui est utilisé par l’équilibrage de charge DNS (par exemple, pool1.contoso.com) et qui est résolu en adresses IP physiques des serveurs du pool. et un autre nom de domaine complet pour les services Web du pool (par exemple, web1.contoso.net), qui est résolu en adresse IP virtuelle du pool.</span><span class="sxs-lookup"><span data-stu-id="2be74-107">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="2be74-108">Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="2be74-108">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2be74-109">L’équilibrage de la charge matérielle est toujours requis pour le trafic HTTPS du client au serveur.</span><span class="sxs-lookup"><span data-stu-id="2be74-109">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="2be74-110">Avant d’utiliser l’équilibrage de charge DNS, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="2be74-110">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="2be74-111">Remplacer le nom de domaine complet du pool des services Web internes.</span><span class="sxs-lookup"><span data-stu-id="2be74-111">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2be74-112">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="2be74-112">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="2be74-113">Créer des enregistrements d’hôte DNS A pour résoudre le nom de domaine complet (FQDN) du pool en adresse IP pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="2be74-113">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="2be74-114">Activer la randomisation d’adresse IP ou, pour l’équilibrage de charge DNS sous Windows Server, activez le round robin.</span><span class="sxs-lookup"><span data-stu-id="2be74-114">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2be74-115">La fonctionnalité de tourniquet (round robin) doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2be74-115">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="2be74-116">Pour remplacer le nom de domaine complet des services web internes</span><span class="sxs-lookup"><span data-stu-id="2be74-116">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="2be74-117">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2be74-117">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="2be74-118">Dans l’arborescence de la console, développez le nœud des pools frontaux Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="2be74-118">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="2be74-119">Cliquez avec le bouton droit sur le pool, cliquez sur **Modifier les propriétés**, puis cliquez sur **Services web**.</span><span class="sxs-lookup"><span data-stu-id="2be74-119">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="2be74-120">Sous **Services web internes**, activez la case à cocher **Remplacer le nom de domaine complet**.</span><span class="sxs-lookup"><span data-stu-id="2be74-120">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="2be74-121">Tapez le nom de domaine complet du pool qui est résolu en adresse IP physique pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="2be74-121">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="2be74-122">Sous **Services web externes**, tapez le nom de domaine complet du pool externe qui est résolu en adresse IP virtuelle du pool, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be74-122">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="2be74-123">Dans l’arborescence de la console, cliquez sur **Lync Server 2013**, puis dans le volet **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="2be74-123">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="2be74-124">Pour créer des enregistrements d’hôte DNS (A) pour tous les serveurs du pool interne</span><span class="sxs-lookup"><span data-stu-id="2be74-124">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="2be74-125">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2be74-125">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="2be74-126">Dans **Gestionnaire DNS**, cliquez sur le serveur DNS qui gère les enregistrements pour le développer.</span><span class="sxs-lookup"><span data-stu-id="2be74-126">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="2be74-127">Cliquez sur le nœud **Zones de recherche directes** pour le développer.</span><span class="sxs-lookup"><span data-stu-id="2be74-127">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="2be74-128">Cliquez avec le bouton droit sur le domaine DNS auquel vous devez ajouter des enregistrements, puis cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="2be74-128">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="2be74-129">Dans la zone **nom** , tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).</span><span class="sxs-lookup"><span data-stu-id="2be74-129">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="2be74-130">Dans la zone Adresse IP, tapez l’adresse IP du serveur frontal, puis sélectionnez **Créer un pointeur d’enregistrement PTR associé** ou **Autoriser tout utilisateur identifié à mettre à jour les enregistrements DNS avec le même nom de propriétaire**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="2be74-130">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="2be74-131">Continuez à créer des enregistrements pour tous les serveurs frontaux membres qui participeront à l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="2be74-131">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="2be74-132">Par exemple, pour un pool nommé pool1.contoso.com et trois serveurs frontaux, vous devrez créer les entrées DNS suivantes :</span><span class="sxs-lookup"><span data-stu-id="2be74-132">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="2be74-133">FQDN</span><span class="sxs-lookup"><span data-stu-id="2be74-133">FQDN</span></span></th>
    <th><span data-ttu-id="2be74-134">Type</span><span class="sxs-lookup"><span data-stu-id="2be74-134">Type</span></span></th>
    <th><span data-ttu-id="2be74-135">Données</span><span class="sxs-lookup"><span data-stu-id="2be74-135">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="2be74-136">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2be74-136">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="2be74-137">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="2be74-137">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="2be74-138">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="2be74-138">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="2be74-139">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2be74-139">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="2be74-140">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="2be74-140">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="2be74-141">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="2be74-141">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="2be74-142">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2be74-142">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="2be74-143">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="2be74-143">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="2be74-144">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="2be74-144">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="2be74-145">Pour plus d’informations sur la création d’enregistrements d’hôte DNS (A), voir [configurer les enregistrements d’hôte DNS pour Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="2be74-145">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="2be74-146">Pour activer le round robin pour Windows Server</span><span class="sxs-lookup"><span data-stu-id="2be74-146">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="2be74-147">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2be74-147">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="2be74-148">Développez **DNS**, cliquez avec le bouton droit sur le serveur DNS que vous souhaitez configurer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="2be74-148">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="2be74-149">Cliquez sur l’onglet **Avancé**, sélectionnez **Activer la fonction Round Robin** et **Activer le tri de masques réseau**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be74-149">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="2be74-150">![Boîte de dialogue de répétition alternée DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Boîte de dialogue de répétition alternée DNS")</span><span class="sxs-lookup"><span data-stu-id="2be74-150">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2be74-151">Cette fonctionnalité doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2be74-151">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2be74-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2be74-152">See Also</span></span>


[<span data-ttu-id="2be74-153">Équilibrage de la charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2be74-153">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

