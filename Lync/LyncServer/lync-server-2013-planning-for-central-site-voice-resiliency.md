---
title: 'Lync Server 2013 : Planification de la résistance vocale du site central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="24e83-102">Planification de la résistance vocale du site central dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e83-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24e83-103">_**Dernière modification de la rubrique:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="24e83-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="24e83-104">De plus en plus d’entreprises ont plusieurs sites basés dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="24e83-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="24e83-105">La mise à jour des services d’urgence, l’accès au support technique et la possibilité d’effectuer des tâches professionnelles critiques quand un site central est hors service est essentiel pour toute solution de résilience vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="24e83-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="24e83-106">Quand un site central devient indisponible, les conditions suivantes doivent être remplies :</span><span class="sxs-lookup"><span data-stu-id="24e83-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="24e83-107">Le basculement vocal doit être fourni.</span><span class="sxs-lookup"><span data-stu-id="24e83-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="24e83-108">Les utilisateurs qui s’inscrivent habituellement avec le pool frontal sur le site central doivent pouvoir s’inscrire avec un autre pool frontal.</span><span class="sxs-lookup"><span data-stu-id="24e83-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="24e83-109">Pour ce faire, vous pouvez créer plusieurs enregistrements SRV DNS, chacun d’eux résolu vers un pool de directeurs ou un pool frontal dans chacun de vos sites centraux.</span><span class="sxs-lookup"><span data-stu-id="24e83-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="24e83-110">Vous pouvez ajuster la priorité et le poids des enregistrements SRV de telle sorte que les utilisateurs qui sont servis par ce site central obtiennent le directeur et la liste frontale correspondants dans d’autres enregistrements SRV.</span><span class="sxs-lookup"><span data-stu-id="24e83-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="24e83-111">Les appels pour et par les utilisateurs situés sur d’autres sites doivent être réacheminés vers le RTC.</span><span class="sxs-lookup"><span data-stu-id="24e83-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="24e83-112">Cette rubrique décrit la solution recommandée pour sécuriser la résistance vocale du site central.</span><span class="sxs-lookup"><span data-stu-id="24e83-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="24e83-113">Architecture et topologie</span><span class="sxs-lookup"><span data-stu-id="24e83-113">Architecture and Topology</span></span>

<span data-ttu-id="24e83-114">La planification de la résilience vocale sur un site central nécessite une connaissance de base du rôle central joué par le Bureau d’enregistrement 2013 du serveur Lync en activant le basculement sur voix.</span><span class="sxs-lookup"><span data-stu-id="24e83-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="24e83-115">Lync Server Registrar est un rôle serveur qui permet l’inscription et l’authentification du client et fournit les services de routage.</span><span class="sxs-lookup"><span data-stu-id="24e83-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="24e83-116">Il se trouve avec d’autres composants sur un serveur Standard Edition, un serveur frontal, un directeur ou une branche Survivable.</span><span class="sxs-lookup"><span data-stu-id="24e83-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="24e83-117">Un pool d’bureaux d’enregistrement est constitué de services d’enregistrement de registre en cours d’exécution sur le pool frontal et résidant sur le même site.</span><span class="sxs-lookup"><span data-stu-id="24e83-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="24e83-118">Le pool frontal doit être équilibré.</span><span class="sxs-lookup"><span data-stu-id="24e83-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="24e83-119">L’équilibrage de charge DNS est recommandé, mais l’équilibrage de charge matérielle est acceptable.</span><span class="sxs-lookup"><span data-stu-id="24e83-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="24e83-120">Un client Lync Découvre le pool frontal par le biais du mécanisme de découverte suivant:</span><span class="sxs-lookup"><span data-stu-id="24e83-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="24e83-121">Enregistrement DNS SRV</span><span class="sxs-lookup"><span data-stu-id="24e83-121">DNS SRV record</span></span>

