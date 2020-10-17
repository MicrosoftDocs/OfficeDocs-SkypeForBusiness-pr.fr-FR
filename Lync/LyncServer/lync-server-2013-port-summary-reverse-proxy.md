---
title: 'Lync Server 2013 : Résumé des ports-proxy inverse'
description: 'Lync Server 2013 : Résumé des ports-proxy inverse.'
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
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555250"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="676dd-103">Résumé des ports-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="676dd-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="676dd-104">_**Dernière modification de la rubrique :** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="676dd-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="676dd-105">Le proxy inverse a des exigences minimales en matière de pare-feu et de port/protocole.</span><span class="sxs-lookup"><span data-stu-id="676dd-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="676dd-106">Exigences de pare-feu externe : HTTPs/TCP/443 et HTTP/TCP/80 facultatif.</span><span class="sxs-lookup"><span data-stu-id="676dd-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="676dd-107">HTTPs est utilisé pour les communications sécurisées SSL et TLS via le proxy inverse.</span><span class="sxs-lookup"><span data-stu-id="676dd-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="676dd-108">HTTP est utilisé si vous choisissez d’autoriser l’accès au service de découverte automatique lors de la modification des certificats peut s’avérer difficile ou non justifié.</span><span class="sxs-lookup"><span data-stu-id="676dd-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="676dd-109">Les clients s’attendent à contacter Office Web Apps Server sur HTTPs.</span><span class="sxs-lookup"><span data-stu-id="676dd-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="676dd-110">Office Web Apps Server attend la communication de clients internes sur HTTPs/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="676dd-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="676dd-111">La configuration recommandée consiste à autoriser le protocole HTTPs/TCP/443 à partir du proxy inverse vers le serveur Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="676dd-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="676dd-112">Le port 8080 est utilisé pour acheminer le trafic depuis l’interface interne du proxy inverse vers le serveur frontal, l’adresse IP virtuelle du pool frontal ou l’adresse IP virtuelle du pool directeur ou directeur facultatif.</span><span class="sxs-lookup"><span data-stu-id="676dd-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="676dd-113">Le port TCP 8080 est requis pour les appareils mobiles exécutant Lync pour localiser le service de découverte automatique dans les situations où la modification du certificat de règle de publication du service Web externe est indésirable (par exemple, si vous avez un grand nombre de domaines SIP).</span><span class="sxs-lookup"><span data-stu-id="676dd-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="676dd-114">Si vous choisissez d’acquérir de nouveaux certificats avec les entrées SAN nécessaires, le port TCP 8080 n’est pas nécessaire et devient facultatif.</span><span class="sxs-lookup"><span data-stu-id="676dd-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="676dd-115">Le port 4443 est utilisé pour le trafic provenant de l’interface interne du proxy inverse vers le serveur frontal, l’adresse IP virtuelle du pool frontal ou l’adresse IP virtuelle du pool directeur ou directeur facultatif.</span><span class="sxs-lookup"><span data-stu-id="676dd-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="676dd-116">![13142405-D5C9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-D5C9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="676dd-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="676dd-117">Ne confondez pas le 4443 sur TCP du proxy inverse au déploiement interne du port 4443 sur le trafic TCP à partir du serveur Standard Edition ou du pool frontal qui gère le rôle magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="676dd-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="676dd-118">Détails des ports et protocoles</span><span class="sxs-lookup"><span data-stu-id="676dd-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="676dd-119">Informations sur le pare-feu pour le serveur proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="676dd-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="676dd-120">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="676dd-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="676dd-121">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="676dd-121">Source IP Address</span></span></th>
<th><span data-ttu-id="676dd-122">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="676dd-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="676dd-123">Notes</span><span class="sxs-lookup"><span data-stu-id="676dd-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="676dd-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="676dd-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="676dd-125">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="676dd-125">Any</span></span></p></td>
<td><p><span data-ttu-id="676dd-126">Port d’écoute du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="676dd-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="676dd-127">Module Redirection vers HTTPs si l’utilisateur entre http:// &lt; publishedSiteFQDN &gt; .</span><span class="sxs-lookup"><span data-stu-id="676dd-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="676dd-128">Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</span><span class="sxs-lookup"><span data-stu-id="676dd-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="676dd-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="676dd-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="676dd-130">N’importe lequel</span><span class="sxs-lookup"><span data-stu-id="676dd-130">Any</span></span></p></td>
<td><p><span data-ttu-id="676dd-131">Port d’écoute du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="676dd-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="676dd-132">Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de périphériques, développement de groupes, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</span><span class="sxs-lookup"><span data-stu-id="676dd-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="676dd-133">Informations sur le pare-feu pour le serveur proxy inverse : interface interne</span><span class="sxs-lookup"><span data-stu-id="676dd-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="676dd-134">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="676dd-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="676dd-135">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="676dd-135">Source IP Address</span></span></th>
<th><span data-ttu-id="676dd-136">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="676dd-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="676dd-137">Notes</span><span class="sxs-lookup"><span data-stu-id="676dd-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="676dd-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="676dd-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="676dd-139">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="676dd-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="676dd-140">Serveur frontal, pool frontal, directeur, pool directeur</span><span class="sxs-lookup"><span data-stu-id="676dd-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="676dd-141">Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</span><span class="sxs-lookup"><span data-stu-id="676dd-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="676dd-142">Le trafic envoyé vers le port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</span><span class="sxs-lookup"><span data-stu-id="676dd-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="676dd-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="676dd-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="676dd-144">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="676dd-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="676dd-145">Serveur frontal, pool frontal, directeur, pool directeur</span><span class="sxs-lookup"><span data-stu-id="676dd-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="676dd-146">Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</span><span class="sxs-lookup"><span data-stu-id="676dd-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="676dd-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="676dd-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="676dd-148">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="676dd-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="676dd-149">Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="676dd-149">Office Web Apps for conferencing</span></span></p></td>
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

