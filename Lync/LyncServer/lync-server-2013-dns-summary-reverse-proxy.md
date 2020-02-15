---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-proxy inverse'
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
ms.openlocfilehash: fde945b4bd08020a072f36be073169454e423279
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="ef555-102">Résumé des enregistrements DNS-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef555-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef555-103">_**Dernière modification de la rubrique :** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="ef555-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="ef555-104">Vous configurez deux cartes réseau dans votre serveur proxy inverse comme suit :</span><span class="sxs-lookup"><span data-stu-id="ef555-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="ef555-105">Cartes réseau de proxy inverse requises</span><span class="sxs-lookup"><span data-stu-id="ef555-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="ef555-106">**Carte réseau 1 (interface interne)** (exemple)</span><span class="sxs-lookup"><span data-stu-id="ef555-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="ef555-107">Interface interne avec 172.25.33.40 affecté.</span><span class="sxs-lookup"><span data-stu-id="ef555-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="ef555-108">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="ef555-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="ef555-109">Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du proxy inverse et les réseaux qui contiennent des serveurs de pools frontaux Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="ef555-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="ef555-110">**Carte réseau 2 (interface externe)** (exemple)</span><span class="sxs-lookup"><span data-stu-id="ef555-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="ef555-111">Au moins une adresse IP publique est affectée à cette carte réseau.</span><span class="sxs-lookup"><span data-stu-id="ef555-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="ef555-p101">La passerelle est définie de sorte à pointer sur le routeur ou le pare-feu intégré de votre périmètre extérieur. (10.45.16.1 dans les exemples de scénario)</span><span class="sxs-lookup"><span data-stu-id="ef555-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="ef555-114">Enregistrements DNS requis pour le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="ef555-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ef555-115">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="ef555-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="ef555-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="ef555-116">FQDN</span></span></th>
<th><span data-ttu-id="ef555-117">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="ef555-117">IP address</span></span></th>
<th><span data-ttu-id="ef555-118">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="ef555-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ef555-119">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-121">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="ef555-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="ef555-p102">Services web externes à partir du déploiement interne. Des enregistrements supplémentaires peuvent être définis et créés pour tous les pools et les serveurs uniques de tous les domaines SIP qui utilisent ce proxy inverse et qui ont défini des services web externes.</span><span class="sxs-lookup"><span data-stu-id="ef555-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef555-124">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-126">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="ef555-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="ef555-127">Les services Web externes pour les directeurs ou les pools directeurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="ef555-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="ef555-128">Vous pouvez définir autant de directeurs que de directeurs distincts, qui peuvent être associés à d’autres domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="ef555-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="ef555-129">La définition des enregistrements DNS pour la publication et la publication des directeurs n’est ni le pool frontal, ni la décision du directeur.</span><span class="sxs-lookup"><span data-stu-id="ef555-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="ef555-130">Vous devez définir et publier le directeur et les services Web externes du pool frontal si vous utilisez des directeurs.</span><span class="sxs-lookup"><span data-stu-id="ef555-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="ef555-131">Les types de trafic spécifiques (pour l’authentification et les autres utilisations) seront d’abord envoyés au directeur, s’il est défini dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="ef555-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef555-132">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-134">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="ef555-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="ef555-135">Conférences rendez-vous publiées en externe</span><span class="sxs-lookup"><span data-stu-id="ef555-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef555-136">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-138">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="ef555-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="ef555-139">Conférences publiées en externe</span><span class="sxs-lookup"><span data-stu-id="ef555-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ef555-140">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-142">Écouteur affecté pour Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ef555-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="ef555-143">Office Web Apps Server déployé en interne ou dans le périmètre et publié pour l’accès au client externe</span><span class="sxs-lookup"><span data-stu-id="ef555-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ef555-144">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="ef555-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="ef555-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ef555-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ef555-146">Écouteur assigné pour les ressources publiées à l’extérieur</span><span class="sxs-lookup"><span data-stu-id="ef555-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="ef555-147">Enregistrement externe de découverte Lync pour la découverte automatique publiée en externe et inclut la mobilité, Microsoft Lync Web App et le planificateur Web App</span><span class="sxs-lookup"><span data-stu-id="ef555-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

