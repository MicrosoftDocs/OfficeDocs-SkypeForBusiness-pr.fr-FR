---
title: 'Lync Server 2013 : définition de la configuration requise pour le contrôle d’admission des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d26596f48178f53f79b1c4cc136610d45705ffd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="a5009-102">Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5009-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5009-103">_**Dernière modification de la rubrique :** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="a5009-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="a5009-p101">La planification du contrôle d’admission des appels (CAC) requiert des informations détaillées sur votre topologie de réseau d’entreprise. Pour vous aider à planifier vos stratégies de contrôle d’admission des appels, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="a5009-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="a5009-106">Identifiez les concentrateurs/dorsales principales (appelés *régions réseau*) dans votre réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a5009-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="a5009-107">Identifiez les bureaux et emplacements (appelés *sites réseau*) dans chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="a5009-108">Déterminez l’itinéraire réseau entre chaque paire de régions réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="a5009-109">Déterminez les limites de bande passante pour chaque liaison réseau étendu (WAN).</span><span class="sxs-lookup"><span data-stu-id="a5009-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5009-110">Les limites de bande passante font référence à la proportion de bande passante sur une liaison de réseau étendu allouée au trafic audio et vidéo de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a5009-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="a5009-111">Quand une liaison réseau étendu est décrite comme « à bande passante restreinte », la liaison réseau étendu a une limite de bande passante qui est inférieure au trafic maximal prévu sur la liaison.</span><span class="sxs-lookup"><span data-stu-id="a5009-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="a5009-112">Identifiez les sous-réseaux IP qui sont affectés à chaque site réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="a5009-113">Pour expliquer ces concepts, nous prendrons l’exemple de topologie réseau présenté à la figure suivante.</span><span class="sxs-lookup"><span data-stu-id="a5009-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="a5009-114">**Exemple de topologie pour le contrôle d’admission des appels**</span><span class="sxs-lookup"><span data-stu-id="a5009-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="a5009-115">![Exemple de topologie de réseau Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Exemple de topologie de réseau Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="a5009-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5009-p103">Tous les sites réseau sont associés à une région réseau. Par exemple, Portland, Reno et Albuquerque sont inclus dans la région Amérique du Nord. Dans cette figure, seules les liaisons réseau étendu auxquelles des stratégies de service Contrôle d’admission des appels sont appliquées sont présentées, avec des limites de bande passante. Les sites réseau Chicago, New York et Détroit apparaissent dans l’ovale de la région Amérique du Nord, car ils ne sont soumis à aucune limite de bande passante et ne nécessitent donc aucune stratégie de service Contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="a5009-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="a5009-120">Les composants de cet exemple de topologie sont décrits dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="a5009-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="a5009-121">Pour plus d’informations sur la planification de cette topologie, notamment les limites de bande passante, voir [example : Gathering Your Requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="a5009-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="a5009-122">Identifier les régions réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-122">Identify Network Regions</span></span>

