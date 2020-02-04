---
title: 'Lync Server 2013 : Résumé des ports - Proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2944cde932413f00b5a4dcb75cd4a37bd5b3a3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="06332-102">Résumé des ports - Proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06332-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06332-103">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="06332-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="06332-104">Le proxy inverse est soumis à une configuration minimale pour le pare-feu et le port/protocole.</span><span class="sxs-lookup"><span data-stu-id="06332-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="06332-105">La configuration requise pour le pare-feu externe est HTTPs/TCP/443 et HTTP/TCP/80 facultatif.</span><span class="sxs-lookup"><span data-stu-id="06332-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="06332-106">HTTPs est utilisé pour les communications sécurisées SSL et TLS par le biais du proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="06332-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="06332-107">HTTP est utilisé si vous choisissez d’autoriser l’accès au service de découverte automatique lors de la modification des certificats peut s’avérer difficile ou n’est pas justifié.</span><span class="sxs-lookup"><span data-stu-id="06332-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="06332-108">Les clients peuvent contacter le serveur Office Web Apps sur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="06332-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="06332-109">Office Web Apps Server attend la communication de clients internes sur HTTPs/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="06332-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="06332-110">La configuration recommandée consiste à autoriser HTTPs/TCP/443 du proxy inverse au serveur Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="06332-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="06332-111">Le port 8080 est utilisé pour acheminer le trafic de l’interface interne du proxy inverse vers le serveur frontal, le pool d’adresses IP virtuelles du pool frontal ou le point de terminaison du réalisateur ou du réalisateur facultatif.</span><span class="sxs-lookup"><span data-stu-id="06332-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="06332-112">Le port TCP 8080 est requis pour les appareils mobiles exécutant Lync pour localiser le service de découverte automatique dans les cas où la modification du certificat de règle de publication de service Web externe n’est pas souhaitable (par exemple, si vous avez un grand nombre de domaines SIP).</span><span class="sxs-lookup"><span data-stu-id="06332-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="06332-113">Si vous choisissez d’acquérir de nouveaux certificats avec les entrées SAN nécessaires, le port TCP 8080 n’est pas nécessaire et est facultatif.</span><span class="sxs-lookup"><span data-stu-id="06332-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="06332-114">Le port 4443 est utilisé pour le trafic de l’interface interne du proxy inverse vers le serveur frontal, le pool d’adresses IP virtuelles de pool frontal ou le directeur principal ou le protocole principal de pool de réalisateur</span><span class="sxs-lookup"><span data-stu-id="06332-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="06332-115">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="06332-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="06332-116">Ne confondez pas le 4443 sur TCP à partir du proxy inverse vers le déploiement interne pour le port 4443 sur le trafic TCP à partir du serveur Standard Edition Server ou du pool frontal qui gère le rôle de magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="06332-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="06332-117">Détails sur les ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="06332-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="06332-118">Détails du pare-feu pour le serveur proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="06332-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06332-119">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="06332-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="06332-120">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="06332-120">Source IP Address</span></span></th>
<th><span data-ttu-id="06332-121">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="06332-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="06332-122">Remarques</span><span class="sxs-lookup"><span data-stu-id="06332-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06332-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="06332-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="06332-124">Indifférente</span><span class="sxs-lookup"><span data-stu-id="06332-124">Any</span></span></p></td>
<td><p><span data-ttu-id="06332-125">Écouteur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="06332-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="06332-126">Facultatif Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;.</span><span class="sxs-lookup"><span data-stu-id="06332-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="06332-127">Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations dans lesquelles l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</span><span class="sxs-lookup"><span data-stu-id="06332-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06332-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="06332-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="06332-129">Indifférente</span><span class="sxs-lookup"><span data-stu-id="06332-129">Any</span></span></p></td>
<td><p><span data-ttu-id="06332-130">Écouteur de proxy inverse</span><span class="sxs-lookup"><span data-stu-id="06332-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="06332-131">Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de l’appareil, développement de groupe, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</span><span class="sxs-lookup"><span data-stu-id="06332-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="06332-132">Détails du pare-feu pour le serveur proxy inverse : interface interne</span><span class="sxs-lookup"><span data-stu-id="06332-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06332-133">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="06332-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="06332-134">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="06332-134">Source IP Address</span></span></th>
<th><span data-ttu-id="06332-135">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="06332-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="06332-136">Remarques</span><span class="sxs-lookup"><span data-stu-id="06332-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06332-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="06332-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="06332-138">Interface du proxy inverse interne</span><span class="sxs-lookup"><span data-stu-id="06332-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="06332-139">Serveur frontal, pool frontal, directeur, pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="06332-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="06332-140">Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication de service Web externe.</span><span class="sxs-lookup"><span data-stu-id="06332-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="06332-141">Le trafic envoyé au port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</span><span class="sxs-lookup"><span data-stu-id="06332-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06332-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="06332-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="06332-143">Interface du proxy inverse interne</span><span class="sxs-lookup"><span data-stu-id="06332-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="06332-144">Serveur frontal, pool frontal, directeur, pool de réalisateurs</span><span class="sxs-lookup"><span data-stu-id="06332-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="06332-145">Le trafic envoyé au port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy, afin que les services Web de réserve puissent le différencier du trafic Web interne.</span><span class="sxs-lookup"><span data-stu-id="06332-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06332-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="06332-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="06332-147">Interface du proxy inverse interne</span><span class="sxs-lookup"><span data-stu-id="06332-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="06332-148">Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="06332-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

