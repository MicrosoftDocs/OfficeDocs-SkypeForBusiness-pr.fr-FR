---
title: 'Lync Server 2013 : configuration du DNS pour l’équilibrage de charge'
description: 'Lync Server 2013 : configuration du DNS pour l’équilibrage de charge.'
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
ms.openlocfilehash: 4b13db22d65ee67723ebc0a31544137d467d5c6b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553450"
---
# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a><span data-ttu-id="15bd7-103">Configurer le DNS pour l’équilibrage de charge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15bd7-103">Configure DNS for load balancing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15bd7-104">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="15bd7-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="15bd7-105">Pour effectuer correctement cette procédure, vous devez être connecté au serveur ou au domaine au moins en tant que membre du groupe Administrateurs du domaine ou du groupe DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="15bd7-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="15bd7-106">L’équilibrage de charge DNS (Domain Name System) équilibre le trafic réseau propre à Lync Server 2013, tel que le trafic SIP et le trafic multimédia.</span><span class="sxs-lookup"><span data-stu-id="15bd7-106">Domain Name System (DNS) Load Balancing balances the network traffic that is unique to Lync Server 2013, such as SIP traffic and media traffic.</span></span> <span data-ttu-id="15bd7-107">L’équilibrage de charge DNS est pris en charge pour les pools frontaux, les pools de serveurs Edge, les pools de serveurs directeurs et les pools de serveurs de médiation autonomes.</span><span class="sxs-lookup"><span data-stu-id="15bd7-107">DNS load balancing is supported for Front End pools, Edge pools, Director pools, and stand-alone Mediation pools.</span></span> <span data-ttu-id="15bd7-108">Un pool configuré pour utiliser l’équilibrage de charge DNS doit avoir deux noms de domaine complets (FQDN) définis : nom de domaine complet (FQDN) du pool normal utilisé par l’équilibrage de charge DNS (par exemple, pool1.contoso.com) et qui est résolu en adresses IP physiques des serveurs du pool, et un autre nom de domaine complet pour les services Web du pool (par exemple, web1.contoso.net), ce qui est résolu en adresse IP virtuelle du pool.</span><span class="sxs-lookup"><span data-stu-id="15bd7-108">A pool that is configured to use DNS load balancing must have two fully qualified domain names (FQDNs) defined: the regular pool FQDN that is used by DNS load balancing (for example, pool1.contoso.com) and that resolves to the physical IPs of the servers in the pool, and another FQDN for the pool’s Web Services (for example, web1.contoso.net), which resolves to the virtual IP address of the pool.</span></span> <span data-ttu-id="15bd7-109">Pour plus d’informations sur l’équilibrage de la charge DNS, voir [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="15bd7-109">For details about DNS Load Balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15bd7-110">L’équilibrage de la charge matérielle est toujours requis pour le trafic HTTPS du client au serveur.</span><span class="sxs-lookup"><span data-stu-id="15bd7-110">Hardware load balancing is still required for client to server HTTPS traffic.</span></span>



</div>

<span data-ttu-id="15bd7-111">Avant d’utiliser l’équilibrage de charge DNS, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="15bd7-111">Before you can use DNS load balancing, you must do the following:</span></span>

1.  <span data-ttu-id="15bd7-112">Remplacer le nom de domaine complet du pool des services Web internes.</span><span class="sxs-lookup"><span data-stu-id="15bd7-112">Override the internal Web Services pool FQDN.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="15bd7-113">Si vous décidez de remplacer les services Web internes par un nom de domaine complet indépendant, chaque nom de domaine complet doit être unique à partir de n’importe quel autre pool frontal, directeur ou pool directeur.</span><span class="sxs-lookup"><span data-stu-id="15bd7-113">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>

    
    </div>

2.  <span data-ttu-id="15bd7-114">Créer des enregistrements d’hôte DNS A pour résoudre le nom de domaine complet (FQDN) du pool en adresse IP pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="15bd7-114">Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.</span></span>

