---
title: 'Lync Server 2013 : Configuration du routage géodépendant'
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
ms.openlocfilehash: a0e82ae8a0dd9961bfeb9d2a513cb77b0affb2c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="efa09-102">Configuration du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa09-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efa09-103">_**Dernière modification de la rubrique :** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="efa09-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="efa09-104">Lync Server 2013 CU1, le routage selon l’emplacement est une fonctionnalité de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="efa09-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="efa09-105">Le routage basé sur l’emplacement est une fonctionnalité de gestion des appels qui contrôle le routage des appels par Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="efa09-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="efa09-106">Il applique des restrictions sur la façon dont les appels peuvent être routés vers des destinations PBX ou PSTN en fonction de l’emplacement de l’appelant Lync.</span><span class="sxs-lookup"><span data-stu-id="efa09-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="efa09-107">Le routage basé sur l’emplacement applique des règles d’autorisation d’appel aux appels RTC en fonction de l’emplacement réseau de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="efa09-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="efa09-108">L’emplacement de l’appelant est déterminé en fonction du site réseau associé au sous-réseau sur lequel est connecté l’appelant.</span><span class="sxs-lookup"><span data-stu-id="efa09-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="efa09-109">La configuration du routage par emplacement nécessite d’abord le déploiement de voix entreprise et la configuration des régions, sites et sous-réseaux réseau.</span><span class="sxs-lookup"><span data-stu-id="efa09-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="efa09-110">Cela permet de configurer la Fondation pour l’activation du routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="efa09-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="efa09-111">Avant de déployer le routage basé sur l’emplacement, vous devez d’abord déployer Enterprise Voice et configurer des régions, des sites et des sous-réseaux réseau associés sur les sites de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="efa09-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="efa09-112">Lorsque vous avez terminé, vous pouvez configurer le routage selon l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="efa09-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="efa09-113">Pour plus d’informations sur la façon de configurer des zones, des sites et des sous-réseaux, voir [déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="efa09-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="efa09-114">Cette section vous guide dans la configuration du routage basé sur l’emplacement à l’aide de l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="efa09-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="efa09-115">![Exemple de routage en fonction de l’emplacement voix entreprise](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemple de routage en fonction de l’emplacement voix entreprise")</span><span class="sxs-lookup"><span data-stu-id="efa09-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="efa09-116">Le tableau suivant représente les utilisateurs définis dans cet exemple.</span><span class="sxs-lookup"><span data-stu-id="efa09-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efa09-117">Type de point de terminaison</span><span class="sxs-lookup"><span data-stu-id="efa09-117">Endpoint type</span></span></th>
<th><span data-ttu-id="efa09-118">Lieu</span><span class="sxs-lookup"><span data-stu-id="efa09-118">Location</span></span></th>
<th><span data-ttu-id="efa09-119">Utilisateurs</span><span class="sxs-lookup"><span data-stu-id="efa09-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efa09-120">Lync</span><span class="sxs-lookup"><span data-stu-id="efa09-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="efa09-121">Delhi entreprise entreprise</span><span class="sxs-lookup"><span data-stu-id="efa09-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="efa09-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="efa09-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-123">Lync</span><span class="sxs-lookup"><span data-stu-id="efa09-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="efa09-124">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="efa09-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="efa09-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="efa09-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa09-126">Lync</span><span class="sxs-lookup"><span data-stu-id="efa09-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="efa09-127">Inconnu (c.-à-d. hôtel)</span><span class="sxs-lookup"><span data-stu-id="efa09-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="efa09-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="efa09-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-129">Private</span><span class="sxs-lookup"><span data-stu-id="efa09-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="efa09-130">Delhi entreprise entreprise</span><span class="sxs-lookup"><span data-stu-id="efa09-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="efa09-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="efa09-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa09-132">Private</span><span class="sxs-lookup"><span data-stu-id="efa09-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="efa09-133">Bureau d’entreprise Hyderabad</span><span class="sxs-lookup"><span data-stu-id="efa09-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="efa09-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="efa09-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="efa09-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="efa09-136">Encore</span><span class="sxs-lookup"><span data-stu-id="efa09-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="efa09-137">RTC-1, RTC-2, RTC-3</span><span class="sxs-lookup"><span data-stu-id="efa09-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="efa09-138">Le tableau suivant représente les systèmes illustrés dans cet exemple d’environnement.</span><span class="sxs-lookup"><span data-stu-id="efa09-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efa09-139">SYSTEME</span><span class="sxs-lookup"><span data-stu-id="efa09-139">System</span></span></th>
<th><span data-ttu-id="efa09-140">Lieu</span><span class="sxs-lookup"><span data-stu-id="efa09-140">Location</span></span></th>
<th><span data-ttu-id="efa09-141">Nom</span><span class="sxs-lookup"><span data-stu-id="efa09-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efa09-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="efa09-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="efa09-143">indifférente</span><span class="sxs-lookup"><span data-stu-id="efa09-143">any</span></span></p></td>
<td><p><span data-ttu-id="efa09-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="efa09-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-145">Lync Server 2013 CU1, médiation Server</span><span class="sxs-lookup"><span data-stu-id="efa09-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="efa09-146">indifférente</span><span class="sxs-lookup"><span data-stu-id="efa09-146">any</span></span></p></td>
<td><p><span data-ttu-id="efa09-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="efa09-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa09-148">Passerelle RTC 1</span><span class="sxs-lookup"><span data-stu-id="efa09-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="efa09-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="efa09-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="efa09-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="efa09-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-151">Passerelle RTC 2</span><span class="sxs-lookup"><span data-stu-id="efa09-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="efa09-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="efa09-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="efa09-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="efa09-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efa09-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="efa09-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="efa09-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="efa09-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="efa09-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="efa09-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efa09-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="efa09-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="efa09-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="efa09-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="efa09-159">PBX ROUGE</span><span class="sxs-lookup"><span data-stu-id="efa09-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="efa09-160">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="efa09-160">In This Section</span></span>

  - [<span data-ttu-id="efa09-161">Configuration d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa09-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="efa09-162">Déploiement de zones, sites et sous-réseaux réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa09-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="efa09-163">Activation du routage par emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa09-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="efa09-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efa09-164">See Also</span></span>


[<span data-ttu-id="efa09-165">Déploiement de fonctionnalités avancées d’entreprise voix dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa09-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

