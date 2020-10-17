---
title: Exemple de collecte de la configuration requise pour le contrôle d’admission des appels
description: Exemple de collecte de la configuration requise pour le contrôle d’admission des appels.
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
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564940"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="be3b0-103">Exemple : collecte de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be3b0-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be3b0-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="be3b0-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="be3b0-p101">Cet exemple indique comment planifier et implémenter le contrôle d’admission des appels (CAC). Globalement, il s’agit des activités suivantes :</span><span class="sxs-lookup"><span data-stu-id="be3b0-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="be3b0-107">Identifiez l’ensemble de vos concentrateurs réseau et dorsales principales (connues aussi sous le nom de *régions réseau*).</span><span class="sxs-lookup"><span data-stu-id="be3b0-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="be3b0-108">Identifiez le site central Lync Server qui doit gérer le contrôle d’admission de la connexion pour chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="be3b0-109">Identifiez et définissez les *sites réseau* connectés à chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="be3b0-110">Pour chaque site réseau dont la connexion au réseau étendu est limitée, décrivez la capacité de bande passante de la connexion WAN et les limites de bande passante que l’administrateur réseau a défini pour le trafic multimédia Lync Server, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="be3b0-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="be3b0-111">Il n’est pas nécessaire d’inclure les sites dont la bande passante de connexion de réseau étendu n’est pas limitée.</span><span class="sxs-lookup"><span data-stu-id="be3b0-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="be3b0-112">Associez chaque sous-réseau de votre réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="be3b0-113">Mappez les liaisons entre régions réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-113">Map the links between the network regions.</span></span> <span data-ttu-id="be3b0-114">Pour chaque lien, décrivez sa capacité de bande passante et les limites que l’administrateur réseau a placées sur le trafic multimédia Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be3b0-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="be3b0-115">Définissez un itinéraire entre chaque paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="be3b0-116">Rassembler les informations requises</span><span class="sxs-lookup"><span data-stu-id="be3b0-116">Gather the Required Information</span></span>