3.  <span data-ttu-id="15bd7-115">Activer la randomisation d’adresse IP ou, pour l’équilibrage de charge DNS sous Windows Server, activez le round robin.</span><span class="sxs-lookup"><span data-stu-id="15bd7-115">Enable IP Address randomization or, for Windows Server DNS, enable round robin.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="15bd7-116">La fonctionnalité de tourniquet (round robin) doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="15bd7-116">Round robin should be enabled by default.</span></span>

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a><span data-ttu-id="15bd7-117">Pour remplacer le nom de domaine complet des services web internes</span><span class="sxs-lookup"><span data-stu-id="15bd7-117">To override internal Web services FQDN</span></span>

1.  <span data-ttu-id="15bd7-118">Démarrez le Générateur de topologie : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Générateur de topologie Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-118">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="15bd7-119">Dans l’arborescence de la console, développez le nœud des pools frontaux Enterprise Edition.</span><span class="sxs-lookup"><span data-stu-id="15bd7-119">From the console tree, expand the Enterprise Edition Front End pools node.</span></span>

3.  <span data-ttu-id="15bd7-120">Cliquez avec le bouton droit sur le pool, cliquez sur **Modifier les propriétés**, puis cliquez sur **Services web**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-120">Right-click the pool, click **Edit Properties**, and then click **Web Services**.</span></span>

4.  <span data-ttu-id="15bd7-121">Sous **Services web internes**, activez la case à cocher **Remplacer le nom de domaine complet**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-121">Below **Internal web services**, select the **Override FQDN** check box.</span></span>

5.  <span data-ttu-id="15bd7-122">Tapez le nom de domaine complet du pool qui est résolu en adresse IP physique pour chaque serveur dans le pool.</span><span class="sxs-lookup"><span data-stu-id="15bd7-122">Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.</span></span>

6.  <span data-ttu-id="15bd7-123">Sous **Services web externes**, tapez le nom de domaine complet du pool externe qui est résolu en adresse IP virtuelle du pool, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-123">Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.</span></span>

7.  <span data-ttu-id="15bd7-124">Dans l’arborescence de la console, cliquez sur **Lync Server 2013**, puis dans le volet **actions** , cliquez sur **publier la topologie**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-124">From the console tree, click **Lync Server 2013**, and then in the **Actions** pane, click **Publish Topology**.</span></span>

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a><span data-ttu-id="15bd7-125">Pour créer des enregistrements d’hôte DNS (A) pour tous les serveurs du pool interne</span><span class="sxs-lookup"><span data-stu-id="15bd7-125">To create DNS Host (A) Records for all internal pool servers</span></span>

1.  <span data-ttu-id="15bd7-126">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-126">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="15bd7-127">Dans **Gestionnaire DNS**, cliquez sur le serveur DNS qui gère les enregistrements pour le développer.</span><span class="sxs-lookup"><span data-stu-id="15bd7-127">In **DNS Manager**, click the DNS Server that manages your records to expand it.</span></span>

3.  <span data-ttu-id="15bd7-128">Cliquez sur le nœud **Zones de recherche directes** pour le développer.</span><span class="sxs-lookup"><span data-stu-id="15bd7-128">Click **Forward Lookup Zones** to expand it.</span></span>

