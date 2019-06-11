---
title: 'Lync Server 2013: Résumé de port-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a40d86799b4922a819642aedf2461f038330593
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="f9174-102">Résumé du port-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9174-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9174-103">_**Dernière modification de la rubrique:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="f9174-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="f9174-104">Le service de découverte automatique de Lync Server 2013 s’exécute sur le directeur et les serveurs du pool frontal, et lorsqu’il `lyncdiscover.<domain>` est `lyncdiscoverinternal.<domain>` publié dans DNS à l’aide des enregistrements d’hôte et, les clients peuvent utiliser les fonctionnalités de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9174-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="f9174-105">Pour que les appareils mobiles exécutant Lync mobile puissent utiliser la découverte automatique, il est possible que vous deviez modifier les listes de noms de remplacement de l’objet du certificat sur tout directeur et serveur frontal exécutant le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="f9174-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="f9174-106">Par ailleurs, il est possible que vous deviez modifier les listes nom de remplacement de l’objet sur les certificats utilisés pour les règles de publication de service Web externe sur les proxys inverses.</span><span class="sxs-lookup"><span data-stu-id="f9174-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="f9174-107">La décision concernant l’utilisation des listes de noms de substitution sur les proxys inverse est basée sur le fait que vous publiez le service de découverte automatique sur le port 80 ou sur le port 443:</span><span class="sxs-lookup"><span data-stu-id="f9174-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="f9174-108">**Publié sur le port 80**   pour les appareils mobiles, aucune modification de certificat n’est requise si la requête initiale au service de découverte automatique a lieu sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="f9174-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="f9174-109">En effet, les appareils mobiles exécutant Lync accèderont au proxy inverse sur le port 80 en externe, puis seront redirigés vers un serveur directeur ou frontal sur le port 8080 en interne.</span><span class="sxs-lookup"><span data-stu-id="f9174-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="f9174-110">**Publié sur le port 443**   la liste autre nom de l’objet sur les certificats utilisés par la règle de publication des `lyncdiscover.<sipdomain>` services Web externes doit contenir une entrée pour chaque domaine SIP au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="f9174-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f9174-111">Pour les nouvelles installations ou mises à niveau de Lync Server 2010 sur lequel vous avez déployé une mobilité, vous avez utilisé le port 80 pour la découverte automatique du service de mobilité ou les certificats ayant été renommés avec le nom d’objet approprié et les noms de substitution de l’objet en vigueur.</span><span class="sxs-lookup"><span data-stu-id="f9174-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="f9174-112">Passez en revue les certificats de votre directeur et de votre serveur frontal pour vérifier le chemin que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="f9174-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="f9174-113">Détails du pare-feu pour le serveur proxy inverse: interface externe</span><span class="sxs-lookup"><span data-stu-id="f9174-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9174-114">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="f9174-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f9174-115">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="f9174-115">Source IP Address</span></span></th>
<th><span data-ttu-id="f9174-116">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="f9174-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="f9174-117">Notes</span><span class="sxs-lookup"><span data-stu-id="f9174-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9174-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="f9174-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="f9174-119">Indifférente</span><span class="sxs-lookup"><span data-stu-id="f9174-119">Any</span></span></p></td>
<td><p><span data-ttu-id="f9174-120">Écouteur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f9174-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="f9174-121">Facultatif Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;.</span><span class="sxs-lookup"><span data-stu-id="f9174-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="f9174-122">Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations dans lesquelles l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</span><span class="sxs-lookup"><span data-stu-id="f9174-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9174-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f9174-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f9174-124">Indifférente</span><span class="sxs-lookup"><span data-stu-id="f9174-124">Any</span></span></p></td>
<td><p><span data-ttu-id="f9174-125">Écouteur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="f9174-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="f9174-126">Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de l’appareil, développement de groupe, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</span><span class="sxs-lookup"><span data-stu-id="f9174-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="f9174-127">Détails du pare-feu pour le serveur proxy inverse: interface interne</span><span class="sxs-lookup"><span data-stu-id="f9174-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9174-128">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="f9174-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f9174-129">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="f9174-129">Source IP Address</span></span></th>
<th><span data-ttu-id="f9174-130">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="f9174-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="f9174-131">Notes</span><span class="sxs-lookup"><span data-stu-id="f9174-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9174-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="f9174-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="f9174-133">Interface du proxy inverse interne</span><span class="sxs-lookup"><span data-stu-id="f9174-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="f9174-134">Serveur frontal, pool frontal, directeur, pool de directeurs, Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="f9174-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="f9174-135">Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</span><span class="sxs-lookup"><span data-stu-id="f9174-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="f9174-136">Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</span><span class="sxs-lookup"><span data-stu-id="f9174-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9174-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="f9174-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="f9174-138">Interface du proxy inverse interne</span><span class="sxs-lookup"><span data-stu-id="f9174-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="f9174-139">Serveur frontal, pool frontal, directeur, pool de directeurs, Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="f9174-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="f9174-140">Le trafic envoyé au port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</span><span class="sxs-lookup"><span data-stu-id="f9174-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

