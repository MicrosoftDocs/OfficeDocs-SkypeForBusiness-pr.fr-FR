---
title: Exemple de collecte de la configuration requise pour le contrôle d’admission des appels
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e0b0a294500514ce1b200fd646ed4e70136828
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="d3968-102">Exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3968-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3968-103">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d3968-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d3968-p101">Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3968-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="d3968-106">Identifiez l’ensemble de vos concentrateurs réseau et dorsales principales (connues aussi sous le nom de *régions réseau*).</span><span class="sxs-lookup"><span data-stu-id="d3968-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="d3968-107">Identifiez le site central Lync Server qui doit gérer le contrôle d’admission de la connexion pour chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="d3968-108">Identifiez et définissez les *sites réseau* connectés à chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="d3968-109">Pour chaque site réseau dont la connexion au réseau étendu est limitée, décrivez la capacité de bande passante de la connexion WAN et les limites de bande passante que l’administrateur réseau a défini pour le trafic multimédia Lync Server, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="d3968-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="d3968-110">Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.</span><span class="sxs-lookup"><span data-stu-id="d3968-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="d3968-111">Associez chaque sous-réseau de votre réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="d3968-112">Mappez les liaisons entre régions réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-112">Map the links between the network regions.</span></span> <span data-ttu-id="d3968-113">Pour chaque lien, décrivez sa capacité de bande passante et les limites que l’administrateur réseau a placées sur le trafic multimédia Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3968-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="d3968-114">Définissez un itinéraire entre chaque paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="d3968-115">Rassembler les informations requises</span><span class="sxs-lookup"><span data-stu-id="d3968-115">Gather the Required Information</span></span>