4.  <span data-ttu-id="15bd7-129">Cliquez avec le bouton droit sur le domaine DNS auquel vous devez ajouter des enregistrements, puis cliquez sur **Nouvel hôte (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-129">Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.</span></span>

5.  <span data-ttu-id="15bd7-130">Dans la zone **nom** , tapez le nom de l’enregistrement de l’hôte (le nom du domaine est automatiquement ajouté).</span><span class="sxs-lookup"><span data-stu-id="15bd7-130">In the **Name** box, type the name of the host record (the domain name will be automatically appended).</span></span>

6.  <span data-ttu-id="15bd7-131">Dans la zone Adresse IP, tapez l’adresse IP du serveur frontal, puis sélectionnez **Créer un pointeur d’enregistrement PTR associé** ou **Autoriser tout utilisateur identifié à mettre à jour les enregistrements DNS avec le même nom de propriétaire**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="15bd7-131">In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.</span></span>

7.  <span data-ttu-id="15bd7-132">Continuez à créer des enregistrements pour tous les serveurs frontaux membres qui participeront à l’équilibrage de charge DNS.</span><span class="sxs-lookup"><span data-stu-id="15bd7-132">Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.</span></span>
    
    <span data-ttu-id="15bd7-133">Par exemple, pour un pool nommé pool1.contoso.com et trois serveurs frontaux, vous devrez créer les entrées DNS suivantes :</span><span class="sxs-lookup"><span data-stu-id="15bd7-133">For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="15bd7-134">FQDN</span><span class="sxs-lookup"><span data-stu-id="15bd7-134">FQDN</span></span></th>
    <th><span data-ttu-id="15bd7-135">Type</span><span class="sxs-lookup"><span data-stu-id="15bd7-135">Type</span></span></th>
    <th><span data-ttu-id="15bd7-136">Données</span><span class="sxs-lookup"><span data-stu-id="15bd7-136">Data</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="15bd7-137">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15bd7-137">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-138">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="15bd7-138">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-139">192.168.1.1</span><span class="sxs-lookup"><span data-stu-id="15bd7-139">192.168.1.1</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="15bd7-140">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15bd7-140">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-141">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="15bd7-141">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-142">192.168.1.2</span><span class="sxs-lookup"><span data-stu-id="15bd7-142">192.168.1.2</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="15bd7-143">Pool1.contoso.com</span><span class="sxs-lookup"><span data-stu-id="15bd7-143">Pool1.contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-144">Hôte (A)</span><span class="sxs-lookup"><span data-stu-id="15bd7-144">Host (A)</span></span></p></td>
    <td><p><span data-ttu-id="15bd7-145">192.168.1.3</span><span class="sxs-lookup"><span data-stu-id="15bd7-145">192.168.1.3</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="15bd7-146">Pour plus d’informations sur la création d’enregistrements d’hôte DNS (A), voir [configurer les enregistrements d’hôte DNS pour Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span><span class="sxs-lookup"><span data-stu-id="15bd7-146">For details about creating DNS Host (A) records, see [Configure DNS Host records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).</span></span>

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a><span data-ttu-id="15bd7-147">Pour activer le round robin pour Windows Server</span><span class="sxs-lookup"><span data-stu-id="15bd7-147">To enable round robin for Windows Server</span></span>

1.  <span data-ttu-id="15bd7-148">Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **DNS**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-148">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="15bd7-149">Développez **DNS**, cliquez avec le bouton droit sur le serveur DNS que vous souhaitez configurer, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-149">Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.</span></span>

3.  <span data-ttu-id="15bd7-150">Cliquez sur l’onglet **Avancé**, sélectionnez **Activer la fonction Round Robin** et **Activer le tri de masques réseau**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="15bd7-150">Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.</span></span>
    
    <span data-ttu-id="15bd7-151">![Boîte de dialogue de répétition alternée DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Boîte de dialogue de répétition alternée DNS")</span><span class="sxs-lookup"><span data-stu-id="15bd7-151">![DNS Round Robin dialog box](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin dialog box")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15bd7-152">Cette fonctionnalité doit être activée par défaut.</span><span class="sxs-lookup"><span data-stu-id="15bd7-152">This feature should be enabled by default.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15bd7-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="15bd7-153">See Also</span></span>


[<span data-ttu-id="15bd7-154">Équilibrage de la charge DNS dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15bd7-154">DNS load balancing in Lync Server 2013</span></span>](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

