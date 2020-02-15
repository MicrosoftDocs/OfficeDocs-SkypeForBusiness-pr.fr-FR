---
title: 'Lync Server 2013 : configuration du routage géodépendant'
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
ms.openlocfilehash: 31e8877c4691decfe0c2e65fd820e97432e095aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="72e0c-102">Configuration du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e0c-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72e0c-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="72e0c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="72e0c-104">Lync Server 2013 CU1, le routage géodépendant est une fonctionnalité de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="72e0c-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="72e0c-105">Le routage géodépendant est une fonctionnalité de gestion des appels qui contrôle la manière dont les appels sont routés par Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="72e0c-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="72e0c-106">Elle impose des restrictions quant à la possibilité de router les appels vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync.</span><span class="sxs-lookup"><span data-stu-id="72e0c-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="72e0c-107">Le routage géodépendant applique des règles d’autorisation d’appels aux appels RTC en fonction de l’emplacement réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="72e0c-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="72e0c-108">L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau auquel l’appelant est connecté.</span><span class="sxs-lookup"><span data-stu-id="72e0c-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="72e0c-109">La configuration du routage géodépendant nécessite le déploiement d’Enterprise Voice, puis la configuration des régions réseau, des sites et des sous-réseaux.</span><span class="sxs-lookup"><span data-stu-id="72e0c-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="72e0c-110">Cela configure les bases de l’activation du routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="72e0c-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="72e0c-111">Avant de déployer le routage géodépendant, vous devez d’abord déployer voix entreprise et configurer des régions réseau, des sites et des sous-réseaux associés sur vos sites réseau.</span><span class="sxs-lookup"><span data-stu-id="72e0c-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="72e0c-112">Une fois terminé, vous pouvez configurer le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="72e0c-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="72e0c-113">Pour connaître les étapes de configuration des régions réseau, des sites et des sous-réseaux, voir [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="72e0c-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="72e0c-114">Cette section vous guide tout au long de la configuration du routage géodépendant en utilisant l’exemple suivant comme illustration.</span><span class="sxs-lookup"><span data-stu-id="72e0c-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="72e0c-115">![Exemple de routage basé sur l’emplacement de voix entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage basé sur l’emplacement de voix entreprise")</span><span class="sxs-lookup"><span data-stu-id="72e0c-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="72e0c-116">Le tableau suivant représente les utilisateurs définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="72e0c-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72e0c-117">Type de point de terminaison</span><span class="sxs-lookup"><span data-stu-id="72e0c-117">Endpoint type</span></span></th>
<th><span data-ttu-id="72e0c-118">L’emplacement</span><span class="sxs-lookup"><span data-stu-id="72e0c-118">Location</span></span></th>
<th><span data-ttu-id="72e0c-119">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="72e0c-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-120">Lync</span><span class="sxs-lookup"><span data-stu-id="72e0c-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="72e0c-121">Siège social de Delhi</span><span class="sxs-lookup"><span data-stu-id="72e0c-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="72e0c-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="72e0c-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-123">Lync</span><span class="sxs-lookup"><span data-stu-id="72e0c-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="72e0c-124">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="72e0c-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="72e0c-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="72e0c-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-126">Lync</span><span class="sxs-lookup"><span data-stu-id="72e0c-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="72e0c-127">Inconnu (c.-à-d. Hotel)</span><span class="sxs-lookup"><span data-stu-id="72e0c-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="72e0c-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="72e0c-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-129">PBX</span><span class="sxs-lookup"><span data-stu-id="72e0c-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="72e0c-130">Siège social de Delhi</span><span class="sxs-lookup"><span data-stu-id="72e0c-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="72e0c-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="72e0c-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-132">PBX</span><span class="sxs-lookup"><span data-stu-id="72e0c-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="72e0c-133">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="72e0c-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="72e0c-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="72e0c-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-135">RTC</span><span class="sxs-lookup"><span data-stu-id="72e0c-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="72e0c-136">Inconnu</span><span class="sxs-lookup"><span data-stu-id="72e0c-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="72e0c-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="72e0c-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="72e0c-138">Le tableau suivant représente les systèmes illustrés dans cet exemple d’environnement.</span><span class="sxs-lookup"><span data-stu-id="72e0c-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="72e0c-139">Système</span><span class="sxs-lookup"><span data-stu-id="72e0c-139">System</span></span></th>
<th><span data-ttu-id="72e0c-140">L’emplacement</span><span class="sxs-lookup"><span data-stu-id="72e0c-140">Location</span></span></th>
<th><span data-ttu-id="72e0c-141">Nom</span><span class="sxs-lookup"><span data-stu-id="72e0c-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="72e0c-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="72e0c-143">indifférent</span><span class="sxs-lookup"><span data-stu-id="72e0c-143">any</span></span></p></td>
<td><p><span data-ttu-id="72e0c-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="72e0c-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-145">Lync Server 2013 CU1, serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="72e0c-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="72e0c-146">indifférent</span><span class="sxs-lookup"><span data-stu-id="72e0c-146">any</span></span></p></td>
<td><p><span data-ttu-id="72e0c-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="72e0c-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-148">Passerelle PSTN 1</span><span class="sxs-lookup"><span data-stu-id="72e0c-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="72e0c-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="72e0c-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="72e0c-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="72e0c-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-151">Passerelle PSTN 2</span><span class="sxs-lookup"><span data-stu-id="72e0c-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="72e0c-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="72e0c-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="72e0c-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="72e0c-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="72e0c-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="72e0c-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="72e0c-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="72e0c-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="72e0c-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="72e0c-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72e0c-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="72e0c-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="72e0c-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="72e0c-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="72e0c-159">PBX ROUGE</span><span class="sxs-lookup"><span data-stu-id="72e0c-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="72e0c-160">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="72e0c-160">In This Section</span></span>

  - [<span data-ttu-id="72e0c-161">Configuration de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e0c-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="72e0c-162">Déploiement des régions réseau, des sites et des sous-réseaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e0c-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="72e0c-163">Activation du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e0c-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72e0c-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72e0c-164">See Also</span></span>


[<span data-ttu-id="72e0c-165">Déploiement des fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72e0c-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

