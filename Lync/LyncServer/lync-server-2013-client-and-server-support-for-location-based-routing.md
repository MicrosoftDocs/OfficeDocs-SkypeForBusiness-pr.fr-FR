---
title: 'Lync Server 2013 : prise en charge des clients et des serveurs pour le routage des Location-Based'
description: 'Lync Server 2013 : prise en charge des clients et des serveurs pour le routage des Location-Based.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549630"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="7817d-103">Prise en charge des clients et des serveurs pour le routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7817d-104">_**Dernière modification de la rubrique :** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="7817d-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="7817d-105">Le routage des Location-Based est appliqué par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7817d-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="7817d-106">Lync Server peut identifier les sites réseau sur lesquels les utilisateurs se connectent à partir du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7817d-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="7817d-107">Étant donné que les utilisateurs distants se trouvent à l’extérieur du réseau d’entreprise, leur emplacement est considéré comme inconnu.</span><span class="sxs-lookup"><span data-stu-id="7817d-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="7817d-108">Prise en charge de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7817d-108">Lync Server Support</span></span>

<span data-ttu-id="7817d-109">Le routage des Location-Based nécessite que Lync Server 2013 CU1 soit déployé sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée.</span><span class="sxs-lookup"><span data-stu-id="7817d-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="7817d-110">Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage Location-Based ne peuvent pas être entièrement appliquées.</span><span class="sxs-lookup"><span data-stu-id="7817d-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="7817d-111">Le tableau suivant identifie les combinaisons de rôles serveur et de versions prises en charge pour le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="7817d-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7817d-112">Version du pool</span><span class="sxs-lookup"><span data-stu-id="7817d-112">Pool version</span></span></th>
<th><span data-ttu-id="7817d-113">Version du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="7817d-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="7817d-114">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="7817d-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7817d-115">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7817d-116">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7817d-117">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-118">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7817d-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="7817d-120">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-121">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7817d-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7817d-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="7817d-123">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-124">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="7817d-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7817d-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7817d-126">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="7817d-128">indifférent</span><span class="sxs-lookup"><span data-stu-id="7817d-128">any</span></span></p></td>
<td><p><span data-ttu-id="7817d-129">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7817d-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="7817d-131">indifférent</span><span class="sxs-lookup"><span data-stu-id="7817d-131">any</span></span></p></td>
<td><p><span data-ttu-id="7817d-132">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7817d-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7817d-134">indifférent</span><span class="sxs-lookup"><span data-stu-id="7817d-134">any</span></span></p></td>
<td><p><span data-ttu-id="7817d-135">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="7817d-136">Prise en charge des clients Lync</span><span class="sxs-lookup"><span data-stu-id="7817d-136">Lync Client Support</span></span>

<span data-ttu-id="7817d-137">Le tableau suivant identifie les clients pris en charge par Location-Based routage.</span><span class="sxs-lookup"><span data-stu-id="7817d-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7817d-138">Type de client</span><span class="sxs-lookup"><span data-stu-id="7817d-138">Client type</span></span></th>
<th><span data-ttu-id="7817d-139">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="7817d-139">Supported</span></span></th>
<th><span data-ttu-id="7817d-140">Détails</span><span class="sxs-lookup"><span data-stu-id="7817d-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7817d-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="7817d-142">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-142">yes</span></span></p></td>
<td><p><span data-ttu-id="7817d-143">Y compris la mise à jour cumulative de Lync 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7817d-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="7817d-145">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="7817d-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="7817d-147">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="7817d-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="7817d-149">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-150">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="7817d-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="7817d-151">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-152">Lync pour Windows 8</span><span class="sxs-lookup"><span data-stu-id="7817d-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="7817d-153">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7817d-154">Lync mobile 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="7817d-155">Non</span><span class="sxs-lookup"><span data-stu-id="7817d-155">no</span></span></p></td>
<td><p><span data-ttu-id="7817d-156">La voix sur IP doit être désactivée pour les clients Lync mobile 2013 si elle est utilisée par les utilisateurs avec le routage Location-Based activé.</span><span class="sxs-lookup"><span data-stu-id="7817d-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7817d-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="7817d-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="7817d-158">oui</span><span class="sxs-lookup"><span data-stu-id="7817d-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="7817d-159">Pour désactiver VoIP pour les clients Lync mobile 2013, affectez une stratégie de mobilité avec le paramètre, audio/vidéo IP, désactivé pour tous les utilisateurs activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="7817d-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="7817d-160">Pour plus d’informations sur la stratégie de mobilité, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="7817d-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7817d-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7817d-161">See Also</span></span>


[<span data-ttu-id="7817d-162">Planification du routage des Location-Based dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7817d-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