<span data-ttu-id="a5009-123">Une région réseau représente une dorsale principale ou un concentrateur réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="a5009-p105">Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.</span><span class="sxs-lookup"><span data-stu-id="a5009-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="a5009-p106">Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient un ensemble de sites réseau (voir la définition des sites réseau plus loin dans cette rubrique). Collaborez avec votre équipe responsable des opérations réseau pour identifier vos régions réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="a5009-130">Association d’un site central avec chaque région réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="a5009-131">CAC exige qu’un site central Lync Server soit défini pour chaque région réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="a5009-132">Le site central est sélectionné en fonction de la meilleure connectivité réseau et de la bande passante la plus élevée parmi les autres sites de la région réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="a5009-133">L’exemple précédent de topologie réseau montre trois régions réseau, chacune comportant un site central qui gère les décisions du service Contrôle d’admission des appels.</span><span class="sxs-lookup"><span data-stu-id="a5009-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="a5009-134">Dans l’exemple précédent, l’association appropriée est indiquée dans le tableau ci-après.</span><span class="sxs-lookup"><span data-stu-id="a5009-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5009-135">Les sites centraux ne correspondent pas nécessairement aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="a5009-136">Dans les exemples de cette documentation, certains sites centraux (Chicago, Londres et Pékin) ont les mêmes noms que les sites réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="a5009-137">Toutefois, même si un site central et un site réseau partagent le même nom, le site central est un élément de la topologie Lync Server, tandis que le site réseau fait partie du réseau global dans lequel réside la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a5009-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="a5009-138">Régions réseau, sites centraux et sites réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5009-139">Région réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-139">Network Region</span></span></th>
<th><span data-ttu-id="a5009-140">Site central</span><span class="sxs-lookup"><span data-stu-id="a5009-140">Central Site</span></span></th>
<th><span data-ttu-id="a5009-141">Sites réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5009-142">Amérique du Nord</span><span class="sxs-lookup"><span data-stu-id="a5009-142">North America</span></span></p></td>
<td><p><span data-ttu-id="a5009-143">Renne</span><span class="sxs-lookup"><span data-stu-id="a5009-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="a5009-144">Renne</span><span class="sxs-lookup"><span data-stu-id="a5009-144">Chicago</span></span></p>
<p><span data-ttu-id="a5009-145">New York</span><span class="sxs-lookup"><span data-stu-id="a5009-145">New York</span></span></p>
<p><span data-ttu-id="a5009-146">Détroit</span><span class="sxs-lookup"><span data-stu-id="a5009-146">Detroit</span></span></p>
<p><span data-ttu-id="a5009-147">Agence</span><span class="sxs-lookup"><span data-stu-id="a5009-147">Portland</span></span></p>
<p><span data-ttu-id="a5009-148">Reno</span><span class="sxs-lookup"><span data-stu-id="a5009-148">Reno</span></span></p>
<p><span data-ttu-id="a5009-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="a5009-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="a5009-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="a5009-151">Londres</span><span class="sxs-lookup"><span data-stu-id="a5009-151">London</span></span></p></td>
<td><p><span data-ttu-id="a5009-152">Londres</span><span class="sxs-lookup"><span data-stu-id="a5009-152">London</span></span></p>
<p><span data-ttu-id="a5009-153">Cologne</span><span class="sxs-lookup"><span data-stu-id="a5009-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-154">APAC</span><span class="sxs-lookup"><span data-stu-id="a5009-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="a5009-155">Pékin</span><span class="sxs-lookup"><span data-stu-id="a5009-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="a5009-156">Pékin</span><span class="sxs-lookup"><span data-stu-id="a5009-156">Beijing</span></span></p>
<p><span data-ttu-id="a5009-157">Rigide</span><span class="sxs-lookup"><span data-stu-id="a5009-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="a5009-158">Identifier les sites réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-158">Identify Network Sites</span></span>

<span data-ttu-id="a5009-p109">Un site réseau représente un lieu physique pour votre organisation, par exemple des bureaux, un ensemble de bâtiments ou un campus. Tout lieu physique qui comporte un réseau local (LAN) et une connectivité de réseau étendu (WAN) vers d’autres sites est considéré comme un site réseau. Commencez par inventorier tous les bureaux de votre organisation. Dans notre exemple de topologie, la région réseau Amérique du Nord comporte les sites réseau suivants : New York, Chicago, Détroit, Portland, Reno et Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="a5009-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="a5009-p110">Vous devez associer chaque site réseau à une région réseau. Selon que le site réseau dispose d’une liaison réseau étendu restreinte, une stratégie de bande passante est associée au site réseau. Pour plus d’informations sur les stratégies de service Contrôle d’admission des appels et la bande passante que vous allouez en les utilisant, voir « Définir des stratégies de bande passante » plus loin dans cette rubrique. Pour configurer le service Contrôle d’admission des appels, associez des sites réseau à des régions réseau, puis créez des stratégies d’allocation de bande passante qui doivent être appliquées aux connexions à bande passante restreinte entre un site ou une région spécifique, mais aussi aux connexions réseau étendu entre des sites et des régions.</span><span class="sxs-lookup"><span data-stu-id="a5009-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="a5009-167">Identifier des liaisons réseau</span><span class="sxs-lookup"><span data-stu-id="a5009-167">Identify Network Links</span></span>

