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
ms.openlocfilehash: efdb03adbdf1392e27c3107eef4aaf97f3708e66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="c6137-102">Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6137-103">_**Dernière modification de la rubrique :** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="c6137-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="c6137-104">Le routage géodépendant est appliqué par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c6137-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="c6137-105">Lync Server peut identifier les sites réseau sur lesquels les utilisateurs se connectent à partir du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6137-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="c6137-106">Étant donné que les utilisateurs distants se trouvent à l’extérieur du réseau d’entreprise, leur emplacement est considéré comme inconnu.</span><span class="sxs-lookup"><span data-stu-id="c6137-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="c6137-107">Prise en charge de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c6137-107">Lync Server Support</span></span>

<span data-ttu-id="c6137-108">Le routage géodépendant nécessite que Lync Server 2013 CU1 soit déployé sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée.</span><span class="sxs-lookup"><span data-stu-id="c6137-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="c6137-109">Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage géodépendant ne peuvent pas être entièrement appliquées.</span><span class="sxs-lookup"><span data-stu-id="c6137-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="c6137-110">Le tableau suivant identifie les combinaisons de rôles serveur et de versions prises en charge pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="c6137-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6137-111">Version du pool</span><span class="sxs-lookup"><span data-stu-id="c6137-111">Pool version</span></span></th>
<th><span data-ttu-id="c6137-112">Version du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="c6137-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="c6137-113">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="c6137-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6137-114">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="c6137-115">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="c6137-116">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-117">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="c6137-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="c6137-119">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-120">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="c6137-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6137-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c6137-122">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-123">Mise à jour cumulative de Lync Server 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="c6137-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6137-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c6137-125">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="c6137-127">indifférent</span><span class="sxs-lookup"><span data-stu-id="c6137-127">any</span></span></p></td>
<td><p><span data-ttu-id="c6137-128">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c6137-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c6137-130">indifférent</span><span class="sxs-lookup"><span data-stu-id="c6137-130">any</span></span></p></td>
<td><p><span data-ttu-id="c6137-131">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6137-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c6137-133">indifférent</span><span class="sxs-lookup"><span data-stu-id="c6137-133">any</span></span></p></td>
<td><p><span data-ttu-id="c6137-134">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="c6137-135">Prise en charge des clients Lync</span><span class="sxs-lookup"><span data-stu-id="c6137-135">Lync Client Support</span></span>

<span data-ttu-id="c6137-136">Le tableau suivant identifie les clients pris en charge par le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="c6137-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6137-137">Type de client</span><span class="sxs-lookup"><span data-stu-id="c6137-137">Client type</span></span></th>
<th><span data-ttu-id="c6137-138">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="c6137-138">Supported</span></span></th>
<th><span data-ttu-id="c6137-139">Détails</span><span class="sxs-lookup"><span data-stu-id="c6137-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6137-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="c6137-141">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-141">yes</span></span></p></td>
<td><p><span data-ttu-id="c6137-142">Y compris la mise à jour cumulative de Lync 2013 février 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c6137-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="c6137-144">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c6137-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c6137-146">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c6137-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="c6137-148">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="c6137-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="c6137-150">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-151">Lync pour Windows 8</span><span class="sxs-lookup"><span data-stu-id="c6137-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="c6137-152">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6137-153">Lync mobile 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="c6137-154">Non</span><span class="sxs-lookup"><span data-stu-id="c6137-154">no</span></span></p></td>
<td><p><span data-ttu-id="c6137-155">La voix sur IP doit être désactivée pour les clients Lync mobile 2013 si elle est utilisée par des utilisateurs dont le routage géodépendant est activé.</span><span class="sxs-lookup"><span data-stu-id="c6137-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6137-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="c6137-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="c6137-157">oui</span><span class="sxs-lookup"><span data-stu-id="c6137-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="c6137-158">Pour désactiver VoIP pour les clients Lync mobile 2013, affectez une stratégie de mobilité avec le paramètre, audio/vidéo IP, désactivé pour tous les utilisateurs activés pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="c6137-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="c6137-159">Pour plus d’informations sur la stratégie de mobilité, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="c6137-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6137-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6137-160">See Also</span></span>


[<span data-ttu-id="c6137-161">Planification du routage géodépendant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6137-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

