---
title: 'Lync Server 2013 : configuration requise pour le routage sur site pour les conférences'
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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="24c7d-102">Configuration requise pour le routage sur site pour les conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24c7d-103">_**Dernière modification de la rubrique :** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="24c7d-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="24c7d-104">Voici les exigences requises pour l’installation et la configuration de l’application de conférence de routage basée sur l’emplacement :</span><span class="sxs-lookup"><span data-stu-id="24c7d-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="24c7d-105">La mise à jour cumulative 2 Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="24c7d-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="24c7d-106">Si une mise à jour cumulative 2 ou une version ultérieure de Lync Server 2013 n’est pas installée sur un serveur ou un pool Lync dans votre topologie, il n’est pas possible de garantir l’exécution du routage de réunion Lync dans l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="24c7d-107">Le routage de géolocalisation Lync Server 2013 est une configuration requise pour l’application de conférence de routage basée sur l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="24c7d-108">Pour plus d’informations sur la configuration du routage de l’emplacement de Lync Server 2013, voir [configuration du routage en fonction](lync-server-2013-configuring-location-based-routing.md)de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="24c7d-109">Les exigences de l’application conférences de routage de géolocalisation sont les mêmes que celles requises pour le routage en fonction de l’emplacement de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24c7d-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="24c7d-110">Pour plus d’informations, reportez-vous à la rubrique [planification pour le routage sur site](lync-server-2013-planning-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="24c7d-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="24c7d-111">Serveurs pris en charge</span><span class="sxs-lookup"><span data-stu-id="24c7d-111">Supported Servers</span></span>

<span data-ttu-id="24c7d-112">L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de la mise à jour cumulative 2 de Lync Server 2013 sur toutes les listes frontales et les serveurs Standard Edition dans votre topologie.</span><span class="sxs-lookup"><span data-stu-id="24c7d-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="24c7d-113">Si la mise à jour cumulative 2 de Lync Server 2013 n’est pas installée sur certains serveurs Lync dans votre topologie, les restrictions de routage basées sur les emplacements ne peuvent pas être entièrement appliquées lors des réunions Lync et des transferts d’appel.</span><span class="sxs-lookup"><span data-stu-id="24c7d-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="24c7d-114">Le tableau suivant identifie la combinaison de rôles et de versions du serveur prenant en charge le routage par emplacement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24c7d-115">Version de pool frontal</span><span class="sxs-lookup"><span data-stu-id="24c7d-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="24c7d-116">Version de serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="24c7d-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="24c7d-117">Pris en charge</span><span class="sxs-lookup"><span data-stu-id="24c7d-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c7d-118">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-119">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-120">Oui</span><span class="sxs-lookup"><span data-stu-id="24c7d-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c7d-121">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-122">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="24c7d-123">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c7d-124">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="24c7d-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="24c7d-126">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c7d-127">Mise à jour cumulative 2 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="24c7d-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-129">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c7d-130">Mise à jour cumulative 1 de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24c7d-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="24c7d-131">Indifférente</span><span class="sxs-lookup"><span data-stu-id="24c7d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="24c7d-132">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24c7d-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="24c7d-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="24c7d-134">Indifférente</span><span class="sxs-lookup"><span data-stu-id="24c7d-134">Any</span></span></p></td>
<td><p><span data-ttu-id="24c7d-135">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24c7d-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="24c7d-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="24c7d-137">Indifférente</span><span class="sxs-lookup"><span data-stu-id="24c7d-137">Any</span></span></p></td>
<td><p><span data-ttu-id="24c7d-138">Non</span><span class="sxs-lookup"><span data-stu-id="24c7d-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="24c7d-139">Clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="24c7d-139">Supported Clients</span></span>

<span data-ttu-id="24c7d-140">Les clients Lync prenant en charge le routage par emplacement des réunions Lync sont les mêmes que ceux prenant en charge le routage sur l’emplacement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24c7d-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="24c7d-141">Pour plus d’informations, consultez [prise en charge des clients et du serveur pour le routage géolocalisation](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="24c7d-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="24c7d-142">Configuration requise pour le serveur de médiation pour les transferts d’appels</span><span class="sxs-lookup"><span data-stu-id="24c7d-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="24c7d-143">L’application de conférence de routage basée sur l’emplacement nécessite le déploiement de serveurs de médiation autonomes pour appliquer les restrictions de routage basées sur les emplacements aux transferts d’appel consultatif.</span><span class="sxs-lookup"><span data-stu-id="24c7d-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="24c7d-144">Pour appliquer le routage des appels de consultation selon l’emplacement, le serveur de médiation doit être associé à un seul homologue du serveur de médiation (par exemple, PBX, passerelle SIP, etc.) dans les régions réseau où le routage de l’emplacement est requis.</span><span class="sxs-lookup"><span data-stu-id="24c7d-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="24c7d-145">Si d’autres homologues du serveur de médiation sont déployés dans la même région réseau, l’homologue du serveur de médiation doit être associé à un serveur de médiation différent.</span><span class="sxs-lookup"><span data-stu-id="24c7d-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="24c7d-146">Cette obligation est détaillée comme suit :</span><span class="sxs-lookup"><span data-stu-id="24c7d-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="24c7d-147">Serveur de médiation unique par plusieurs homologues du serveur de médiation lorsque le transfert d’un appel consultatif est acheminé vers un homologue du serveur de médiation par le biais d’un serveur de médiation configuré avec plusieurs ISL SIP pour plusieurs homologues (PBX et passerelles), le Conseil le transfert d’appel est bloqué pour empêcher le contournement du protocole RTC si le transfert d’appel est autorisé par le biais de lignes SIP, mais rejeté par d’autres ISL SIP.</span><span class="sxs-lookup"><span data-stu-id="24c7d-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="24c7d-148">Par exemple, dans le cas d’un serveur de médiation unique qui dessert un homologue du serveur de médiation de la passerelle RTC et un homologue du serveur de médiation PBX, le comportement suivant est observé :</span><span class="sxs-lookup"><span data-stu-id="24c7d-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="24c7d-149">Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison RTC à un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel n’est pas autorisé à éviter le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="24c7d-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="24c7d-150">Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison PBX au sein d’un même site (site 1) pour un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais d’un virement RTC potentiel, l’appel est rejeté même l en contournement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="24c7d-151">Séparation des serveurs de médiation par le pair du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="24c7d-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="24c7d-152">Lorsque le transfert consultatif est ciblé auprès d’un homologue de serveur de médiation, le transfert de la consultation est évalué par rapport à l’homologue du serveur de médiation unique desservi par le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="24c7d-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="24c7d-153">L’appel sera interdit ou autorisé en fonction de son potentiel dans le cadre du contournement du numéro RTC, quels que soient les autres homologues du site dans le cadre de leur service par des serveurs de médiation distincts.</span><span class="sxs-lookup"><span data-stu-id="24c7d-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="24c7d-154">Par exemple, dans le cas d’un serveur de médiation distinct prenant en service un homologue de serveur de médiation de passerelle RTC et un homologue de serveur de médiation PBX, le comportement suivant est observé :</span><span class="sxs-lookup"><span data-stu-id="24c7d-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="24c7d-155">Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel avec un point de terminaison RTC à un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel n’est pas autorisé à éviter le contournement du numéro RTC.</span><span class="sxs-lookup"><span data-stu-id="24c7d-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="24c7d-156">Lorsqu’un utilisateur Lync à partir d’un site donné (par exemple, le site 1) tente de transférer un appel à l’aide d’un point de terminaison PBX dans le même site (site 1) pour un utilisateur Lync à partir d’un site différent (par exemple, site 2) par le biais du transfert de consultation, l’appel est autorisé à ne pas occasionner de contournement assurance.</span><span class="sxs-lookup"><span data-stu-id="24c7d-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="24c7d-157">Fonctionnalités non prises en charge par l’application de conférence de routage basée sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="24c7d-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="24c7d-158">Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence de routage basée sur l’emplacement :</span><span class="sxs-lookup"><span data-stu-id="24c7d-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="24c7d-159">Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="24c7d-159">Dial-in conferencing.</span></span> <span data-ttu-id="24c7d-160">Le routage en fonction de l’emplacement ne peut pas être appliqué pour la Conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="24c7d-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="24c7d-161">Toute demande d’accès à une conférence donnée n’est pas limitée par le routage de l’emplacement, même si l’organisateur de la Conférence est un utilisateur de Lync prenant en charge le routage de l’emplacement.</span><span class="sxs-lookup"><span data-stu-id="24c7d-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="24c7d-162">Nous vous conseillons de ne pas mettre en place des numéros d’accès aux conférences dans les régions dans lesquelles les restrictions de routage basées sur l’emplacement doivent être appliquées.</span><span class="sxs-lookup"><span data-stu-id="24c7d-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

