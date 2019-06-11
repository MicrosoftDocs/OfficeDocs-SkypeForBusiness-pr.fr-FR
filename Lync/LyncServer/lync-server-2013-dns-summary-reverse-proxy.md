---
title: 'Lync Server 2013 : Résumé DNS - Proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="a49f5-102">Résumé DNS - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a49f5-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a49f5-103">_**Dernière modification de la rubrique:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="a49f5-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="a49f5-104">Vous pouvez configurer deux cartes réseau dans votre proxy inverse en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="a49f5-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="a49f5-105">Configuration requise pour la carte réseau du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="a49f5-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="a49f5-106">Exemple **de carte réseau 1 (interface interne)**</span><span class="sxs-lookup"><span data-stu-id="a49f5-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="a49f5-107">Interface interne avec 172.25.33.40 attribué.</span><span class="sxs-lookup"><span data-stu-id="a49f5-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="a49f5-108">Aucune passerelle par défaut n’est définie.</span><span class="sxs-lookup"><span data-stu-id="a49f5-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="a49f5-109">Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne du proxy inverse vers tout réseau qui contient des serveurs de pool frontal Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="a49f5-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="a49f5-110">Exemple **de carte réseau 2 (interface externe)**</span><span class="sxs-lookup"><span data-stu-id="a49f5-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="a49f5-111">Au moins une adresse IP publique est affectée à cette carte réseau.</span><span class="sxs-lookup"><span data-stu-id="a49f5-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="a49f5-112">La passerelle est définie de telle sorte qu’elle pointe vers le routeur ou le pare-feu intégré de votre périmètre externe.</span><span class="sxs-lookup"><span data-stu-id="a49f5-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="a49f5-113">(10.45.16.1 dans les exemples de scénarios)</span><span class="sxs-lookup"><span data-stu-id="a49f5-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="a49f5-114">Enregistrements DNS requis pour le proxy inverse</span><span class="sxs-lookup"><span data-stu-id="a49f5-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a49f5-115">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="a49f5-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="a49f5-116">FQDN</span><span class="sxs-lookup"><span data-stu-id="a49f5-116">FQDN</span></span></th>
<th><span data-ttu-id="a49f5-117">Adresse IP</span><span class="sxs-lookup"><span data-stu-id="a49f5-117">IP address</span></span></th>
<th><span data-ttu-id="a49f5-118">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="a49f5-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a49f5-119">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-121">Écouteur affecté pour les ressources publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="a49f5-122">Services Web externes du déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a49f5-122">External web services from the internal deployment.</span></span> <span data-ttu-id="a49f5-123">Il est possible de définir et de créer des enregistrements supplémentaires pour tous les domaines SIP qui utiliseront ce proxy inverse, ainsi que les services Web externes définis.</span><span class="sxs-lookup"><span data-stu-id="a49f5-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a49f5-124">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-126">Écouteur affecté pour les ressources publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="a49f5-127">Services Web externes pour les directeurs ou les pools de réalisateurs dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="a49f5-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="a49f5-128">Vous pouvez définir autant de directeurs qu’il existe de gestionnaires distincts, qui peuvent être associés à d’autres domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="a49f5-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="a49f5-129">La définition des enregistrements DNS pour et la publication des directeurs ne constituent pas le pool frontal ou la décision du réalisateur.</span><span class="sxs-lookup"><span data-stu-id="a49f5-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="a49f5-130">Vous devez définir et publier le directeur et les services Web externes du pool frontal si vous utilisez des directeurs.</span><span class="sxs-lookup"><span data-stu-id="a49f5-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="a49f5-131">Les types de trafic spécifiques (pour l’authentification et d’autres utilisations) seront d’abord envoyés au directeur, s’il est défini dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="a49f5-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a49f5-132">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-134">Écouteur affecté pour les ressources publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="a49f5-135">Conférence rendez-vous publiée en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a49f5-136">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-138">Écouteur affecté pour les ressources publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="a49f5-139">Conférences publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a49f5-140">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-142">Écouteur attribué pour Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="a49f5-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="a49f5-143">Office Web Apps Server déployé en interne ou dans le périmètre et publié pour un accès client externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a49f5-144">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="a49f5-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a49f5-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a49f5-146">Écouteur affecté pour les ressources publiées en externe</span><span class="sxs-lookup"><span data-stu-id="a49f5-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="a49f5-147">Lync Discover enregistrement externe pour une découverte automatique publiée en externe et inclut la mobilité, Microsoft Lync Web App et l’application Web du planificateur</span><span class="sxs-lookup"><span data-stu-id="a49f5-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

