---
title: 'Lync Server 2013 : configuration du routage des Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517413"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="640e5-102">Configuration du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640e5-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="640e5-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="640e5-104">Lync Server 2013 CU1, le routage Location-Based est une fonctionnalité de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="640e5-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="640e5-105">Le routage des Location-Based est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="640e5-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="640e5-106">Elle impose des restrictions quant à la possibilité de router les appels vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync.</span><span class="sxs-lookup"><span data-stu-id="640e5-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="640e5-107">Le routage des Location-Based applique les règles d’autorisation des appels aux appels RTC en fonction de l’emplacement réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="640e5-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="640e5-108">L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau auquel l’appelant est connecté.</span><span class="sxs-lookup"><span data-stu-id="640e5-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="640e5-109">La configuration du routage des Location-Based nécessite le déploiement d’Enterprise Voice, puis la configuration des régions réseau, des sites et des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="640e5-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="640e5-110">Cela permet de configurer la base pour activer le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="640e5-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="640e5-111">Avant de déployer Location-Based routage, vous devez d’abord déployer voix entreprise et configurer des régions réseau, des sites et des sous-réseaux associés sur vos sites réseau.</span><span class="sxs-lookup"><span data-stu-id="640e5-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="640e5-112">Une fois l’opération terminée, vous pouvez configurer le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="640e5-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="640e5-113">Pour connaître les étapes de configuration des régions réseau, des sites et des sous-réseaux, voir [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="640e5-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="640e5-114">Cette section vous guide tout au long de la configuration du routage des Location-Based à l’aide de l’exemple suivant comme illustration.</span><span class="sxs-lookup"><span data-stu-id="640e5-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="640e5-115">![Exemple de routage basé sur l’emplacement de voix entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage basé sur l’emplacement de voix entreprise")</span><span class="sxs-lookup"><span data-stu-id="640e5-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="640e5-116">Le tableau suivant représente les utilisateurs définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="640e5-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640e5-117">Type de point de terminaison</span><span class="sxs-lookup"><span data-stu-id="640e5-117">Endpoint type</span></span></th>
<th><span data-ttu-id="640e5-118">Emplacement</span><span class="sxs-lookup"><span data-stu-id="640e5-118">Location</span></span></th>
<th><span data-ttu-id="640e5-119">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="640e5-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640e5-120">Lync</span><span class="sxs-lookup"><span data-stu-id="640e5-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="640e5-121">Siège social de Delhi</span><span class="sxs-lookup"><span data-stu-id="640e5-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="640e5-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="640e5-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-123">Lync</span><span class="sxs-lookup"><span data-stu-id="640e5-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="640e5-124">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="640e5-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="640e5-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="640e5-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-126">Lync</span><span class="sxs-lookup"><span data-stu-id="640e5-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="640e5-127">Inconnu (c.-à-d. Hotel)</span><span class="sxs-lookup"><span data-stu-id="640e5-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="640e5-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="640e5-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-129">PBX</span><span class="sxs-lookup"><span data-stu-id="640e5-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="640e5-130">Siège social de Delhi</span><span class="sxs-lookup"><span data-stu-id="640e5-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="640e5-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="640e5-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-132">PBX</span><span class="sxs-lookup"><span data-stu-id="640e5-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="640e5-133">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="640e5-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="640e5-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="640e5-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-135">RTC</span><span class="sxs-lookup"><span data-stu-id="640e5-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="640e5-136">Inconnu</span><span class="sxs-lookup"><span data-stu-id="640e5-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="640e5-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="640e5-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="640e5-138">Le tableau suivant représente les systèmes illustrés dans cet exemple d’environnement.</span><span class="sxs-lookup"><span data-stu-id="640e5-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="640e5-139">Système</span><span class="sxs-lookup"><span data-stu-id="640e5-139">System</span></span></th>
<th><span data-ttu-id="640e5-140">Emplacement</span><span class="sxs-lookup"><span data-stu-id="640e5-140">Location</span></span></th>
<th><span data-ttu-id="640e5-141">Nom</span><span class="sxs-lookup"><span data-stu-id="640e5-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="640e5-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="640e5-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="640e5-143">indifférent</span><span class="sxs-lookup"><span data-stu-id="640e5-143">any</span></span></p></td>
<td><p><span data-ttu-id="640e5-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="640e5-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-145">Lync Server 2013 CU1, serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="640e5-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="640e5-146">indifférent</span><span class="sxs-lookup"><span data-stu-id="640e5-146">any</span></span></p></td>
<td><p><span data-ttu-id="640e5-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="640e5-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-148">Passerelle PSTN 1</span><span class="sxs-lookup"><span data-stu-id="640e5-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="640e5-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="640e5-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="640e5-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="640e5-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-151">Passerelle PSTN 2</span><span class="sxs-lookup"><span data-stu-id="640e5-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="640e5-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="640e5-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="640e5-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="640e5-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="640e5-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="640e5-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="640e5-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="640e5-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="640e5-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="640e5-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="640e5-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="640e5-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="640e5-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="640e5-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="640e5-159">PBX ROUGE</span><span class="sxs-lookup"><span data-stu-id="640e5-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="640e5-160">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="640e5-160">In This Section</span></span>

  - [<span data-ttu-id="640e5-161">Configuration de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="640e5-162">Déploiement des régions réseau, des sites et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="640e5-163">Activation du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="640e5-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="640e5-164">See Also</span></span>


[<span data-ttu-id="640e5-165">Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640e5-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