<span data-ttu-id="be3b0-117">Pour préparer le contrôle d’admission des appels, rassemblez les informations présentées dans les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="be3b0-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="be3b0-p104">Identifiez vos régions réseau. Une région réseau représente une dorsale principale ou un concentrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="be3b0-p105">Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="be3b0-p106">Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient une collection de sites réseau. Définissez les régions réseau de votre entreprise avec l’administrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="be3b0-126">Identifiez le site central associé à chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="be3b0-127">Un site central contient au moins un serveur frontal et le déploiement Lync Server qui gère le contrôle d’admission des médias pour tout le trafic multimédia transitant par la connexion WAN de la région réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="be3b0-128">**Exemple de réseau d’entreprise divisé en trois régions réseau**</span><span class="sxs-lookup"><span data-stu-id="be3b0-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="be3b0-129">![Exemple de topologie réseau avec 3 régions réseau](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Exemple de topologie réseau avec 3 régions réseau")</span><span class="sxs-lookup"><span data-stu-id="be3b0-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be3b0-130">Un réseau MPLS (Multiprotocol Label Switching) devrait être représenté en tant que région réseau dans laquelle un emplacement géographique est associé à un site réseau correspondant.</span><span class="sxs-lookup"><span data-stu-id="be3b0-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="be3b0-131">Pour plus d’informations, reportez-vous à la rubrique «<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call Admission Control on an MPLS Network with Lync Server 2013</A>» dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="be3b0-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="be3b0-132">Dans l’exemple de topologie réseau, il existe trois régions réseau, chacune comportant un site central Lync Server qui gère le contrôle d’admission des requêtes.</span><span class="sxs-lookup"><span data-stu-id="be3b0-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="be3b0-133">Le site central approprié pour une région réseau est choisi par le voisinage géographique.</span><span class="sxs-lookup"><span data-stu-id="be3b0-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="be3b0-134">Étant donné que le trafic multimédia sera le plus lourd dans les régions réseau, la propriété par voisinage géographique le rend autonome et continuera de fonctionner même si d’autres sites centraux deviennent indisponibles.</span><span class="sxs-lookup"><span data-stu-id="be3b0-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="be3b0-135">Dans cet exemple, un déploiement Lync Server nommé Chicago est le site central de la région Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="be3b0-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="be3b0-136">Tous les utilisateurs Lync en Amérique du Nord sont hébergés sur des serveurs du déploiement de Chicago.</span><span class="sxs-lookup"><span data-stu-id="be3b0-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="be3b0-137">Le tableau suivant répertorie les sites centraux pour les trois régions réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="be3b0-138">Régions réseau et leur site central associé</span><span class="sxs-lookup"><span data-stu-id="be3b0-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="be3b0-139">Région réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-139">Network Region</span></span></th>
    <th><span data-ttu-id="be3b0-140">Site central</span><span class="sxs-lookup"><span data-stu-id="be3b0-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-141">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-142">Renne</span><span class="sxs-lookup"><span data-stu-id="be3b0-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="be3b0-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-144">Londres</span><span class="sxs-lookup"><span data-stu-id="be3b0-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-145">APAC</span><span class="sxs-lookup"><span data-stu-id="be3b0-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-146">Pékin</span><span class="sxs-lookup"><span data-stu-id="be3b0-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be3b0-147">En fonction de votre topologie Lync Server, le même site central peut être affecté à plusieurs régions réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="be3b0-p111">Pour chaque région réseau, identifiez tous les sites réseau (bureaux ou emplacements) dont les connexions au WAN ne sont pas soumises à une limite de bande passante. Comme ces sites disposent de liaisons réseau dont la bande passante n’est pas limitée, il n’est pas nécessaire de leur appliquer des stratégies de bande passante CAC.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="be3b0-150">Dans l’exemple présenté dans le tableau suivant, trois sites réseau disposent de liaisons réseau dont la bande passante n’est pas limitée : New York, Chicago et Détroit.</span><span class="sxs-lookup"><span data-stu-id="be3b0-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="be3b0-151">Sites réseau non limités par la bande passante de la connexion WAN</span><span class="sxs-lookup"><span data-stu-id="be3b0-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="be3b0-152">Site réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-152">Network Site</span></span></th>
    <th><span data-ttu-id="be3b0-153">Région réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-154">New York</span><span class="sxs-lookup"><span data-stu-id="be3b0-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-155">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-156">Renne</span><span class="sxs-lookup"><span data-stu-id="be3b0-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-157">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-158">Détroit</span><span class="sxs-lookup"><span data-stu-id="be3b0-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-159">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="be3b0-160">Pour chaque région réseau, identifiez tous les sites réseau se connectant à la région réseau via des liaisons WAN dont la bande passante est limitée.</span><span class="sxs-lookup"><span data-stu-id="be3b0-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="be3b0-161">Pour garantir la qualité de l’audio et de la vidéo, nous recommandons de surveiller les réseaux WAN des sites dont la bande passante est limitée et d’imposer des stratégies de bande passante CAC limitant le flux multimédia (vocal ou vidéo) depuis et vers la région réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="be3b0-162">Dans l’exemple présenté dans le tableau suivant, trois sites réseaux sont limités par la bande passante du WAN : Portland, Reno et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="be3b0-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="be3b0-163">Sites réseau limités par la bande passante de la connexion WAN</span><span class="sxs-lookup"><span data-stu-id="be3b0-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="be3b0-164">Site réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-164">Network Site</span></span></th>
    <th><span data-ttu-id="be3b0-165">Région réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-166">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="be3b0-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-167">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-168">Reno</span><span class="sxs-lookup"><span data-stu-id="be3b0-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-169">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-170">Agence</span><span class="sxs-lookup"><span data-stu-id="be3b0-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-171">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="be3b0-172">**Région réseau CAC Amérique du Nord et trois sites réseau non limités par la bande passante (Chicago, New York et Détroit) et trois sites réseau limités par la bande passante de la liaison WAN (Portland, Reno et Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="be3b0-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="be3b0-173">![Exemples de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Exemples de sites réseau limités par la bande passante de la connexion WAN")</span><span class="sxs-lookup"><span data-stu-id="be3b0-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="be3b0-174">Pour chaque liaison WAN dont la bande passante est limitée, déterminez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="be3b0-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="be3b0-175">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="be3b0-176">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p113">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="be3b0-179">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="be3b0-180">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p115">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="be3b0-183">Sites réseau et informations de restriction de bande passante WAN (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="be3b0-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="be3b0-184">Site réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-184">Network Site</span></span></th>
    <th><span data-ttu-id="be3b0-185">Région réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-185">Network Region</span></span></th>
    <th><span data-ttu-id="be3b0-186">Limite BP</span><span class="sxs-lookup"><span data-stu-id="be3b0-186">BW Limit</span></span></th>
    <th><span data-ttu-id="be3b0-187">Limite audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="be3b0-188">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="be3b0-189">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-189">Video Limit</span></span></th>
    <th><span data-ttu-id="be3b0-190">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-191">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="be3b0-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-192">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-193">5,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-194">2,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-195">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-195">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-196">1 400</span><span class="sxs-lookup"><span data-stu-id="be3b0-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-197">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-198">Reno</span><span class="sxs-lookup"><span data-stu-id="be3b0-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-199">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-200">10 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-201">4 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-202">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-202">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-203">2 800</span><span class="sxs-lookup"><span data-stu-id="be3b0-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-204">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-205">Agence</span><span class="sxs-lookup"><span data-stu-id="be3b0-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-206">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-207">5,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-208">4 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-209">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-209">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-210">2 800</span><span class="sxs-lookup"><span data-stu-id="be3b0-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-211">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-212">New York</span><span class="sxs-lookup"><span data-stu-id="be3b0-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-213">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-214">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-215">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-216">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-217">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-218">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-219">Renne</span><span class="sxs-lookup"><span data-stu-id="be3b0-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-220">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-221">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-222">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-223">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-224">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-225">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-226">Détroit</span><span class="sxs-lookup"><span data-stu-id="be3b0-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-227">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-228">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-229">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-230">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-231">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-232">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="be3b0-233">Pour chaque sous-réseau du réseau, indiquez son site réseau associé.</span><span class="sxs-lookup"><span data-stu-id="be3b0-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="be3b0-p116">Chaque sous-réseau doit être associé à un site réseau, même si le site réseau n’est pas soumis à une limite de bande passante. Cela est dû au fait que le contrôle d’admission des appels utilise les informations relatives aux sous-réseaux pour déterminer sur quel site réseau un système d’extrémité doit se situer. Lorsque les emplacements de chaque partie de la session sont déterminés, le contrôle d’admission des appels peut déterminer si la bande passante est suffisante pour établir l’appel. Lorsqu’une session est établie sur une liaison dont la bande passante n’est pas limitée, une alerte est générée.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="be3b0-238">Si vous déployez des serveurs Edge A/V, les adresses IP publiques de chaque serveur Edge doivent être associées au site réseau sur lequel le serveur Edge est déployé.</span><span class="sxs-lookup"><span data-stu-id="be3b0-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="be3b0-239">Vous devez ajouter chaque adresse IP publique du serveur Edge A/V à vos paramètres de configuration réseau en tant que sous-réseau avec un masque de sous réseau de 32.</span><span class="sxs-lookup"><span data-stu-id="be3b0-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="be3b0-240">Par exemple, si vous déployez des serveurs Edge A/V à Chicago, pour chaque adresse IP externe de ces serveurs, créez un sous-réseau avec un masque de sous-réseau de 32 et associez le site réseau Chicago à ces sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="be3b0-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="be3b0-241">Pour plus d’informations sur les adresses IP publiques, voir <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determine External A/V Firewall and Port Requirements for Lync Server 2013</A> dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="be3b0-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be3b0-p118">Une alerte d’indicateur d’intégrité clé est générée, indiquant une liste d’adresses IP figurant dans votre réseau, mais non associées à un sous-réseau ou figurant dans un sous-réseau non associé à un site réseau. L’alerte n’est générée qu’une seule fois par période de 8 heures. Les informations d’alerte pertinentes et un exemple sont présentés ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="be3b0-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="be3b0-245"><STRONG>Source :</STRONG> Service de stratégie de bande passante CS (Core)</span><span class="sxs-lookup"><span data-stu-id="be3b0-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="be3b0-246"><STRONG>Numéro d’événement :</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="be3b0-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="be3b0-247"><STRONG>Niveau :</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="be3b0-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="be3b0-248"><STRONG>Description :</STRONG> Les sous-réseaux pour les adresses IP suivantes : la &lt; liste des adresses IP n' &gt; est pas configurée ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="be3b0-249"><STRONG>Cause :</STRONG> Les sous-réseaux pour les adresses IP correspondantes sont absents des paramètres de configuration du réseau ou les sous-réseaux ne sont pas associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="be3b0-250"><STRONG>Résolution :</STRONG> Ajoutez des sous-réseaux correspondant à la liste précédente d’adresses IP dans les paramètres de configuration du réseau et associez chaque sous-réseau à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="be3b0-p119">Par exemple, si la liste d’adresses IP qui apparaît dans l’alerte indique 10.121.248.226 et 10.121.249.20, soit ces adresses IP ne sont pas associées à un sous-réseau, soit le sous-réseau auquel elles sont associées n’appartient pas au site réseau. Si 10.121.248.0/24 et 10.121.249.0/24 sont les sous-réseaux associés à ces adresses, vous pouvez résoudre le problème comme suit :</span><span class="sxs-lookup"><span data-stu-id="be3b0-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="be3b0-253">Vérifiez que l’adresse IP 10.121.248.226 est associée au sous-réseau 10.121.248.0/24 et l’adresse IP 10.121.249.20 au sous-réseau 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="be3b0-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="be3b0-254">Vérifiez que les sous-réseaux 10.121.248.0/24 et 10.121.249.0/24 sont chacun associés à un site réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="be3b0-255">Sites réseau et sous-réseaux associés (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="be3b0-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="be3b0-256">Site réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-256">Network Site</span></span></th>
    <th><span data-ttu-id="be3b0-257">Région réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-257">Network Region</span></span></th>
    <th><span data-ttu-id="be3b0-258">Limite BP</span><span class="sxs-lookup"><span data-stu-id="be3b0-258">BW Limit</span></span></th>
    <th><span data-ttu-id="be3b0-259">Limite audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="be3b0-260">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="be3b0-261">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-261">Video Limit</span></span></th>
    <th><span data-ttu-id="be3b0-262">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="be3b0-263">Sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="be3b0-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-264">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="be3b0-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-265">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-266">5,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-267">2,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-268">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-268">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-269">1 400</span><span class="sxs-lookup"><span data-stu-id="be3b0-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-270">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-270">700</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="be3b0-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-272">Reno</span><span class="sxs-lookup"><span data-stu-id="be3b0-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-273">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-274">10 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-275">4 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-276">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-276">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-277">2 800</span><span class="sxs-lookup"><span data-stu-id="be3b0-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-278">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-278">700</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="be3b0-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-280">Agence</span><span class="sxs-lookup"><span data-stu-id="be3b0-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-281">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-282">5,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-283">4 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-284">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-284">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-285">2 800</span><span class="sxs-lookup"><span data-stu-id="be3b0-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-286">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-286">700</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="be3b0-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-288">New York</span><span class="sxs-lookup"><span data-stu-id="be3b0-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-289">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-290">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-291">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-292">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-293">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-294">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="be3b0-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-296">Renne</span><span class="sxs-lookup"><span data-stu-id="be3b0-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-297">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-298">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-299">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-300">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-301">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-302">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="be3b0-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-304">Détroit</span><span class="sxs-lookup"><span data-stu-id="be3b0-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-305">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-306">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-307">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-308">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-309">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-310">(aucune limite)</span><span class="sxs-lookup"><span data-stu-id="be3b0-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="be3b0-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="be3b0-312">Dans le contrôle d’admission des appels Lync Server, les connexions entre les régions réseau sont appelées *liens de région*.</span><span class="sxs-lookup"><span data-stu-id="be3b0-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="be3b0-313">Pour chaque lien de région, déterminez ce qui suit, tout comme vous l’avez fait pour les sites réseau :</span><span class="sxs-lookup"><span data-stu-id="be3b0-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="be3b0-314">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="be3b0-315">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p122">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="be3b0-318">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="be3b0-319">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p124">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="be3b0-322">**Liens de région réseau et limites de bande passante associées**</span><span class="sxs-lookup"><span data-stu-id="be3b0-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="be3b0-323">![Exemple de limitations entre 3 régions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Exemple de limitations entre 3 régions")</span><span class="sxs-lookup"><span data-stu-id="be3b0-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="be3b0-324">Information de bande passante du lien de région (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="be3b0-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="be3b0-325">Nom de la liaison réseau</span><span class="sxs-lookup"><span data-stu-id="be3b0-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="be3b0-326">Première région</span><span class="sxs-lookup"><span data-stu-id="be3b0-326">First Region</span></span></th>
    <th><span data-ttu-id="be3b0-327">Seconde région</span><span class="sxs-lookup"><span data-stu-id="be3b0-327">Second Region</span></span></th>
    <th><span data-ttu-id="be3b0-328">Limite BP</span><span class="sxs-lookup"><span data-stu-id="be3b0-328">BW Limit</span></span></th>
    <th><span data-ttu-id="be3b0-329">Limite audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="be3b0-330">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="be3b0-331">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-331">Video Limit</span></span></th>
    <th><span data-ttu-id="be3b0-332">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-333">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="be3b0-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-334">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="be3b0-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-336">50 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-337">20,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-338">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-338">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-339">14 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-340">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-341">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="be3b0-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="be3b0-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-343">APAC</span><span class="sxs-lookup"><span data-stu-id="be3b0-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-344">25 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-345">10 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-346">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-346">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-347">7 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-348">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="be3b0-349">Définissez un itinéraire entre chaque paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="be3b0-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="be3b0-350">Deux liaisons sont nécessaires à l’itinéraire entre les régions Amérique du Nord et APAC, car aucun lien de région ne les relie directement.</span><span class="sxs-lookup"><span data-stu-id="be3b0-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="be3b0-351">Itinéraires de région</span><span class="sxs-lookup"><span data-stu-id="be3b0-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="be3b0-352">Nom de l’itinéraire</span><span class="sxs-lookup"><span data-stu-id="be3b0-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="be3b0-353">Première région</span><span class="sxs-lookup"><span data-stu-id="be3b0-353">First Region</span></span></th>
    <th><span data-ttu-id="be3b0-354">Seconde région</span><span class="sxs-lookup"><span data-stu-id="be3b0-354">Second Region</span></span></th>
    <th><span data-ttu-id="be3b0-355">Liens de région</span><span class="sxs-lookup"><span data-stu-id="be3b0-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-356">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="be3b0-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-357">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="be3b0-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-359">NA-EMEA-LINK</span><span class="sxs-lookup"><span data-stu-id="be3b0-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="be3b0-360">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="be3b0-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="be3b0-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-362">APAC</span><span class="sxs-lookup"><span data-stu-id="be3b0-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-363">EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="be3b0-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-364">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="be3b0-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-365">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="be3b0-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-366">APAC</span><span class="sxs-lookup"><span data-stu-id="be3b0-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-367">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="be3b0-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="be3b0-368">Pour chaque paire de sites réseau directement connectée à une seule liaison (appelée liaison *intersite*), déterminez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="be3b0-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="be3b0-369">Limite de bande passante globale à appliquer à toutes les sessions audio simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="be3b0-370">Si une nouvelle session audio entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p126">Limite de bande passante à appliquer à chaque session audio individuelle. La bande passante CAC par défaut est de 175 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="be3b0-373">Limite de bande passante globale à appliquer à toutes les sessions vidéo simultanées.</span><span class="sxs-lookup"><span data-stu-id="be3b0-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="be3b0-374">Si une nouvelle session vidéo entraîne le dépassement de cette limite, Lync Server n’autorise pas le démarrage de la session.</span><span class="sxs-lookup"><span data-stu-id="be3b0-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="be3b0-p128">Limite de bande passante à appliquer à chaque session vidéo individuelle. La bande passante CAC par défaut est de 700 Kbits/s, mais elle est modifiable par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="be3b0-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="be3b0-377">**Région réseau CAC Amérique du Nord avec les capacités et les limites de bande passante de la liaison intersite entre Reno et Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="be3b0-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="be3b0-378">![Exemples de sites réseau limités par la bande passante de la connexion WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Exemples de sites réseau limités par la bande passante de la connexion WAN")</span><span class="sxs-lookup"><span data-stu-id="be3b0-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="be3b0-379">Information de bande passante d’une liaison intersite entre deux sites réseau (bande passante en Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="be3b0-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="be3b0-380">Nom de la liaison intersite</span><span class="sxs-lookup"><span data-stu-id="be3b0-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="be3b0-381">Premier site</span><span class="sxs-lookup"><span data-stu-id="be3b0-381">First Site</span></span></th>
    <th><span data-ttu-id="be3b0-382">Second site</span><span class="sxs-lookup"><span data-stu-id="be3b0-382">Second Site</span></span></th>
    <th><span data-ttu-id="be3b0-383">Limite BP</span><span class="sxs-lookup"><span data-stu-id="be3b0-383">BW Limit</span></span></th>
    <th><span data-ttu-id="be3b0-384">Limite audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="be3b0-385">Limite de session audio</span><span class="sxs-lookup"><span data-stu-id="be3b0-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="be3b0-386">Limite vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-386">Video Limit</span></span></th>
    <th><span data-ttu-id="be3b0-387">Limite de session vidéo</span><span class="sxs-lookup"><span data-stu-id="be3b0-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="be3b0-388">Reno-Albu-lien intersites</span><span class="sxs-lookup"><span data-stu-id="be3b0-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-389">Reno</span><span class="sxs-lookup"><span data-stu-id="be3b0-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-390">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="be3b0-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-391">20,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-392">12 000</span><span class="sxs-lookup"><span data-stu-id="be3b0-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-393">175</span><span class="sxs-lookup"><span data-stu-id="be3b0-393">175</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-394">5,000</span><span class="sxs-lookup"><span data-stu-id="be3b0-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="be3b0-395">700</span><span class="sxs-lookup"><span data-stu-id="be3b0-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="be3b0-396">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="be3b0-396">Next Steps</span></span>

<span data-ttu-id="be3b0-397">Une fois que vous avez rassemblé les informations requises, vous pouvez effectuer un déploiement CAC à l’aide du panneau de configuration Lync Server Management Shell ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be3b0-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="be3b0-398">Bien que vous puissiez effectuer la plupart des tâches de configuration réseau à l’aide du panneau de configuration Lync Server, pour créer des sous-réseaux et des liaisons intersites, vous devez utiliser Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="be3b0-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="be3b0-399">Pour plus d’informations, reportez-vous à la documentation Lync Server Management Shell pour la cmdlet <STRONG>New-CsNetworkSubnet</STRONG> et la cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="be3b0-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