<span data-ttu-id="a5009-p111">Les liaisons réseau représentent les connexions au réseau étendu physique qui relient différentes régions et différents sites. Dans notre exemple de topologie, il y a deux liaisons réseau régionales, cinq liaisons réseau entre des régions et des sites, et une liaison réseau entre deux sites.</span><span class="sxs-lookup"><span data-stu-id="a5009-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="a5009-170">Les deux liaisons régionales sont entre Amérique du Nord et EMEA, représentés par NA-EMEA-LINK, et entre APAC et EMEA, représentés par EMEA-APAC-LINK.</span><span class="sxs-lookup"><span data-stu-id="a5009-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="a5009-p112">Les liaisons de sites sont indiquées par des traits connectant Portland, Reno et Albuquerque à la région Amérique du Nord, Manille à la région APAC, et Cologne à la région EMEA. Le trait entre Reno et Albuquerque indique une liaison réseau directe entre ces deux sites.</span><span class="sxs-lookup"><span data-stu-id="a5009-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="a5009-173">Définir des stratégies de bande passante</span><span class="sxs-lookup"><span data-stu-id="a5009-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="a5009-p113">Collaborez avec votre équipe responsable des opérations réseau pour déterminer la quantité de bande passante de réseau étendu mise à disposition du trafic audio et vidéo en temps réel sur les liaisons réseau étendu de votre organisation. Les stratégies de bande passante sont généralement appliquées aux liaisons réseau étendu si l’utilisation de la bande passante est restreinte ; c’est-à-dire, si on pense qu’elle sera supérieure à la bande passante pouvant être allouée aux modes audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="a5009-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="a5009-p114">Les *stratégies de bande passante* du service Contrôle d’admission des appels définissent la bande passante maximale qui peut être réservée aux modes audio et vidéo en temps réel. Comme le service Contrôle d’admission des appels ne limite pas la bande passante d’un autre trafic de données, il ne peut pas empêcher les autres trafics de données (par exemple, un transfert de fichiers volumineux ou la diffusion en continu de morceaux de musique) d’utiliser toute la bande passante réseau.</span><span class="sxs-lookup"><span data-stu-id="a5009-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="a5009-178">Les stratégies de bande passante CAC peuvent définir un ou plusieurs des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a5009-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="a5009-179">Bande passante totale maximale allouée à l’audio.</span><span class="sxs-lookup"><span data-stu-id="a5009-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="a5009-180">Bande passante totale maximale allouée à la vidéo.</span><span class="sxs-lookup"><span data-stu-id="a5009-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="a5009-181">Bande passante maximale allouée à un appel audio unique (session).</span><span class="sxs-lookup"><span data-stu-id="a5009-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="a5009-182">Bande passante maximale allouée à un appel vidéo unique (session).</span><span class="sxs-lookup"><span data-stu-id="a5009-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a5009-183">Toutes les valeurs de bande passante CAC représentent les limites de bande passante <EM>unidirectionnelle</EM> maximales.</span><span class="sxs-lookup"><span data-stu-id="a5009-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a5009-184">Les fonctionnalités de stratégie de voix Lync Server 2013 permettent de remplacer les vérifications de stratégie de bande passante pour les appels entrants vers l’utilisateur (pas pour les appels sortants passés par l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="a5009-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="a5009-185">Une fois la session établie, la consommation de bande passante est calculée avec précision.</span><span class="sxs-lookup"><span data-stu-id="a5009-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="a5009-186">Ce paramètre doit être utilisé avec modération.</span><span class="sxs-lookup"><span data-stu-id="a5009-186">This setting should be used sparingly.</span></span> <span data-ttu-id="a5009-187">Pour plus d’informations, voir <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">créer une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync server 2013</A> ou <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="a5009-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="a5009-p116">Pour optimiser l’utilisation de la bande passante par session, tenez compte du type des codecs audio et vidéo qui seront utilisés. Plus particulièrement, allouez suffisamment de bande passante pour un codec que vous pensez utiliser fréquemment. À l’inverse, si vous souhaitez empêcher le média d’utiliser un codec nécessitant davantage de bande passante, définissez une bande passante maximale par session qui soit suffisamment basse pour décourager ce type d’utilisation. Pour l’audio, tous les codecs ne sont pas disponibles pour chaque scénario. Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a5009-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="a5009-193">Les appels audio P2P entre les points de terminaison Lync utiliseront RTAudio (8 kHz) ou RTAudio (16 kHz) lorsque vous factorerez la bande passante et la définition des priorités des codecs.</span><span class="sxs-lookup"><span data-stu-id="a5009-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="a5009-194">Les appels de conférence entre les points de terminaison Lync et le service de conférence A/V utiliseront G. 722 ou Siren.</span><span class="sxs-lookup"><span data-stu-id="a5009-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="a5009-195">Les appels vers le réseau téléphonique commuté (PSTN) vers ou à partir de points de terminaison Lync utiliseront G. 711 ou RTAudio (8 kHz).</span><span class="sxs-lookup"><span data-stu-id="a5009-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="a5009-196">Utilisez le tableau suivant pour optimiser les paramètres de bande passante par session maximale.</span><span class="sxs-lookup"><span data-stu-id="a5009-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="a5009-197">Utilisation de la bande passante par codecs</span><span class="sxs-lookup"><span data-stu-id="a5009-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5009-198">Codec</span><span class="sxs-lookup"><span data-stu-id="a5009-198">Codec</span></span></th>
<th><span data-ttu-id="a5009-199">Besoin en bande passante sans correction des erreurs de transfert (FEC)</span><span class="sxs-lookup"><span data-stu-id="a5009-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="a5009-200">Besoin en bande passante avec correction des erreurs de transfert (FEC)</span><span class="sxs-lookup"><span data-stu-id="a5009-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5009-201">RTAudio (8 kHz)</span><span class="sxs-lookup"><span data-stu-id="a5009-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="a5009-202">49,8 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-203">61,6 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-204">RTAudio (16 kHz)</span><span class="sxs-lookup"><span data-stu-id="a5009-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="a5009-205">67 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-206">96 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-207">Siren</span><span class="sxs-lookup"><span data-stu-id="a5009-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="a5009-208">57,6 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-209">73,6 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-210">G. 711</span><span class="sxs-lookup"><span data-stu-id="a5009-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="a5009-211">102 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-212">166 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-213">G. 722</span><span class="sxs-lookup"><span data-stu-id="a5009-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="a5009-214">105,6 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-215">169,6 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-216">RTVideo (CIF 15 i/s)</span><span class="sxs-lookup"><span data-stu-id="a5009-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="a5009-217">260 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-218">Non applicable</span><span class="sxs-lookup"><span data-stu-id="a5009-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-219">RTVideo (VGA 30 i/s)</span><span class="sxs-lookup"><span data-stu-id="a5009-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="a5009-220">610 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-221">Non applicable</span><span class="sxs-lookup"><span data-stu-id="a5009-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a5009-p117">Les besoins en bande passante prennent en compte le traitement des éléments suivants : Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-Time Transport Protocol) et SRTP (Secure Real-Time Transport Protocol). Ils incluent également 10 Kbits/s pour le traitement RTCP.</span><span class="sxs-lookup"><span data-stu-id="a5009-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="a5009-224">Les codecs G.722.1 et Siren sont similaires, mais offrent différentes vitesses de transmission.</span><span class="sxs-lookup"><span data-stu-id="a5009-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="a5009-225">G. 722, le codec par défaut pour la Conférence Lync Server, est complètement différent des codecs G. 722.1 et Siren.</span><span class="sxs-lookup"><span data-stu-id="a5009-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="a5009-226">Le codec Siren est utilisé dans Lync Server dans les situations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5009-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="a5009-227">La stratégie de bande passante est définie sur une valeur trop basse pour permettre l’utilisation de G.722.</span><span class="sxs-lookup"><span data-stu-id="a5009-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="a5009-228">Si un client Communications Server 2007 ou Communications Server 2007 R2 se connecte à un service de conférence Lync Server (car ces clients ne prennent pas en charge le codec G. 722).</span><span class="sxs-lookup"><span data-stu-id="a5009-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="a5009-229">Utilisation de la bande passante par scénario</span><span class="sxs-lookup"><span data-stu-id="a5009-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a5009-230">Scénario</span><span class="sxs-lookup"><span data-stu-id="a5009-230">Scenario</span></span></th>
<th><span data-ttu-id="a5009-231">Besoins en bande passante optimisés pour la quantité (Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="a5009-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="a5009-232">Besoins en bande passante pour le mode équilibré (Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="a5009-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="a5009-233">Besoins en bande passante optimisés pour la qualité (Kbits/s)</span><span class="sxs-lookup"><span data-stu-id="a5009-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a5009-234">Appels audio d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="a5009-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="a5009-235">45 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-236">62 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-237">91 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-238">Téléconférences</span><span class="sxs-lookup"><span data-stu-id="a5009-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="a5009-239">53 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-240">101 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-241">165 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-242">Appels RTC (entre Lync 2013 et la passerelle PSTN, avec déviation du trafic multimédia)</span><span class="sxs-lookup"><span data-stu-id="a5009-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="a5009-243">97 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-244">97 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-245">161 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-246">Appels RTC (entre Lync 2013 et le serveur de médiation sans déviation du trafic multimédia)</span><span class="sxs-lookup"><span data-stu-id="a5009-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="a5009-247">45 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-248">97 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-249">161 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a5009-250">Appels RTC (entre le serveur de médiation et la passerelle PSTN, sans déviation du trafic multimédia)</span><span class="sxs-lookup"><span data-stu-id="a5009-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="a5009-251">97 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-252">97 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-253">161 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a5009-254">Appels Lync Polycom</span><span class="sxs-lookup"><span data-stu-id="a5009-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="a5009-255">101 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-256">101 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="a5009-257">101 Kbits/s</span><span class="sxs-lookup"><span data-stu-id="a5009-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="a5009-258">Identifier les sous-réseaux IP</span><span class="sxs-lookup"><span data-stu-id="a5009-258">Identify IP Subnets</span></span>

<span data-ttu-id="a5009-p118">Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.</span><span class="sxs-lookup"><span data-stu-id="a5009-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="a5009-p119">Dans notre exemple, le site New York de la région Amérique du Nord se voit affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supposons que Bob, qui travaille généralement à Détroit, se rende dans les bureaux de New York pour suivre une formation. Quand il allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages réservées à New York (par exemple, 172.29.80.103).</span><span class="sxs-lookup"><span data-stu-id="a5009-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="a5009-264">Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="a5009-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="a5009-265">Un client Lync prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé.</span><span class="sxs-lookup"><span data-stu-id="a5009-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="a5009-266">Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte.</span><span class="sxs-lookup"><span data-stu-id="a5009-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="a5009-267">Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels.</span><span class="sxs-lookup"><span data-stu-id="a5009-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="a5009-268">(Si vous déployez le contrôle d’admission des appels, mais pas le contournement de média, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)</span><span class="sxs-lookup"><span data-stu-id="a5009-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="a5009-269">Par exemple, si un client se connecte sur un ordinateur dont l’adresse IP est 172.29.81.57 avec un masque de sous-réseau IP 255.255.255.0, Lync 2013 demande l’ID de contournement associé au sous-réseau 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="a5009-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="a5009-270">Si le sous-réseau est défini comme 172.29.0.0/16, bien que le client appartienne au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="a5009-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="a5009-271">Par conséquent, il est important que l’administrateur entre des sous-réseaux exactement comme fournis par les clients Lync (qui sont configurés avec des sous-réseaux pendant la configuration du réseau, de façon statique ou par DHCP).</span><span class="sxs-lookup"><span data-stu-id="a5009-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

