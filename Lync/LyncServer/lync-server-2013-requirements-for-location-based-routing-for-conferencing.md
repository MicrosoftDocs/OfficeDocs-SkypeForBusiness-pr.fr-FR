---
title: 'Lync Server 2013 : configuration requise pour le routage géodépendant pour les conférences'
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
ms.openlocfilehash: 9a5e97ed5e762b35489eac0b69fbfcad45a8e822
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="02348-102">Configuration requise pour le routage géodépendant pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02348-103">_**Dernière modification de la rubrique :** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="02348-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="02348-104">Les conditions requises pour l’installation et la configuration de l’application de conférence de routage basée sur l’emplacement sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="02348-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="02348-105">La mise à jour cumulative 2 de Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="02348-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02348-106">Si la mise à jour cumulative 2 ou ultérieure de Lync Server 2013 n’est pas installée sur un pool ou un serveur Lync dans votre topologie, l’application du routage géodépendant des réunions Lync n’est pas garantie.</span><span class="sxs-lookup"><span data-stu-id="02348-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="02348-107">Le routage géodépendant de Lync Server 2013 est une condition préalable pour l’application de conférence de routage basée sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="02348-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="02348-108">Pour plus d’informations sur la configuration du routage géodépendant de Lync Server 2013, reportez-vous à la rubrique [Configuring location-based Routing](lync-server-2013-configuring-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="02348-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="02348-109">La configuration requise de l’application de conférence de routage basée sur l’emplacement est identique à celle requise pour le routage géodépendant de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02348-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="02348-110">Pour plus d’informations, reportez-vous à la rubrique [Planning for location-based Routing](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="02348-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="02348-111">Serveurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="02348-111">Supported Servers</span></span>

<span data-ttu-id="02348-112">L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur tous les pools frontaux et les serveurs Standard Edition de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="02348-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="02348-113">Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync de votre topologie, les restrictions de routage géodépendant ne peuvent pas être appliquées entièrement sur les réunions Lync et les transferts d’appels consultatifs.</span><span class="sxs-lookup"><span data-stu-id="02348-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="02348-114">Le tableau suivant identifie les combinaisons de rôles serveur et de versions qui prennent en charge le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="02348-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02348-115">Version du pool frontal</span><span class="sxs-lookup"><span data-stu-id="02348-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="02348-116">Version du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="02348-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="02348-117">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="02348-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02348-118">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="02348-119">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="02348-120">Oui</span><span class="sxs-lookup"><span data-stu-id="02348-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02348-121">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="02348-122">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="02348-123">Non</span><span class="sxs-lookup"><span data-stu-id="02348-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02348-124">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="02348-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="02348-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="02348-126">Non</span><span class="sxs-lookup"><span data-stu-id="02348-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02348-127">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="02348-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="02348-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="02348-129">Non</span><span class="sxs-lookup"><span data-stu-id="02348-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02348-130">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02348-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="02348-131">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="02348-131">Any</span></span></p></td>
<td><p><span data-ttu-id="02348-132">Non</span><span class="sxs-lookup"><span data-stu-id="02348-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02348-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="02348-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="02348-134">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="02348-134">Any</span></span></p></td>
<td><p><span data-ttu-id="02348-135">Non</span><span class="sxs-lookup"><span data-stu-id="02348-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02348-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="02348-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="02348-137">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="02348-137">Any</span></span></p></td>
<td><p><span data-ttu-id="02348-138">Non</span><span class="sxs-lookup"><span data-stu-id="02348-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="02348-139">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="02348-139">Supported Clients</span></span>

<span data-ttu-id="02348-140">Les clients Lync qui prennent en charge le routage géodépendant des réunions Lync sont les mêmes que ceux qui prennent en charge le routage géodépendant de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02348-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="02348-141">Pour plus d’informations, reportez-vous à la rubrique [prise en charge des clients et des serveurs pour le routage géodépendant](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="02348-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="02348-142">Exigences de serveur de médiation pour les transferts d’appel consultatifs</span><span class="sxs-lookup"><span data-stu-id="02348-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="02348-143">L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de serveurs de médiation autonomes afin d’appliquer des restrictions de routage géodépendant sur les transferts d’appel consultatifs.</span><span class="sxs-lookup"><span data-stu-id="02348-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="02348-144">Pour appliquer le routage basé sur l’emplacement des transferts d’appel consultatifs, le serveur de médiation doit être associé à un seul serveur de médiation (PBX, passerelle SIP, etc.) dans les régions réseau où le routage géodépendant est requis.</span><span class="sxs-lookup"><span data-stu-id="02348-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="02348-145">Si des homologues de serveur de médiation supplémentaires sont déployés dans la même région réseau, le serveur de médiation homologue doit être associé à un autre serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="02348-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="02348-146">Cette exigence est détaillée de la manière suivante :</span><span class="sxs-lookup"><span data-stu-id="02348-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="02348-147">Serveur de médiation unique par plusieurs homologues de serveur de médiation lorsqu’un transfert d’appel consultatif est acheminé vers un homologue de serveur de médiation via un serveur de médiation configuré avec plusieurs jonctions SIP vers plusieurs pairs (PBX et passerelles), le Conseil consultatif le transfert d’appel est bloqué pour empêcher la déviation du trafic téléphonique PSTN si le transfert d’appel consultatif est autorisé via certaines jonctions SIP, mais interdit par le biais d’autres jonctions SIP.</span><span class="sxs-lookup"><span data-stu-id="02348-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="02348-148">Par exemple, dans le cas d’un serveur de médiation unique traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :</span><span class="sxs-lookup"><span data-stu-id="02348-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="02348-149">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="02348-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="02348-150">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est interdit même s’il n’est pas en mesure d’engendrer une probabilité RTC potentielle. l contournement.</span><span class="sxs-lookup"><span data-stu-id="02348-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="02348-151">Serveurs de médiation distincts par homologue de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="02348-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="02348-152">Lorsqu’un transfert consultatif est ciblé sur un homologue de serveur de médiation, le transfert consultatif est évalué par rapport à l’homologue de serveur de médiation unique desservi par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="02348-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="02348-153">L’appel sera rejeté ou autorisé en fonction du potentiel qu’il peut supporter dans le cadre du contournement de téléphone RTC, indépendamment de tous les autres homologues de serveur de médiation dans le site, car ils sont desservis par des serveurs de médiation distincts.</span><span class="sxs-lookup"><span data-stu-id="02348-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="02348-154">Par exemple, dans le cas d’un serveur de médiation distinct traitant un homologue de serveur de médiation de passerelle PSTN et un homologue de serveur de médiation de PBX, le comportement suivant sera observé :</span><span class="sxs-lookup"><span data-stu-id="02348-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="02348-155">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PSTN à un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel n’est pas autorisé à empêcher le contournement de téléphone PSTN.</span><span class="sxs-lookup"><span data-stu-id="02348-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="02348-156">Lorsqu’un utilisateur Lync à partir d’un site donné (site 1) tente de transférer un appel avec un point de terminaison PBX dans le même site (site 1) vers un utilisateur Lync à partir d’un autre site (site 2) via le transfert consultatif, l’appel est autorisé, car il n’est pas soumis à un contournement de numéro de téléphone PSTN potentiel. ant.</span><span class="sxs-lookup"><span data-stu-id="02348-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="02348-157">Fonctionnalités non prises en charge par l’application de conférence de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="02348-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="02348-158">Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage basée sur l’emplacement :</span><span class="sxs-lookup"><span data-stu-id="02348-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="02348-159">Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="02348-159">Dial-in conferencing.</span></span> <span data-ttu-id="02348-160">Le routage géodépendant ne peut pas être appliqué pour les conférences rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="02348-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="02348-161">Toute demande d’accès à une conférence donnée n’est pas limitée par le routage géodépendant même si l’organisateur de la Conférence est un utilisateur Lync activé pour le routage géodépendant.</span><span class="sxs-lookup"><span data-stu-id="02348-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="02348-162">Il est recommandé de ne pas mettre en service les numéros d’accès aux conférences dans les régions où des restrictions de routage géodépendant doivent être appliquées.</span><span class="sxs-lookup"><span data-stu-id="02348-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

