---
title: 'Lync Server 2013 : configuration requise pour le routage des Location-Based pour les conférences'
description: 'Lync Server 2013 : configuration requise pour le routage des Location-Based pour les conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542520"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f824d-103">Configuration requise pour le routage des Location-Based pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f824d-104">_**Dernière modification de la rubrique :** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="f824d-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="f824d-105">Les conditions requises pour l’installation et la configuration de l’application de conférence de routage de Location-Based sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f824d-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="f824d-106">La mise à jour cumulative 2 de Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f824d-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f824d-107">Si la mise à jour cumulative 2 ou ultérieure de Lync Server 2013 n’est pas installée sur un serveur ou un pool Lync dans votre topologie, la mise en œuvre de Location-Based routage des réunions Lync n’est pas garantie.</span><span class="sxs-lookup"><span data-stu-id="f824d-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="f824d-108">Le routage de Location-Based Lync Server 2013 est une condition préalable pour l’application de conférence de routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f824d-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="f824d-109">Pour plus d’informations sur la configuration du routage de Location-Based Lync Server 2013, reportez-vous à la rubrique [configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f824d-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="f824d-110">La configuration requise d' Location-Based application de conférence de routage est identique à la configuration requise pour le routage Location-Based de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f824d-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="f824d-111">Pour plus d’informations, reportez-vous à la rubrique [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f824d-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="f824d-112">Serveurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="f824d-112">Supported Servers</span></span>

<span data-ttu-id="f824d-113">L’application de conférence de routage de Location-Based nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur tous les serveurs de pool de Front-End et Standard Edition de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="f824d-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="f824d-114">Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync de votre topologie, les restrictions de routage Location-Based ne peuvent pas être appliquées entièrement sur les réunions Lync et les transferts d’appels consultatifs.</span><span class="sxs-lookup"><span data-stu-id="f824d-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="f824d-115">Le tableau suivant identifie les combinaisons de rôles serveur et de versions qui prennent en charge le routage des Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f824d-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f824d-116">Version du pool Front-End</span><span class="sxs-lookup"><span data-stu-id="f824d-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="f824d-117">Version du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f824d-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="f824d-118">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="f824d-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f824d-119">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="f824d-120">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="f824d-121">Oui</span><span class="sxs-lookup"><span data-stu-id="f824d-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f824d-122">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="f824d-123">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="f824d-124">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f824d-125">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="f824d-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f824d-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="f824d-127">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f824d-128">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="f824d-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f824d-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f824d-130">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f824d-131">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f824d-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="f824d-132">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="f824d-132">Any</span></span></p></td>
<td><p><span data-ttu-id="f824d-133">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f824d-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f824d-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="f824d-135">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="f824d-135">Any</span></span></p></td>
<td><p><span data-ttu-id="f824d-136">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f824d-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="f824d-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="f824d-138">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="f824d-138">Any</span></span></p></td>
<td><p><span data-ttu-id="f824d-139">Non</span><span class="sxs-lookup"><span data-stu-id="f824d-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="f824d-140">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="f824d-140">Supported Clients</span></span>

<span data-ttu-id="f824d-141">Les clients Lync qui prennent en charge Location-Based le routage des réunions Lync sont les mêmes que les clients qui prennent en charge Lync Server 2013 Location-Based le routage.</span><span class="sxs-lookup"><span data-stu-id="f824d-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="f824d-142">Pour plus d’informations, reportez-vous à la rubrique [prise en charge des clients et des serveurs pour le routage Location-Based](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f824d-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="f824d-143">Exigences de serveur de médiation pour les transferts d’appel consultatifs</span><span class="sxs-lookup"><span data-stu-id="f824d-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="f824d-144">L’application de conférence de routage de Location-Based nécessite le déploiement de serveurs de médiation autonomes afin d’appliquer des restrictions de routage Location-Based sur les transferts d’appel consultatifs.</span><span class="sxs-lookup"><span data-stu-id="f824d-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="f824d-145">Pour appliquer Location-Based routage des transferts d’appel consultatifs, le serveur de médiation doit être associé à un seul serveur de médiation (PBX, passerelle SIP, etc.) dans les régions réseau où le routage Location-Based est requis.</span><span class="sxs-lookup"><span data-stu-id="f824d-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="f824d-146">Si des homologues de serveur de médiation supplémentaires sont déployés dans la même région réseau, le serveur de médiation homologue doit être associé à un autre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f824d-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="f824d-147">Cette exigence est détaillée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="f824d-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="f824d-148">Serveur de médiation unique par plusieurs homologues de serveur de médiation lorsqu’un transfert d’appel consultatif est acheminé vers un homologue de serveur de médiation par le biais d’un serveur de médiation configuré avec plusieurs jonctions SIP vers plusieurs homologues (PBX et passerelles), le transfert d’appel consultatif est bloqué pour empêcher le contournement des appels téléphoniques PSTN si le transfert consultatif est autorisé via des jonctions SIP,</span><span class="sxs-lookup"><span data-stu-id="f824d-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="f824d-149">Par exemple, dans le cas d’un serveur de médiation unique traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :</span><span class="sxs-lookup"><span data-stu-id="f824d-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="f824d-150">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="f824d-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="f824d-151">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur de Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est interdit même s’il n’est pas pris en compte dans le cadre d’un contournement de téléphone PSTN potentiel.</span><span class="sxs-lookup"><span data-stu-id="f824d-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="f824d-152">Serveurs de médiation distincts par homologue de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="f824d-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="f824d-153">Lorsqu’un transfert consultatif est ciblé sur un homologue de serveur de médiation, le transfert consultatif est évalué par rapport à l’homologue de serveur de médiation unique desservi par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f824d-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="f824d-154">L’appel sera rejeté ou autorisé en fonction du potentiel qu’il peut supporter dans le cadre du contournement de téléphone RTC, indépendamment de tous les autres homologues de serveur de médiation dans le site, car ils sont desservis par des serveurs de médiation distincts.</span><span class="sxs-lookup"><span data-stu-id="f824d-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="f824d-155">Par exemple, dans le cas d’un serveur de médiation distinct traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :</span><span class="sxs-lookup"><span data-stu-id="f824d-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="f824d-156">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="f824d-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="f824d-157">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est autorisé, car il n’est pas soumis à un contournement de téléphone PSTN potentiel.</span><span class="sxs-lookup"><span data-stu-id="f824d-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="f824d-158">Fonctionnalités non prises en charge par l’application de conférence de routage Location-Based</span><span class="sxs-lookup"><span data-stu-id="f824d-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="f824d-159">Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage de Location-Based :</span><span class="sxs-lookup"><span data-stu-id="f824d-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="f824d-160">Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="f824d-160">Dial-in conferencing.</span></span> <span data-ttu-id="f824d-161">Le routage des Location-Based ne peut pas être appliqué pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="f824d-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="f824d-162">Toute demande d’accès à une conférence donnée n’est pas restreinte par le routage des Location-Based même si l’organisateur de la Conférence est un utilisateur Lync activé pour le routage de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="f824d-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="f824d-163">Il est recommandé de ne pas mettre en service les numéros d’accès aux conférences dans les régions Location-Based où des restrictions de routage doivent être appliquées.</span><span class="sxs-lookup"><span data-stu-id="f824d-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

