---
title: 'Lync Server 2013 : Résumé des ports-découverte automatique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93750418bce8ea98d0cee385232bc09bb0bd63bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b5a57-102">Résumé des ports-découverte automatique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5a57-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5a57-103">_**Dernière modification de la rubrique :** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="b5a57-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="b5a57-104">Le service de découverte automatique Lync Server 2013 s’exécute sur les serveurs de pools frontaux et de directeurs et, lorsqu' `lyncdiscover.<domain>` il `lyncdiscoverinternal.<domain>` est publié dans DNS à l’aide des enregistrements de l’hôte et, peut être utilisé par les clients pour accéder aux fonctionnalités de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5a57-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="b5a57-105">Pour que les appareils mobiles exécutant Lync mobile puissent utiliser la découverte automatique, vous devez d’abord modifier les listes des autres noms de sujet du certificat sur un directeur et un serveur frontal exécutant le service de découverte automatique.</span><span class="sxs-lookup"><span data-stu-id="b5a57-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="b5a57-106">En outre, il peut s’avérer nécessaire de modifier les listes des autres noms de sujet sur les certificats utilisés pour les règles de publication des services web externes sur les proxys inverses.</span><span class="sxs-lookup"><span data-stu-id="b5a57-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="b5a57-107">La décision d’utiliser des listes d’autres noms de sujet sur les proxys inverses est basée sur la publication du service de découverte automatique sur le port 80 ou sur le port 443 :</span><span class="sxs-lookup"><span data-stu-id="b5a57-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="b5a57-108">**Publié sur le port 80**   pour les appareils mobiles, aucune modification de certificat n’est requise si la requête initiale du service de découverte automatique a lieu sur le port 80.</span><span class="sxs-lookup"><span data-stu-id="b5a57-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="b5a57-109">Cela est dû au fait que les appareils mobiles exécutant Lync accèdent au proxy inverse sur le port 80 de manière externe, puis sont redirigés vers un directeur ou un serveur frontal sur le port 8080 en interne.</span><span class="sxs-lookup"><span data-stu-id="b5a57-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="b5a57-110">**Publié sur le port 443**   la liste autre nom du sujet sur les certificats utilisés par la règle de publication des services `lyncdiscover.<sipdomain>` Web externes doit contenir une entrée pour chaque domaine SIP de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b5a57-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b5a57-111">Pour les nouvelles installations ou mises à niveau à partir de Lync Server 2010 où vous avez déployé la mobilité, vous avez utilisé le port 80 pour la découverte automatique du service de mobilité ou émis à nouveau les certificats avec le nom d’objet et les autres noms de sujet appropriés sur place.</span><span class="sxs-lookup"><span data-stu-id="b5a57-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="b5a57-112">Passez en revue les certificats sur votre directeur et votre serveur frontal pour confirmer le chemin d’accès que vous avez choisi.</span><span class="sxs-lookup"><span data-stu-id="b5a57-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="b5a57-113">Informations sur le pare-feu pour le serveur proxy inverse : interface externe</span><span class="sxs-lookup"><span data-stu-id="b5a57-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5a57-114">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b5a57-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5a57-115">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b5a57-115">Source IP Address</span></span></th>
<th><span data-ttu-id="b5a57-116">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b5a57-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="b5a57-117">Notes</span><span class="sxs-lookup"><span data-stu-id="b5a57-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a57-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b5a57-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b5a57-119">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b5a57-119">Any</span></span></p></td>
<td><p><span data-ttu-id="b5a57-120">Port d’écoute du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b5a57-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b5a57-121">Module Redirection vers HTTPs si l’utilisateur entre http://&lt;publishedSiteFQDN&gt;.</span><span class="sxs-lookup"><span data-stu-id="b5a57-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="b5a57-122">Également requis si vous utilisez Office Web Apps pour les conférences et le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</span><span class="sxs-lookup"><span data-stu-id="b5a57-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a57-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b5a57-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b5a57-124">N'importe lequel</span><span class="sxs-lookup"><span data-stu-id="b5a57-124">Any</span></span></p></td>
<td><p><span data-ttu-id="b5a57-125">Port d’écoute du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b5a57-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b5a57-126">Téléchargements de carnets d’adresses, service de requête sur le Web du carnet d’adresses, découverte automatique, mises à jour du client, contenu de la réunion, mises à jour de périphériques, développement de groupes, Office Web Apps pour les conférences, Conférence rendez-vous et réunions.</span><span class="sxs-lookup"><span data-stu-id="b5a57-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="b5a57-127">Informations sur le pare-feu pour le serveur proxy inverse : interface interne</span><span class="sxs-lookup"><span data-stu-id="b5a57-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5a57-128">Protocole/TCP ou UDP/Port</span><span class="sxs-lookup"><span data-stu-id="b5a57-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b5a57-129">Adresse IP source</span><span class="sxs-lookup"><span data-stu-id="b5a57-129">Source IP Address</span></span></th>
<th><span data-ttu-id="b5a57-130">Adresse IP de destination</span><span class="sxs-lookup"><span data-stu-id="b5a57-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="b5a57-131">Notes</span><span class="sxs-lookup"><span data-stu-id="b5a57-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5a57-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="b5a57-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="b5a57-133">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b5a57-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b5a57-134">Serveur frontal, pool frontal, directeur, pool Directeur, Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="b5a57-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="b5a57-135">Obligatoire si vous utilisez le service de découverte automatique pour les appareils mobiles exécutant Lync dans les situations où l’organisation ne souhaite pas modifier le certificat de règle de publication du service Web externe.</span><span class="sxs-lookup"><span data-stu-id="b5a57-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="b5a57-136">Le trafic envoyé vers le port 80 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 8080 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</span><span class="sxs-lookup"><span data-stu-id="b5a57-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5a57-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b5a57-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b5a57-138">Interface interne du proxy inverse</span><span class="sxs-lookup"><span data-stu-id="b5a57-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b5a57-139">Serveur frontal, pool frontal, directeur, pool Directeur, Office Web Apps pour les conférences</span><span class="sxs-lookup"><span data-stu-id="b5a57-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="b5a57-140">Le trafic envoyé vers le port 443 sur l’interface externe du proxy inverse est redirigé vers un pool sur le port 4443 à partir de l’interface interne du proxy inverse. Ainsi, les services web du pool peuvent faire la distinction par rapport au trafic web interne.</span><span class="sxs-lookup"><span data-stu-id="b5a57-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

