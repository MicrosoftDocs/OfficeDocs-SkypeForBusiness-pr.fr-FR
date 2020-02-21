---
title: Configuration requise pour les ports Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port requirements
ms:assetid: 9a6c1300-ef88-4181-a8f1-43cd3093962b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398798(v=OCS.15)
ms:contentKeyID: 48184886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a4ac38534f7d52aca3df9c24cac10be10dee5be6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-requirements-for-lync-server-2013"></a><span data-ttu-id="b750a-102">Configuration requise pour les ports pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-102">Port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b750a-103">_**Dernière modification de la rubrique :** 2013-03-27_</span><span class="sxs-lookup"><span data-stu-id="b750a-103">_**Topic Last Modified:** 2013-03-27_</span></span>

<span data-ttu-id="b750a-104">Lync Server nécessite l’ouverture de ports spécifiques sur le pare-feu.</span><span class="sxs-lookup"><span data-stu-id="b750a-104">Lync Server requires that specific ports on the firewall be open.</span></span> <span data-ttu-id="b750a-105">En outre, si la sécurité IPsec (Internet Protocol Security) est déployée dans votre organisation, IPsec doit être désactivé sur la plage de ports utilisée pour la fourniture de l’audio, de la vidéo et de la vidéo panoramique.</span><span class="sxs-lookup"><span data-stu-id="b750a-105">Additionally, if Internet Protocol security (IPsec) is deployed in your organization, IPsec must be disabled over the range of ports used for the delivery of audio, video, and panorama video.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b750a-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b750a-106">In This Section</span></span>

<span data-ttu-id="b750a-107">Cette section contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b750a-107">This section includes the following topics:</span></span>

  - [<span data-ttu-id="b750a-108">Ports et protocoles pour les serveurs internes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-108">Ports and protocols for internal servers in Lync Server 2013</span></span>](lync-server-2013-ports-and-protocols-for-internal-servers.md)

  - [<span data-ttu-id="b750a-109">Exceptions IPsec dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-109">IPsec exceptions in Lync Server 2013</span></span>](lync-server-2013-ipsec-exceptions.md)

  - [<span data-ttu-id="b750a-110">Résumé des ports-serveur Edge unique consolidé avec adresses IP privées avec la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-110">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="b750a-111">Résumé des ports-serveur Edge unique consolidé avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-111">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="b750a-112">Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP privées à l’aide de la conversion d’adresses réseau dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-112">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="b750a-113">Résumé des ports-serveur Edge consolidé ajusté, équilibrage de charge DNS avec adresses IP publiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-113">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="b750a-114">Résumé des ports-serveur Edge consolidé ajusté avec des programmes d’équilibrage de la charge matérielle dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-114">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [<span data-ttu-id="b750a-115">Résumé des ports-proxy inverse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-115">Port summary - Reverse proxy in Lync Server 2013</span></span>](lync-server-2013-port-summary-reverse-proxy.md)

  - [<span data-ttu-id="b750a-116">Résumé des ports-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b750a-116">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

