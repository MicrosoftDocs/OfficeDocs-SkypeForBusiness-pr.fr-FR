---
title: 'Lync Server 2013 : Prise en charge des clients et des serveurs pour le routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="68e33-102">Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68e33-103">_**Dernière modification de la rubrique:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="68e33-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="68e33-104">Le routage basé sur l’emplacement est appliqué par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68e33-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="68e33-105">Lync Server peut identifier les sites réseau dans lesquels les utilisateurs se connectent au sein du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="68e33-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="68e33-106">Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.</span><span class="sxs-lookup"><span data-stu-id="68e33-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="68e33-107">Prise en charge de Lync Server</span><span class="sxs-lookup"><span data-stu-id="68e33-107">Lync Server Support</span></span>

<span data-ttu-id="68e33-108">Le routage basé sur l’emplacement nécessite le déploiement de Lync Server 2013 CU1 sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée.</span><span class="sxs-lookup"><span data-stu-id="68e33-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="68e33-109">Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage basées sur l’emplacement ne peuvent pas être entièrement appliquées.</span><span class="sxs-lookup"><span data-stu-id="68e33-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="68e33-110">Le tableau suivant identifie la combinaison des rôles de serveur et des versions prises en charge pour le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="68e33-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68e33-111">Version du pool</span><span class="sxs-lookup"><span data-stu-id="68e33-111">Pool version</span></span></th>
<th><span data-ttu-id="68e33-112">Version de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="68e33-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="68e33-113">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="68e33-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68e33-114">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="68e33-115">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="68e33-116">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-117">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="68e33-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="68e33-119">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-120">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="68e33-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="68e33-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="68e33-122">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-123">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="68e33-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="68e33-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="68e33-125">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="68e33-127">Quelconque</span><span class="sxs-lookup"><span data-stu-id="68e33-127">any</span></span></p></td>
<td><p><span data-ttu-id="68e33-128">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="68e33-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="68e33-130">Quelconque</span><span class="sxs-lookup"><span data-stu-id="68e33-130">any</span></span></p></td>
<td><p><span data-ttu-id="68e33-131">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="68e33-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="68e33-133">Quelconque</span><span class="sxs-lookup"><span data-stu-id="68e33-133">any</span></span></p></td>
<td><p><span data-ttu-id="68e33-134">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="68e33-135">Prise en charge du client Lync</span><span class="sxs-lookup"><span data-stu-id="68e33-135">Lync Client Support</span></span>

<span data-ttu-id="68e33-136">Le tableau suivant identifie les clients pris en charge par le routage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="68e33-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68e33-137">Type de client</span><span class="sxs-lookup"><span data-stu-id="68e33-137">Client type</span></span></th>
<th><span data-ttu-id="68e33-138">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="68e33-138">Supported</span></span></th>
<th><span data-ttu-id="68e33-139">Détails</span><span class="sxs-lookup"><span data-stu-id="68e33-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68e33-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="68e33-141">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-141">yes</span></span></p></td>
<td><p><span data-ttu-id="68e33-142">Y compris la mise à jour cumulative de Lync 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="68e33-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="68e33-144">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="68e33-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="68e33-146">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="68e33-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="68e33-148">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="68e33-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="68e33-150">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-151">Lync pour Windows 8</span><span class="sxs-lookup"><span data-stu-id="68e33-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="68e33-152">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68e33-153">2013 mobile Lync</span><span class="sxs-lookup"><span data-stu-id="68e33-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="68e33-154">Non</span><span class="sxs-lookup"><span data-stu-id="68e33-154">no</span></span></p></td>
<td><p><span data-ttu-id="68e33-155">VoIP doit être désactivée pour les clients 2013 mobiles Lync, s’il est utilisé par les utilisateurs avec le routage par emplacement activé.</span><span class="sxs-lookup"><span data-stu-id="68e33-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68e33-156">2010 mobile Lync</span><span class="sxs-lookup"><span data-stu-id="68e33-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="68e33-157">Oui</span><span class="sxs-lookup"><span data-stu-id="68e33-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="68e33-158">Pour désactiver la voix sur IP (VoIP) pour les clients 2013 Lync mobile, attribuez une stratégie de mobilité avec le paramètre, audio/vidéo IP désactivé pour tous les utilisateurs activés pour le routage en fonction de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="68e33-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="68e33-159">Pour plus d’informations sur la stratégie de mobilité, reportez-vous à <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="68e33-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68e33-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68e33-160">See Also</span></span>


[<span data-ttu-id="68e33-161">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68e33-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

