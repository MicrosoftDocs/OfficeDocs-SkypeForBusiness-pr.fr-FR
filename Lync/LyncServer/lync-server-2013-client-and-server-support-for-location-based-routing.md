---
title: 'Lync Server 2013 : prise en charge des clients et des serveurs pour le routage géodépendant'
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
ms.openlocfilehash: daf0fb3656a5a57a5e4c7a6c25b7a08d29f79e86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b0784-102">Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0784-103">_**Dernière modification de la rubrique :** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="b0784-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="b0784-104">Le routage géodépendant est appliqué par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0784-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="b0784-105">Lync Server peut identifier les sites réseau sur lesquels les utilisateurs se connectent à partir du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="b0784-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="b0784-106">Étant donné que les utilisateurs distants se trouvent à l’extérieur du réseau d’entreprise, leur emplacement est considéré comme inconnu.</span><span class="sxs-lookup"><span data-stu-id="b0784-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="b0784-107">Prise en charge de Lync Server</span><span class="sxs-lookup"><span data-stu-id="b0784-107">Lync Server Support</span></span>

<span data-ttu-id="b0784-108">Le routage géodépendant nécessite que Lync Server 2013 CU1 soit déployé sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée.</span><span class="sxs-lookup"><span data-stu-id="b0784-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="b0784-109">Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage géodépendant ne peuvent pas être entièrement appliquées.</span><span class="sxs-lookup"><span data-stu-id="b0784-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="b0784-110">Le tableau suivant identifie les combinaisons de rôles serveur et de versions prises en charge pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="b0784-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0784-111">Version du pool</span><span class="sxs-lookup"><span data-stu-id="b0784-111">Pool version</span></span></th>
<th><span data-ttu-id="b0784-112">Version du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="b0784-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="b0784-113">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="b0784-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0784-114">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b0784-115">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b0784-116">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-117">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b0784-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b0784-119">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-120">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b0784-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b0784-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b0784-122">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-123">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b0784-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b0784-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b0784-125">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b0784-127">indifférent</span><span class="sxs-lookup"><span data-stu-id="b0784-127">any</span></span></p></td>
<td><p><span data-ttu-id="b0784-128">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b0784-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b0784-130">indifférent</span><span class="sxs-lookup"><span data-stu-id="b0784-130">any</span></span></p></td>
<td><p><span data-ttu-id="b0784-131">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b0784-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b0784-133">indifférent</span><span class="sxs-lookup"><span data-stu-id="b0784-133">any</span></span></p></td>
<td><p><span data-ttu-id="b0784-134">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="b0784-135">Prise en charge des clients Lync</span><span class="sxs-lookup"><span data-stu-id="b0784-135">Lync Client Support</span></span>

<span data-ttu-id="b0784-136">Le tableau suivant identifie les clients pris en charge par le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="b0784-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0784-137">Type de client</span><span class="sxs-lookup"><span data-stu-id="b0784-137">Client type</span></span></th>
<th><span data-ttu-id="b0784-138">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="b0784-138">Supported</span></span></th>
<th><span data-ttu-id="b0784-139">Détails</span><span class="sxs-lookup"><span data-stu-id="b0784-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0784-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="b0784-141">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-141">yes</span></span></p></td>
<td><p><span data-ttu-id="b0784-142">Y compris la mise à jour cumulative de Lync 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b0784-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="b0784-144">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b0784-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b0784-146">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b0784-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="b0784-148">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="b0784-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="b0784-150">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-151">Lync pour Windows 8</span><span class="sxs-lookup"><span data-stu-id="b0784-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="b0784-152">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0784-153">Lync mobile 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="b0784-154">Non</span><span class="sxs-lookup"><span data-stu-id="b0784-154">no</span></span></p></td>
<td><p><span data-ttu-id="b0784-155">La voix sur IP doit être désactivée pour les clients Lync mobile 2013 si elle est utilisée par des utilisateurs dont le routage géodépendant est activé.</span><span class="sxs-lookup"><span data-stu-id="b0784-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0784-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="b0784-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="b0784-157">oui</span><span class="sxs-lookup"><span data-stu-id="b0784-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="b0784-158">Pour désactiver VoIP pour les clients Lync mobile 2013, affectez une stratégie de mobilité avec le paramètre, audio/vidéo IP, désactivé pour tous les utilisateurs activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="b0784-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="b0784-159">Pour plus d’informations sur la stratégie de mobilité, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="b0784-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0784-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b0784-160">See Also</span></span>


[<span data-ttu-id="b0784-161">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0784-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