2.  <span data-ttu-id="24e83-122">Service Web de découverte automatique (nouveau dans Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="24e83-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="24e83-123">Option DHCP 120</span><span class="sxs-lookup"><span data-stu-id="24e83-123">DHCP option 120</span></span>

<span data-ttu-id="24e83-124">Lorsque le client Lync se connecte au pool frontal, il est dirigé par le biais de l’équilibrage de charge vers l’un des serveurs frontaux de la liste.</span><span class="sxs-lookup"><span data-stu-id="24e83-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="24e83-125">Ce serveur frontal, à son tour, redirige le client vers un bureau d’enregistrement préféré dans le pool.</span><span class="sxs-lookup"><span data-stu-id="24e83-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="24e83-126">Chaque utilisateur activé pour voix entreprise est attribué à un pool d’bureaux d’enregistrement particulier, lequel devient le pool d’inscriptions principal de cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24e83-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="24e83-127">Sur un site donné, des centaines voire des milliers d’utilisateurs partagent généralement un seul pool de serveurs d’inscriptions principal.</span><span class="sxs-lookup"><span data-stu-id="24e83-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="24e83-128">Pour calculer la consommation des ressources du site central par les utilisateurs de site de succursale qui recourent au site central pour accéder aux fonctionnalités de présence, de conférence ou de basculement, nous vous conseillons de considérer chaque utilisateur de site de succursale comme s’il était inscrit sur le site central.</span><span class="sxs-lookup"><span data-stu-id="24e83-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="24e83-129">Il n’existe actuellement aucune limite sur le nombre d’utilisateurs de sites de succursales, y compris les utilisateurs enregistrés auprès d’une unité de succursale Survivable.</span><span class="sxs-lookup"><span data-stu-id="24e83-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="24e83-130">Pour garantir la résistance vocale en cas de défaillance du site central, le pool de serveurs d’inscriptions principal doit avoir un pool de serveurs d’inscriptions de sauvegarde associé, situé sur un autre site.</span><span class="sxs-lookup"><span data-stu-id="24e83-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="24e83-131">La sauvegarde peut être configurée à l’aide des paramètres de résilience du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="24e83-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="24e83-132">S’il existe une liaison réseau étendu résistante entre les deux sites, les utilisateurs dont le pool de serveurs d’inscriptions principal n’est plus disponible sont automatiquement dirigés vers le pool de serveurs d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24e83-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="24e83-133">Les étapes suivantes décrivent le processus de découverte et d’inscription des clients :</span><span class="sxs-lookup"><span data-stu-id="24e83-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="24e83-134">Un client Découvre Lync Server via les enregistrements DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="24e83-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="24e83-135">Dans Lync Server 2013, les enregistrements DNS SRV peuvent être configurés pour renvoyer plusieurs FQDN vers la requête DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="24e83-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="24e83-136">Par exemple, si l’entreprise Contoso possède trois sites centraux (Amérique du Nord, Europe et Asie-Pacifique) et un pool directeur sur chaque site central, les enregistrements DNS SRV peuvent pointer vers les noms de domaine complets du pool directeur sur chacun des trois sites.</span><span class="sxs-lookup"><span data-stu-id="24e83-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="24e83-137">Tant que le pool de directeurs dans l’un des emplacements est disponible, le client peut se connecter au premier serveur Lync tronçon.</span><span class="sxs-lookup"><span data-stu-id="24e83-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24e83-138">L’utilisation d’un pool de directeurs est facultative.</span><span class="sxs-lookup"><span data-stu-id="24e83-138">Using a Director pool is optional.</span></span> <span data-ttu-id="24e83-139">Un pool frontal peut être utilisé à la place.</span><span class="sxs-lookup"><span data-stu-id="24e83-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="24e83-140">Le pool de répertoires informe le client Lync sur le pool d’inscriptions principal de l’utilisateur et le pool d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24e83-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="24e83-141">Le client Lync tente d’abord de se connecter au pool d’inscriptions principal de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24e83-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="24e83-142">Si le pool de serveurs d’inscriptions principal est disponible, le serveur d’inscriptions accepte l’inscription.</span><span class="sxs-lookup"><span data-stu-id="24e83-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="24e83-143">Si le pool d’inscriptions principal n’est pas disponible, le client Lync tente de se connecter au pool d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24e83-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="24e83-144">Si le pool de serveurs d’inscriptions de sauvegarde est disponible et a déterminé que le pool de serveurs d’inscriptions principal de l’utilisateur est indisponible (en détectant un manque de pulsations pendant l’intervalle de basculement spécifié), le pool de serveurs d’inscriptions de sauvegarde accepte l’inscription de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="24e83-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="24e83-145">Après que le Bureau d’enregistrement de la sauvegarde a détecté que le Bureau d’enregistrement principal est de nouveau disponible, le pool d’inscriptions de sauvegarde redirigera les clients Lync de basculement vers leur pool principal.</span><span class="sxs-lookup"><span data-stu-id="24e83-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="24e83-146">La figure suivante illustre la topologie recommandée pour garantir la résilience du site central.</span><span class="sxs-lookup"><span data-stu-id="24e83-146">The following figure shows the recommended topology for assuring central site resiliency.</span></span> <span data-ttu-id="24e83-147">Les deux sites sont connectés à l’aide d’une liaison réseau étendu fiable.</span><span class="sxs-lookup"><span data-stu-id="24e83-147">The two sites are connected by a resilient WAN link.</span></span> <span data-ttu-id="24e83-148">Si le site central devient indisponible, les utilisateurs qui sont affectés à ce pool sont dirigés vers le site de sauvegarde pour inscription.</span><span class="sxs-lookup"><span data-stu-id="24e83-148">If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="24e83-149">**Topologie recommandée pour la résilience vocale d’un site central**</span><span class="sxs-lookup"><span data-stu-id="24e83-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="24e83-150">![Topologie pour les appels vocaux de site resliency] (images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie pour les appels vocaux de site resliency")</span><span class="sxs-lookup"><span data-stu-id="24e83-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="24e83-151">Conditions requises et recommandations</span><span class="sxs-lookup"><span data-stu-id="24e83-151">Requirements and Recommendations</span></span>

<span data-ttu-id="24e83-152">Les conditions préalables et recommandations suivantes, relatives à l’implémentation de la résistance vocale du site central, sont appropriées à la plupart des organisations :</span><span class="sxs-lookup"><span data-stu-id="24e83-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="24e83-153">Les sites où se trouvent les pools de serveurs d’inscriptions principaux et de sauvegarde doivent être connectés par une liaison réseau étendu résistante.</span><span class="sxs-lookup"><span data-stu-id="24e83-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="24e83-154">Chaque site central doit contenir un pool de serveurs d’inscriptions comprenant un ou plusieurs serveurs d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="24e83-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="24e83-155">La charge de chaque pool de serveurs d’inscriptions doit être équilibrée via l’équilibrage de la charge DNS, l’équilibrage de la charge matérielle ou les deux.</span><span class="sxs-lookup"><span data-stu-id="24e83-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="24e83-156">Pour plus d’informations sur la planification de la configuration de l’équilibrage de charge, voir [Configuration requise pour l’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24e83-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="24e83-157">Chaque utilisateur doit être affecté à un pool d’inscriptions principal en utilisant l’applet **de commande Set-Csuser** de Lync Server Management Shell ou le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24e83-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="24e83-158">Le pool de serveurs d’inscriptions principal doit être associé à un pool de serveurs d’inscriptions de sauvegarde situé sur un autre site central.</span><span class="sxs-lookup"><span data-stu-id="24e83-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="24e83-159">Le pool de serveurs d’inscriptions principal doit être configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="24e83-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="24e83-160">Par défaut, le serveur d’inscriptions principal est configuré pour basculer vers le pool de serveurs d’inscriptions de sauvegarde après 300 secondes.</span><span class="sxs-lookup"><span data-stu-id="24e83-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="24e83-161">Vous pouvez modifier cet intervalle à l’aide du générateur de topologie Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="24e83-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="24e83-162">Configurez un itinéraire de basculement, comme décrit dans la rubrique «[configuration d’un itinéraire de basculement dans Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)» de la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="24e83-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="24e83-163">Lors de la configuration de l’itinéraire, spécifiez une passerelle située sur un autre site que la passerelle définie dans l’itinéraire principal.</span><span class="sxs-lookup"><span data-stu-id="24e83-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="24e83-164">Si le site central contient votre serveur de gestion principal et qu’il est susceptible d’être indisponible pendant une longue période, vous devez réinstaller vos outils de gestion sur le site de sauvegarde ; sinon, vous ne pourrez pas modifier vos paramètres de gestion.</span><span class="sxs-lookup"><span data-stu-id="24e83-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="24e83-165">Dépendances</span><span class="sxs-lookup"><span data-stu-id="24e83-165">Dependencies</span></span>

<span data-ttu-id="24e83-166">Le serveur Lync dépend de l’infrastructure et des composants logiciels suivants pour garantir la résilience vocale:</span><span class="sxs-lookup"><span data-stu-id="24e83-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24e83-167"><strong>Composant</strong></span><span class="sxs-lookup"><span data-stu-id="24e83-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="24e83-168"><strong>Fonction</strong></span><span class="sxs-lookup"><span data-stu-id="24e83-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24e83-169">DNS</span><span class="sxs-lookup"><span data-stu-id="24e83-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="24e83-170">Résolution des enregistrements SRV et des enregistrements A pour la connectivité serveur-serveur et serveur-client</span><span class="sxs-lookup"><span data-stu-id="24e83-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24e83-171">Exchange et services web Exchange (EWS)</span><span class="sxs-lookup"><span data-stu-id="24e83-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="24e83-172">Stockage des contacts ; données de calendrier</span><span class="sxs-lookup"><span data-stu-id="24e83-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24e83-173">Messagerie unifiée Exchange et services web Exchange</span><span class="sxs-lookup"><span data-stu-id="24e83-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="24e83-174">Journaux des appels, liste des messages vocaux, messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="24e83-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24e83-175">Options DHCP 120</span><span class="sxs-lookup"><span data-stu-id="24e83-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="24e83-176">Si DNS SRV n’est pas disponible, le client tente d’utiliser l’option DHCP 120 pour découvrir le serveur d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="24e83-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="24e83-177">Pour que cette opération fonctionne, un serveur DHCP doit être configuré ou le protocole DHCP Lync Server 2013 doit être activé.</span><span class="sxs-lookup"><span data-stu-id="24e83-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="24e83-178">Pour plus d’informations, consultez la configuration matérielle et logicielle requise pour la résilience de site pour les filiales dans la section Configuration de la résilience de <a href="lync-server-2013-branch-site-resiliency-requirements.md">site pour Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="24e83-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="24e83-179">Fonctionnalités vocales de secours</span><span class="sxs-lookup"><span data-stu-id="24e83-179">Survivable Voice Features</span></span>

<span data-ttu-id="24e83-180">Si les conditions et recommandations précédentes ont été implémentées, les fonctionnalités vocales suivantes seront fournies par le pool de serveurs d’inscriptions :</span><span class="sxs-lookup"><span data-stu-id="24e83-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="24e83-181">Appels RTC sortants</span><span class="sxs-lookup"><span data-stu-id="24e83-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="24e83-182">Appels RTC entrants si le fournisseur de services de téléphonie prend en charge le basculement vers un site de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="24e83-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="24e83-183">Appels Enterprise entre des utilisateurs situés sur le même site ou sur deux sites différents</span><span class="sxs-lookup"><span data-stu-id="24e83-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="24e83-184">Fonctionnalités de base de gestion des appels, dont la mise en attente, la récupération et le transfert</span><span class="sxs-lookup"><span data-stu-id="24e83-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="24e83-185">Messagerie instantanée entre deux utilisateurs et partage audio et vidéo entre des utilisateurs situés sur le même site</span><span class="sxs-lookup"><span data-stu-id="24e83-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="24e83-186">Services de transfert d’appel, de sonnerie simultanée des points de terminaison, de délégation d’appel et d’appel d’équipe, mais seulement si les deux parties utilisant la délégation d’appel (ou tous les membres de l’équipe) sont configurés sur le même site.</span><span class="sxs-lookup"><span data-stu-id="24e83-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="24e83-187">Les téléphones et clients existants continuent à fonctionner.</span><span class="sxs-lookup"><span data-stu-id="24e83-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="24e83-188">Enregistrement des détails des appels (CDR)</span><span class="sxs-lookup"><span data-stu-id="24e83-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="24e83-189">Authentification et autorisation</span><span class="sxs-lookup"><span data-stu-id="24e83-189">Authentication and authorization</span></span>

<span data-ttu-id="24e83-190">En fonction de leur configuration, les fonctionnalités vocales suivantes fonctionneront ou ne fonctionneront pas lors de la mise hors service d’un site central principal :</span><span class="sxs-lookup"><span data-stu-id="24e83-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="24e83-191">Dépôt et récupération de messages vocaux</span><span class="sxs-lookup"><span data-stu-id="24e83-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="24e83-192">Si vous souhaitez que la messagerie unifiée Exchange soit disponible lorsque le site central principal est hors service, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="24e83-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="24e83-193">Modifiez les enregistrements DNS SRV pour que les serveurs de messagerie unifiée Exchange situés sur le site central pointent sur les serveurs de messagerie unifiée Exchange de sauvegarde situés sur un autre site.</span><span class="sxs-lookup"><span data-stu-id="24e83-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="24e83-194">Configurez le plan de numérotation de messagerie unifiée Exchange de chaque utilisateur de manière à inclure les serveurs de messagerie unifiée Exchange à la fois sur le site central et sur le site de sauvegarde, mais définissez les serveurs de messagerie unifiée Exchange</span><span class="sxs-lookup"><span data-stu-id="24e83-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="24e83-195">Si le site principal devient indisponible, l’administrateur Exchange doit marquer les serveurs Exchange UM sur le site de sauvegarde comme activé.</span><span class="sxs-lookup"><span data-stu-id="24e83-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="24e83-196">Si aucune des solutions précédentes n’est possible, la messagerie unifiée Exchange ne sera pas disponible dans l’éventualité où le site central ne sera pas disponible.</span><span class="sxs-lookup"><span data-stu-id="24e83-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="24e83-197">Conférence de tout type</span><span class="sxs-lookup"><span data-stu-id="24e83-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="24e83-p116">Un utilisateur qui a été basculé vers un site de sauvegarde peut prendre part à une conférence créée ou hébergée par un organisateur dont le pool est disponible, mais ne peut pas créer ni héberger de conférence sur son propre pool principal, qui n’est plus disponible. De même, les autres utilisateurs ne peuvent pas participer aux conférences hébergées sur le pool principal de l’utilisateur concerné.</span><span class="sxs-lookup"><span data-stu-id="24e83-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="24e83-200">Les fonctionnalités vocales suivantes ne fonctionnent pas lorsqu’un site central principal est hors service :</span><span class="sxs-lookup"><span data-stu-id="24e83-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="24e83-201">Standard automatique de conférence</span><span class="sxs-lookup"><span data-stu-id="24e83-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="24e83-202">Routage basé sur la présence et DND</span><span class="sxs-lookup"><span data-stu-id="24e83-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="24e83-203">Mise à jour des paramètres de transfert d’appel</span><span class="sxs-lookup"><span data-stu-id="24e83-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="24e83-204">Service Response Group et parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="24e83-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="24e83-205">Provisionnement des nouveaux téléphones et clients</span><span class="sxs-lookup"><span data-stu-id="24e83-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="24e83-206">Recherche web du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="24e83-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24e83-207">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="24e83-207">See Also</span></span>


[<span data-ttu-id="24e83-208">Planification de la résistance vocale d’un site de succursale dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24e83-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