<span data-ttu-id="d3968-116">Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="d3968-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="d3968-p104">Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="d3968-p105">Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.</span><span class="sxs-lookup"><span data-stu-id="d3968-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="d3968-p106">Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="d3968-125">Identifiez le site central associé à chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="d3968-126">Un site central contient au moins un serveur frontal et le déploiement Lync Server qui gère le contrôle d’admission des médias pour tout le trafic multimédia transitant par la connexion WAN de la région réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="d3968-127">**Exemple de réseau d’entreprise divisé en trois régions réseau**</span><span class="sxs-lookup"><span data-stu-id="d3968-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="d3968-128">![Exemple de topologie réseau avec 3 régions réseau](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemple de topologie réseau avec 3 régions réseau")</span><span class="sxs-lookup"><span data-stu-id="d3968-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3968-129">Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant.</span><span class="sxs-lookup"><span data-stu-id="d3968-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="d3968-130">Pour plus d’informations, reportez-vous à la rubrique «<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call Admission Control on an MPLS Network with Lync Server 2013</A>» dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d3968-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="d3968-131">Dans l’exemple de topologie réseau, il existe trois régions réseau, chacune comportant un site central Lync Server qui gère le contrôle d’admission des requêtes.</span><span class="sxs-lookup"><span data-stu-id="d3968-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="d3968-132">Le site central approprié pour une région réseau est choisi par le voisinage géographique.</span><span class="sxs-lookup"><span data-stu-id="d3968-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="d3968-133">Étant donné que le trafic multimédia sera le plus lourd dans les régions réseau, la propriété par voisinage géographique le rend autonome et continuera de fonctionner même si d’autres sites centraux deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="d3968-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="d3968-134">Dans cet exemple, un déploiement Lync Server nommé Chicago est le site central de la région Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="d3968-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="d3968-135">Tous les utilisateurs Lync en Amérique du Nord sont hébergés sur des serveurs du déploiement de Chicago.</span><span class="sxs-lookup"><span data-stu-id="d3968-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="d3968-136">Le tableau suivant répertorie les sites centraux pour les trois régions réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="d3968-137">Régions réseau et leur site central associé</span><span class="sxs-lookup"><span data-stu-id="d3968-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-138">Région réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-138">Network Region</span></span></th>
    <th><span data-ttu-id="d3968-139">Site central</span><span class="sxs-lookup"><span data-stu-id="d3968-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-140">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-141">Renne</span><span class="sxs-lookup"><span data-stu-id="d3968-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="d3968-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d3968-143">Londres</span><span class="sxs-lookup"><span data-stu-id="d3968-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-144">APAC</span><span class="sxs-lookup"><span data-stu-id="d3968-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d3968-145">Pékin</span><span class="sxs-lookup"><span data-stu-id="d3968-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3968-146">En fonction de votre topologie Lync Server, le même site central peut être affecté à plusieurs régions réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="d3968-p111">Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au WAN ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.</span><span class="sxs-lookup"><span data-stu-id="d3968-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="d3968-149">Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.</span><span class="sxs-lookup"><span data-stu-id="d3968-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="d3968-150">Sites réseau non limités par la bande passante de la connexion WAN</span><span class="sxs-lookup"><span data-stu-id="d3968-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-151">Site réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-151">Network Site</span></span></th>
    <th><span data-ttu-id="d3968-152">Région réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-153">New York</span><span class="sxs-lookup"><span data-stu-id="d3968-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="d3968-154">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-155">Renne</span><span class="sxs-lookup"><span data-stu-id="d3968-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d3968-156">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-157">Détroit</span><span class="sxs-lookup"><span data-stu-id="d3968-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d3968-158">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="d3968-159">Pour chaque région réseau, identifiez tous les sites réseau se connectant à la région réseau via des liaisons WAN dont la bande passante est limitée.</span><span class="sxs-lookup"><span data-stu-id="d3968-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="d3968-160">Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux WAN des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) depuis et vers la région réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="d3968-161">Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du WAN : Portland, Reno et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="d3968-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="d3968-162">Sites réseau limités par la bande passante de la connexion WAN</span><span class="sxs-lookup"><span data-stu-id="d3968-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-163">Site réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-163">Network Site</span></span></th>
    <th><span data-ttu-id="d3968-164">Région réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="d3968-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d3968-166">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-167">Reno</span><span class="sxs-lookup"><span data-stu-id="d3968-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d3968-168">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-169">Agence</span><span class="sxs-lookup"><span data-stu-id="d3968-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d3968-170">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="d3968-171">**Région réseau CAC Amérique du Nord et trois sites réseau non limités par la bande passante (Chicago, New York et Détroit) et trois sites réseau limités par la bande passante de la liaison WAN (Portland, Reno et Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="d3968-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="d3968-172">![Exemples de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemples de sites réseau limités par la bande passante de la connexion WAN")</span><span class="sxs-lookup"><span data-stu-id="d3968-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="d3968-173">Pour chaque liaison WAN dont la bande passante est limitée, déterminez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="d3968-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="d3968-174">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d3968-175">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p113">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d3968-178">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d3968-179">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p115">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="d3968-182">Sites réseau et informations de restriction de bande passante WAN (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="d3968-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-183">Site réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-183">Network Site</span></span></th>
    <th><span data-ttu-id="d3968-184">Région réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-184">Network Region</span></span></th>
    <th><span data-ttu-id="d3968-185">Limite BP</span><span class="sxs-lookup"><span data-stu-id="d3968-185">BW Limit</span></span></th>
    <th><span data-ttu-id="d3968-186">Limite audio</span><span class="sxs-lookup"><span data-stu-id="d3968-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="d3968-187">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="d3968-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d3968-188">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-188">Video Limit</span></span></th>
    <th><span data-ttu-id="d3968-189">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="d3968-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d3968-191">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-192">5,000</span><span class="sxs-lookup"><span data-stu-id="d3968-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-193">2,000</span><span class="sxs-lookup"><span data-stu-id="d3968-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-194">175</span><span class="sxs-lookup"><span data-stu-id="d3968-194">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-195">1 400</span><span class="sxs-lookup"><span data-stu-id="d3968-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="d3968-196">700</span><span class="sxs-lookup"><span data-stu-id="d3968-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-197">Reno</span><span class="sxs-lookup"><span data-stu-id="d3968-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d3968-198">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-199">10 000</span><span class="sxs-lookup"><span data-stu-id="d3968-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-200">4 000</span><span class="sxs-lookup"><span data-stu-id="d3968-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-201">175</span><span class="sxs-lookup"><span data-stu-id="d3968-201">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-202">2 800</span><span class="sxs-lookup"><span data-stu-id="d3968-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d3968-203">700</span><span class="sxs-lookup"><span data-stu-id="d3968-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-204">Agence</span><span class="sxs-lookup"><span data-stu-id="d3968-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d3968-205">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-206">5,000</span><span class="sxs-lookup"><span data-stu-id="d3968-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-207">4 000</span><span class="sxs-lookup"><span data-stu-id="d3968-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-208">175</span><span class="sxs-lookup"><span data-stu-id="d3968-208">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-209">2 800</span><span class="sxs-lookup"><span data-stu-id="d3968-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d3968-210">700</span><span class="sxs-lookup"><span data-stu-id="d3968-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-211">New York</span><span class="sxs-lookup"><span data-stu-id="d3968-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="d3968-212">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-213">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-214">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-215">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-216">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-217">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-218">Renne</span><span class="sxs-lookup"><span data-stu-id="d3968-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d3968-219">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-220">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-221">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-222">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-223">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-224">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-225">Détroit</span><span class="sxs-lookup"><span data-stu-id="d3968-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d3968-226">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-227">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-228">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-229">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-230">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-231">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="d3968-232">Pour chaque sous-réseau du réseau, indiquez son site réseau associé.</span><span class="sxs-lookup"><span data-stu-id="d3968-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="d3968-p116">Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un système d’extrémité doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="d3968-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="d3968-237">Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé.</span><span class="sxs-lookup"><span data-stu-id="d3968-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="d3968-238">Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32.</span><span class="sxs-lookup"><span data-stu-id="d3968-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="d3968-239">Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="d3968-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="d3968-240">Pour plus d’informations sur les adresses IP publiques, voir <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine External A/V Firewall and Port Requirements for Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="d3968-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3968-p118">Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d3968-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="d3968-244"><STRONG>Source :</STRONG> Service de stratégie de bande passante CS (Core)</span><span class="sxs-lookup"><span data-stu-id="d3968-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="d3968-245"><STRONG>Numéro d’événement :</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="d3968-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="d3968-246"><STRONG>Niveau :</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="d3968-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="d3968-247"><STRONG>Description :</STRONG> Les sous-réseaux pour les adresses IP suivantes &lt;: la liste des&gt; adresses IP n’est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="d3968-248"><STRONG>Cause :</STRONG> Les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="d3968-249"><STRONG>Résolution :</STRONG> Ajoutez des sous-réseaux correspondant à la liste précédente d’adresses IP dans les paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="d3968-p119">Par exemple, si la liste d’adresses IP qui apparaît dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3968-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="d3968-252">Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="d3968-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="d3968-253">Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="d3968-254">Sites réseau et sous-réseaux associés (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="d3968-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-255">Site réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-255">Network Site</span></span></th>
    <th><span data-ttu-id="d3968-256">Région réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-256">Network Region</span></span></th>
    <th><span data-ttu-id="d3968-257">Limite BP</span><span class="sxs-lookup"><span data-stu-id="d3968-257">BW Limit</span></span></th>
    <th><span data-ttu-id="d3968-258">Limite audio</span><span class="sxs-lookup"><span data-stu-id="d3968-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="d3968-259">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="d3968-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d3968-260">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-260">Video Limit</span></span></th>
    <th><span data-ttu-id="d3968-261">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="d3968-262">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="d3968-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="d3968-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d3968-264">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-265">5,000</span><span class="sxs-lookup"><span data-stu-id="d3968-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-266">2,000</span><span class="sxs-lookup"><span data-stu-id="d3968-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-267">175</span><span class="sxs-lookup"><span data-stu-id="d3968-267">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-268">1 400</span><span class="sxs-lookup"><span data-stu-id="d3968-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="d3968-269">700</span><span class="sxs-lookup"><span data-stu-id="d3968-269">700</span></span></p></td>
    <td><p><span data-ttu-id="d3968-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="d3968-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-271">Reno</span><span class="sxs-lookup"><span data-stu-id="d3968-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d3968-272">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-273">10 000</span><span class="sxs-lookup"><span data-stu-id="d3968-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-274">4 000</span><span class="sxs-lookup"><span data-stu-id="d3968-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-275">175</span><span class="sxs-lookup"><span data-stu-id="d3968-275">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-276">2 800</span><span class="sxs-lookup"><span data-stu-id="d3968-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d3968-277">700</span><span class="sxs-lookup"><span data-stu-id="d3968-277">700</span></span></p></td>
    <td><p><span data-ttu-id="d3968-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="d3968-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-279">Agence</span><span class="sxs-lookup"><span data-stu-id="d3968-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="d3968-280">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-281">5,000</span><span class="sxs-lookup"><span data-stu-id="d3968-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-282">4 000</span><span class="sxs-lookup"><span data-stu-id="d3968-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-283">175</span><span class="sxs-lookup"><span data-stu-id="d3968-283">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-284">2 800</span><span class="sxs-lookup"><span data-stu-id="d3968-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="d3968-285">700</span><span class="sxs-lookup"><span data-stu-id="d3968-285">700</span></span></p></td>
    <td><p><span data-ttu-id="d3968-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="d3968-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-287">New York</span><span class="sxs-lookup"><span data-stu-id="d3968-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="d3968-288">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-289">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-290">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-291">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-292">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-293">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="d3968-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-295">Renne</span><span class="sxs-lookup"><span data-stu-id="d3968-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="d3968-296">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-297">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-298">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-299">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-300">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-301">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="d3968-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-303">Détroit</span><span class="sxs-lookup"><span data-stu-id="d3968-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="d3968-304">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-305">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-306">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-307">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-308">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-309">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="d3968-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="d3968-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="d3968-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="d3968-311">Dans le contrôle d’admission des appels Lync Server, les connexions entre les régions réseau sont appelées *liens de région*.</span><span class="sxs-lookup"><span data-stu-id="d3968-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="d3968-312">Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :</span><span class="sxs-lookup"><span data-stu-id="d3968-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="d3968-313">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d3968-314">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p122">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d3968-317">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d3968-318">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p124">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="d3968-321">**Liens de région réseau et limites de bande passante associées**</span><span class="sxs-lookup"><span data-stu-id="d3968-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="d3968-322">![Exemple de limitations entre 3 régions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemple de limitations entre 3 régions")</span><span class="sxs-lookup"><span data-stu-id="d3968-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="d3968-323">Information de bande passante du lien de région (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="d3968-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-324">Nom de la liaison réseau</span><span class="sxs-lookup"><span data-stu-id="d3968-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="d3968-325">Première région</span><span class="sxs-lookup"><span data-stu-id="d3968-325">First Region</span></span></th>
    <th><span data-ttu-id="d3968-326">Seconde région</span><span class="sxs-lookup"><span data-stu-id="d3968-326">Second Region</span></span></th>
    <th><span data-ttu-id="d3968-327">Limite BP</span><span class="sxs-lookup"><span data-stu-id="d3968-327">BW Limit</span></span></th>
    <th><span data-ttu-id="d3968-328">Limite audio</span><span class="sxs-lookup"><span data-stu-id="d3968-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="d3968-329">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="d3968-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d3968-330">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-330">Video Limit</span></span></th>
    <th><span data-ttu-id="d3968-331">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-332">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="d3968-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="d3968-333">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="d3968-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d3968-335">50 000</span><span class="sxs-lookup"><span data-stu-id="d3968-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-336">20,000</span><span class="sxs-lookup"><span data-stu-id="d3968-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-337">175</span><span class="sxs-lookup"><span data-stu-id="d3968-337">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-338">14 000</span><span class="sxs-lookup"><span data-stu-id="d3968-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-339">700</span><span class="sxs-lookup"><span data-stu-id="d3968-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-340">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="d3968-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="d3968-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="d3968-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d3968-342">APAC</span><span class="sxs-lookup"><span data-stu-id="d3968-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d3968-343">25 000</span><span class="sxs-lookup"><span data-stu-id="d3968-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-344">10 000</span><span class="sxs-lookup"><span data-stu-id="d3968-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-345">175</span><span class="sxs-lookup"><span data-stu-id="d3968-345">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-346">7 000</span><span class="sxs-lookup"><span data-stu-id="d3968-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-347">700</span><span class="sxs-lookup"><span data-stu-id="d3968-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="d3968-348">Définissez un itinéraire entre chaque paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="d3968-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="d3968-349">Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement.</span><span class="sxs-lookup"><span data-stu-id="d3968-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="d3968-350">Itinéraires de région</span><span class="sxs-lookup"><span data-stu-id="d3968-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-351">Nom de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="d3968-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="d3968-352">Première région</span><span class="sxs-lookup"><span data-stu-id="d3968-352">First Region</span></span></th>
    <th><span data-ttu-id="d3968-353">Seconde région</span><span class="sxs-lookup"><span data-stu-id="d3968-353">Second Region</span></span></th>
    <th><span data-ttu-id="d3968-354">Liens de région</span><span class="sxs-lookup"><span data-stu-id="d3968-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-355">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="d3968-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d3968-356">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="d3968-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d3968-358">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="d3968-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="d3968-359">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="d3968-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d3968-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="d3968-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="d3968-361">APAC</span><span class="sxs-lookup"><span data-stu-id="d3968-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d3968-362">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="d3968-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-363">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="d3968-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="d3968-364">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="d3968-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="d3968-365">APAC</span><span class="sxs-lookup"><span data-stu-id="d3968-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="d3968-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="d3968-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="d3968-367">Pour chaque paire de sites réseau directement connectée à une seule liaison (appelée liaison *intersite*), déterminez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d3968-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="d3968-368">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="d3968-369">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p126">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="d3968-372">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="d3968-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="d3968-373">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="d3968-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="d3968-p128">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d3968-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="d3968-376">**Région réseau CAC Amérique du Nord avec les capacités et les limites de bande passante de la liaison intersite entre Reno et Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="d3968-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="d3968-377">![Exemples de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Exemples de sites réseau limités par la bande passante de la connexion WAN")</span><span class="sxs-lookup"><span data-stu-id="d3968-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="d3968-378">Information de bande passante d’une liaison intersite entre deux sites réseau (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="d3968-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="d3968-379">Nom de la liaison intersite</span><span class="sxs-lookup"><span data-stu-id="d3968-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="d3968-380">Premier site</span><span class="sxs-lookup"><span data-stu-id="d3968-380">First Site</span></span></th>
    <th><span data-ttu-id="d3968-381">Second site</span><span class="sxs-lookup"><span data-stu-id="d3968-381">Second Site</span></span></th>
    <th><span data-ttu-id="d3968-382">Limite BP</span><span class="sxs-lookup"><span data-stu-id="d3968-382">BW Limit</span></span></th>
    <th><span data-ttu-id="d3968-383">Limite audio</span><span class="sxs-lookup"><span data-stu-id="d3968-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="d3968-384">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="d3968-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="d3968-385">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-385">Video Limit</span></span></th>
    <th><span data-ttu-id="d3968-386">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="d3968-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="d3968-387">Reno-Albu-lien intersites</span><span class="sxs-lookup"><span data-stu-id="d3968-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="d3968-388">Reno</span><span class="sxs-lookup"><span data-stu-id="d3968-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="d3968-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="d3968-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="d3968-390">20,000</span><span class="sxs-lookup"><span data-stu-id="d3968-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-391">12 000</span><span class="sxs-lookup"><span data-stu-id="d3968-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-392">175</span><span class="sxs-lookup"><span data-stu-id="d3968-392">175</span></span></p></td>
    <td><p><span data-ttu-id="d3968-393">5,000</span><span class="sxs-lookup"><span data-stu-id="d3968-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="d3968-394">700</span><span class="sxs-lookup"><span data-stu-id="d3968-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="d3968-395">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="d3968-395">Next Steps</span></span>

<span data-ttu-id="d3968-396">Une fois que vous avez rassemblé les informations requises, vous pouvez effectuer un déploiement CAC à l’aide du panneau de configuration Lync Server Management Shell ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3968-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d3968-397">Bien que vous puissiez effectuer la plupart des tâches de configuration réseau à l’aide du panneau de configuration Lync Server, pour créer des sous-réseaux et des liaisons intersites, vous devez utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d3968-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="d3968-398">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour la cmdlet <STRONG>New-CsNetworkSubnet</STRONG> et la cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d3968-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

