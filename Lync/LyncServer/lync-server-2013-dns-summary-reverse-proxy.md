---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-proxy inverse'
description: 'Lync Server 2013 : Résumé des enregistrements DNS-proxy inverse.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2d806893786a11317be1eff9bfdc08c9230bf3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544790"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="012bd-103">Résumé des enregistrements DNS-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="012bd-103">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="012bd-104">_**Dernière modification de la rubrique :** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="012bd-104">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="012bd-105">Vous configurez deux cartes réseau dans votre serveur proxy inverse comme suit :</span><span class="sxs-lookup"><span data-stu-id="012bd-105">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="012bd-106">Cartes réseau de proxy inverse requises</span><span class="sxs-lookup"><span data-stu-id="012bd-106">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="012bd-107">**Carte réseau 1 (interface interne)** (exemple)</span><span class="sxs-lookup"><span data-stu-id="012bd-107">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="012bd-108">Interface interne avec 172.25.33.40 affecté.</span><span class="sxs-lookup"><span data-stu-id="012bd-108">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="012bd-109">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="012bd-109">No default gateway is defined.</span></span>
    
    <span data-ttu-id="012bd-110">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du proxy inverse et les réseaux qui contiennent des serveurs de pools frontaux Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="012bd-110">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="012bd-111">**Carte réseau 2 (interface externe)** (exemple)</span><span class="sxs-lookup"><span data-stu-id="012bd-111">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="012bd-112">Au moins une adresse IP publique est affectée à cette carte réseau.</span><span class="sxs-lookup"><span data-stu-id="012bd-112">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="012bd-p101">La passerelle est définie de sorte à pointer sur le routeur ou le pare-feu intégré de votre périmètre extérieur. (10.45.16.1 dans les exemples de scénario)</span><span class="sxs-lookup"><span data-stu-id="012bd-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="012bd-115">Enregistrements DNS requis pour le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="012bd-115">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="012bd-116">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="012bd-116">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="012bd-117">FQDN</span><span class="sxs-lookup"><span data-stu-id="012bd-117">FQDN</span></span></th>
<th><span data-ttu-id="012bd-118">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="012bd-118">IP address</span></span></th>
<th><span data-ttu-id="012bd-119">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="012bd-119">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="012bd-120">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-120">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-121">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-121">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-122">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="012bd-122">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="012bd-p102">Services web externes à partir du déploiement interne. Des enregistrements supplémentaires peuvent être définis et créés pour tous les pools et les serveurs uniques de tous les domaines SIP qui utilisent ce proxy inverse et qui ont défini des services web externes.</span><span class="sxs-lookup"><span data-stu-id="012bd-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="012bd-125">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-125">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-126">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-126">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-127">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="012bd-127">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="012bd-128">Les services Web externes pour les directeurs ou les pools directeurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="012bd-128">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="012bd-129">Vous pouvez définir autant de directeurs que de directeurs distincts, qui peuvent être associés à d’autres domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="012bd-129">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="012bd-130">La définition des enregistrements DNS pour la publication et la publication des directeurs n’est ni le pool frontal, ni la décision du directeur.</span><span class="sxs-lookup"><span data-stu-id="012bd-130">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="012bd-131">Vous devez définir et publier le directeur et les services Web externes du pool frontal si vous utilisez des directeurs.</span><span class="sxs-lookup"><span data-stu-id="012bd-131">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="012bd-132">Les types de trafic spécifiques (pour l’authentification et les autres utilisations) seront d’abord envoyés au directeur, s’il est défini dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="012bd-132">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="012bd-133">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-133">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-134">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-134">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-135">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="012bd-135">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="012bd-136">Conférences rendez-vous publiées en externe</span><span class="sxs-lookup"><span data-stu-id="012bd-136">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="012bd-137">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-137">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-138">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-138">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-139">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="012bd-139">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="012bd-140">Conférences publiées en externe</span><span class="sxs-lookup"><span data-stu-id="012bd-140">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="012bd-141">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-141">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-142">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-142">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-143">Écouteur affecté pour Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="012bd-143">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="012bd-144">Office Web Apps Server déployé en interne ou dans le périmètre et publié pour l’accès au client externe</span><span class="sxs-lookup"><span data-stu-id="012bd-144">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="012bd-145">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="012bd-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="012bd-146">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="012bd-146">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="012bd-147">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="012bd-147">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="012bd-148">Enregistrement externe de découverte Lync pour la découverte automatique publiée en externe et inclut la mobilité, Microsoft Lync Web App et le planificateur Web App</span><span class="sxs-lookup"><span data-stu-id="012bd-148">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

